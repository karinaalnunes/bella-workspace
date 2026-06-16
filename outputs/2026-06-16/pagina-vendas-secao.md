# Copy para AnalisePage — Máxima Finance IA
*Turno da noite — 16/06/2026 | Bella*

> **Para o dev:** Este documento contém todo o texto, microcopy, estados e lógica de exibição da AnalisePage. Use os tokens entre `{{ }}` para integrar com a camada de dados (Supabase + Claude API). A hierarquia de componentes está na ordem de renderização de cima para baixo.

---

## 1. HEADER DA PÁGINA

### Breadcrumb
```
Dashboard > Análises > {{ nome_empresa || "Minha Empresa" }}
```

### Título Principal
```
Análise do DRE — {{ mes_referencia_extenso }} de {{ ano_referencia }}
```

### Subtítulo (mostrar só quando análise existir)
```
Gerado em {{ data_geracao }} às {{ hora_geracao }} • Modelo: Sofia IA v2
```

### Pill de status — lógica condicional:
| Estado | Componente | Cor |
|---|---|---|
| Análise pronta | `✅ Análise concluída` | Verde |
| Processando | `⏳ Analisando seu DRE...` | Amarelo |
| Erro / falha | `⚠️ Análise incompleta` | Vermelho |
| Sem DRE | `📄 Nenhum DRE enviado ainda` | Cinza |

---

## 2. CARD DE DIAGNÓSTICO GERAL (topo, destaque)

### Label
```
Diagnóstico Geral
```

### Nota Sofia (output da IA — renderizar dentro de um card com borda esquerda colorida)
```
{{ diagnostico_geral_ia }}
```

*Token: string gerada pela Claude API. Exemplo de output esperado:*
> "Seu DRE de maio mostra um negócio saudável, mas com um sinal de atenção: a margem bruta caiu 4 pontos percentuais em relação a abril. Isso geralmente indica aumento de custos diretos ou desconto excessivo nas vendas. Antes de qualquer decisão, veja os detalhes abaixo."

### Estado vazio (sem análise ainda):
```
Título: "Sofia ainda não analisou este período"
Corpo: "Faça o upload do DRE deste mês para receber o diagnóstico completo em segundos."
CTA: [Enviar DRE agora →]
```

---

## 3. BLOCO DE INDICADORES — 4 CARDS

Exibir em grid 2×2 (mobile: coluna única).

### Card 1 — Receita Bruta
```
Label: "Receita Bruta"
Valor: R$ {{ receita_bruta | format_currency }}
Variação: {{ variacao_receita_bruta }}% vs. mês anterior
  → Se positiva: seta ↑ verde + "R$ {{ delta }} a mais"
  → Se negativa: seta ↓ vermelha + "R$ {{ delta }} a menos"
Tooltip: "Total das vendas antes de devoluções, impostos e descontos."
```

### Card 2 — Margem Bruta
```
Label: "Margem Bruta"
Valor: {{ margem_bruta_pct }}%
Sub-valor: R$ {{ margem_bruta_valor | format_currency }}
Variação: {{ variacao_margem_bruta }}% vs. mês anterior
Tooltip: "Quanto sobra das vendas depois de pagar o custo direto do produto ou serviço (CMV)."
Alerta condicional:
  → Se margem < 30%: ⚠️ "Margem abaixo do ideal para seu segmento."
  → Se margem < 15%: 🔴 "Margem crítica. Revisar precificação com urgência."
```

### Card 3 — Resultado Operacional (EBIT)
```
Label: "Resultado Operacional"
Valor: R$ {{ resultado_operacional | format_currency }}
Variação: {{ variacao_resultado_op }}% vs. mês anterior
Tooltip: "Lucro da operação antes de impostos e receitas/despesas financeiras. É o número que mostra se o negócio é rentável por si mesmo."
Alerta condicional:
  → Se negativo: 🔴 "Operação no prejuízo. Sofia preparou uma análise de causas abaixo."
```

### Card 4 — Lucro Líquido
```
Label: "Lucro Líquido"
Valor: R$ {{ lucro_liquido | format_currency }}
Margem líquida: {{ margem_liquida_pct }}%
Variação: {{ variacao_lucro_liquido }}% vs. mês anterior
Tooltip: "O que sobra para o dono depois de pagar tudo: custos, despesas, impostos e despesas financeiras."
Destaque especial:
  → Se lucro > 0: card com fundo verde-claro
  → Se lucro < 0: card com fundo vermelho-claro + ícone de alerta
```

---

## 4. ANÁLISE DETALHADA DA SOFIA (seção longa — acordeão por categoria)

### Título da seção:
```
O que a Sofia encontrou no seu DRE
```

### Subtítulo:
```
Análise completa em linguagem simples — sem jargão contábil
```

---

### Acordeão 1 — Receitas

**Header do acordeão:**
```
📈 Receitas — {{ receita_bruta | format_currency }} bruta / {{ receita_liquida | format_currency }} líquida
```

**Conteúdo (output da IA):**
```
{{ analise_receitas_ia }}
```

*Output esperado da Sofia:*
> "Sua receita bruta de R$ 87.400 foi R$ 12.000 maior que o mês passado — ótimo sinal. Mas atenção: a receita líquida ficou em R$ 71.200. Isso significa que R$ 16.200 (18,5%) foram para devoluções, descontos e impostos sobre venda. Se esse percentual está crescendo, pode ser sinal de desconto excessivo ou aumento da carga tributária."

---

### Acordeão 2 — Custos (CMV/CPV)

**Header:**
```
🏭 Custo das Mercadorias / Serviços — {{ cmv_valor | format_currency }} ({{ cmv_pct }}% da receita)
```

**Conteúdo (output da IA):**
```
{{ analise_cmv_ia }}
```

**Alerta condicional no header:**
```
→ Se CMV > 60% da receita: chip vermelho "⚠️ CMV alto"
→ Se CMV entre 40-60%: chip amarelo "Atenção"
→ Se CMV < 40%: chip verde "Saudável"
```

---

### Acordeão 3 — Despesas Operacionais

**Header:**
```
💼 Despesas Operacionais — {{ despesas_op_valor | format_currency }} ({{ despesas_op_pct }}% da receita)
```

**Tabela de despesas (renderizar automaticamente a partir do DRE):**
```
| Categoria | Valor | % da Receita | Variação |
|---|---|---|---|
| {{ categoria_1 }} | R$ {{ valor_1 }} | {{ pct_1 }}% | {{ var_1 }}% |
| ... | ... | ... | ... |
```

**Conteúdo (output da IA):**
```
{{ analise_despesas_ia }}
```

---

### Acordeão 4 — Resultado Financeiro

**Header:**
```
🏦 Resultado Financeiro — {{ resultado_financeiro | format_currency }}
```

**Conteúdo (output da IA):**
```
{{ analise_financeiro_ia }}
```

**Alerta específico — se resultado financeiro negativo:**
```
💡 "Despesas financeiras altas geralmente indicam dívida cara ou capital de giro financiado por cheque especial. Sofia preparou sugestões abaixo."
```

---

## 5. RECOMENDAÇÕES DA SOFIA (3 ações prioritárias)

### Título:
```
O que fazer agora
```

### Subtítulo:
```
Sofia identificou 3 ações prioritárias para este mês
```

### Cards de recomendação (renderizar 3):
```
[ícone] Ação {{ n }}
{{ titulo_recomendacao_n }}
{{ corpo_recomendacao_n }}
Prioridade: {{ prioridade_n }} — [Alta / Média / Baixa]
```

*Token: `{{ recomendacoes_ia }}` — array com 3 objetos `{ icon, titulo, corpo, prioridade }`*

*Exemplo de output esperado da Sofia:*
```json
[
  {
    "icon": "💰",
    "titulo": "Revise o preço dos 3 produtos com menor margem",
    "corpo": "Seus produtos A, B e C representam 40% do faturamento mas contribuem com apenas 12% da margem. Um aumento de 8% nesses produtos poderia adicionar R$ 6.200 de margem sem perder volume.",
    "prioridade": "Alta"
  },
  {
    "icon": "📦",
    "titulo": "Negocie prazo maior com fornecedores",
    "corpo": "Seu ciclo de caixa está negativo em 12 dias — você paga fornecedor antes de receber do cliente. Aumentar o prazo de pagamento de 30 para 45 dias resolveria esse descasamento.",
    "prioridade": "Alta"
  },
  {
    "icon": "📉",
    "titulo": "Corte ou renegocie as despesas de marketing",
    "corpo": "Suas despesas de marketing cresceram 34% vs. mês anterior enquanto a receita cresceu apenas 14%. Avalie o ROI canal por canal antes do próximo mês.",
    "prioridade": "Média"
  }
]
```

---

## 6. COMPARATIVO — SÉRIE HISTÓRICA (gráfico)

### Título:
```
Evolução dos últimos {{ n_meses }} meses
```

### Gráfico de linha — 3 séries:
- Receita Bruta (azul)
- Margem Bruta (verde)
- Lucro Líquido (roxo)

**Token:** `{{ historico_meses }}` — array de objetos `{ mes, receita_bruta, margem_bruta, lucro_liquido }`

**Estado vazio (menos de 2 meses de dados):**
```
Título: "Ainda pouco histórico"
Corpo: "Envie DREs de mais meses para ver a evolução do negócio no tempo. Quanto mais meses, mais precisa fica a análise da Sofia."
CTA: [Enviar DRE de outro mês →]
```

---

## 7. CHAT SOFIA (botão flutuante / painel lateral)

### Botão flutuante (canto inferior direito):
```
[💬 Pergunte à Sofia]
```

### Mensagem de abertura do chat (contextual — usar dados da análise):
```
"Olá! Analisei o DRE de {{ mes_referencia }}. 
Tenho 3 pontos importantes para conversar com você.
O que você quer entender primeiro?"

Sugestões rápidas:
• [Por que a margem caiu?]
• [Como cortar custos sem demitir?]
• [O negócio está saudável?]
• [Quanto posso reinvestir agora?]
```

### Estado sem análise (chat bloqueado):
```
"Envie o DRE primeiro para eu poder responder com precisão sobre os números da sua empresa."
[Enviar DRE →]
```

---

## 8. EXPORTAÇÃO E AÇÕES

### Barra de ações (topo direito da página):
```
[📥 Baixar PDF] [📤 Compartilhar] [🔄 Reanalisar] [📅 Enviar novo DRE]
```

**Microcopy do botão "Reanalisar":**
```
Tooltip: "Gera uma nova análise com os mesmos dados. Útil se você atualizou o DRE."
```

**Modal de compartilhamento:**
```
Título: "Compartilhar análise"
Corpo: "Gere um link temporário (válido por 7 dias) para compartilhar este relatório com seu contador ou sócio."
[Gerar link] [Cancelar]
```

---

## 9. ESTADOS DE LOADING / ERRO

### Loading (processamento em curso):
```
[Spinner]
"Sofia está analisando seu DRE..."
"Isso leva menos de 30 segundos."

Mensagens rotativas durante o loading:
• "Lendo as linhas do DRE..."
• "Calculando margem bruta e operacional..."
• "Identificando pontos de atenção..."
• "Preparando recomendações personalizadas..."
```

### Erro de processamento:
```
Ícone: ⚠️
Título: "Não consegui ler este DRE"
Corpo: "O arquivo pode estar com formatação incomum. Tente converter para PDF ou copie os dados para nossa planilha modelo."
CTAs: [Tentar novamente] [Baixar planilha modelo] [Falar com suporte]
```

### Erro de arquivo:
```
Título: "Formato não suportado"
Corpo: "Aceitamos PDF, Excel (.xlsx) e CSV. Seu arquivo está em outro formato?"
CTA: [Enviar outro arquivo]
```

---

## 10. BLOQUEIO DE PLANO (upsell in-page)

### Para usuários Gratuito tentando acessar análise detalhada:
```
[Ícone cadeado]
Título: "Análise completa disponível no plano Pro"
Corpo: "Você está vendo um resumo. Com o Pro você acessa a análise linha por linha, as 3 recomendações da Sofia, o histórico de 12 meses e o chat ilimitado."

Card de comparação rápida:
Gratuito (seu plano): ✅ Diagnóstico geral | ❌ Análise detalhada | ❌ Recomendações | ❌ Histórico
Pro R$97/mês: ✅ Tudo do Gratuito | ✅ Análise linha por linha | ✅ 3 recomendações/mês | ✅ Histórico 12 meses | ✅ Chat ilimitado

CTA: [Quero análise completa — R$97/mês]
Link secundário: "Ver todos os planos"
```

---

## 11. EMPTY STATE GERAL (nenhum DRE enviado)

```
[Ilustração — documento com lupa]

Título: "Sua primeira análise está a 1 upload de distância"
Corpo: "Envie o DRE do mês passado e a Sofia entrega um diagnóstico completo em menos de 30 segundos. Sem contador. Sem planilha. Em português simples."

O que você vai receber:
✅ Diagnóstico geral do negócio
✅ 4 indicadores principais com variação
✅ Análise da Sofia em linguagem simples
✅ 3 ações prioritárias para o próximo mês

CTA principal: [📄 Enviar meu primeiro DRE]
Link secundário: "Ver exemplo de análise"
```

---

## TOKENS DE INTEGRAÇÃO — RESUMO

```javascript
// Dados do DRE processado
const analiseData = {
  // Meta
  mes_referencia: "maio",
  mes_referencia_extenso: "Maio",
  ano_referencia: 2026,
  data_geracao: "16/06/2026",
  hora_geracao: "19:42",
  nome_empresa: "Empresa ABC Ltda",
  
  // Indicadores
  receita_bruta: 87400,
  receita_liquida: 71200,
  cmv_valor: 32000,
  cmv_pct: 36.6,
  margem_bruta_valor: 39200,
  margem_bruta_pct: 44.9,
  despesas_op_valor: 28000,
  despesas_op_pct: 32.0,
  resultado_operacional: 11200,
  resultado_financeiro: -2100,
  lucro_liquido: 9100,
  margem_liquida_pct: 10.4,
  
  // Variações (vs. mês anterior)
  variacao_receita_bruta: 15.9,
  variacao_margem_bruta: -4.1,
  variacao_resultado_op: 8.2,
  variacao_lucro_liquido: 6.7,
  
  // Outputs da IA (string gerada pela Claude API)
  diagnostico_geral_ia: "...",
  analise_receitas_ia: "...",
  analise_cmv_ia: "...",
  analise_despesas_ia: "...",
  analise_financeiro_ia: "...",
  recomendacoes_ia: [...],
  
  // Histórico
  historico_meses: [...]
}
```

---

*Prioridade de implementação:*
1. Indicadores (4 cards) + Diagnóstico Geral
2. Chat Sofia flutuante
3. Acordeões de análise detalhada
4. Gráfico histórico
5. Estados de loading/erro
6. Bloco de upsell

*Esta AnalisePage + DashboardPage (pronta em `outputs/2026-06-14/pagina-vendas-secao.md`) são os 2 gargalos críticos para o lançamento.*
