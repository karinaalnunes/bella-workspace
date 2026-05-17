# Página de Vendas — Seção: Onboarding Flow / Copy do Primeiro Acesso
*Produzido por Bella | Turno da Noite | 17/05/2026*

---

## CONTEXTO DE USO

Esta seção cobre o copy in-app para o **fluxo de ativação do novo usuário** — desde o cadastro até a primeira análise de DRE entregue com sucesso. É o momento em que o usuário decide se fica ou abandona o produto.

Inclui: tela de boas-vindas, onboarding de 3 etapas, tooltips, tela de upload, estado de loading da IA e primeira entrega do diagnóstico.

---

## TELA 1 — BOAS-VINDAS (pós-cadastro)

### Headline
> Bem-vindo(a) à Máxima Finance IA.
> Seu diagnóstico financeiro começa agora.

### Subtítulo
> Em menos de 2 minutos, você vai entender o que o seu DRE está dizendo — em português simples, sem planilha, sem contador.

### CTA principal
> **Começar minha análise →**

### CTA secundário (link texto)
> Ver tour rápido primeiro

---

## TELA 2 — ONBOARDING (3 etapas visuais)

### Passo 1
**Ícone:** upload de arquivo
**Título:** Faça o upload do seu DRE
**Descrição:** PDF, Excel ou planilha — qualquer formato. Se não tiver, a Sofia te ajuda a montar do zero.

### Passo 2
**Ícone:** IA/análise
**Título:** A IA analisa tudo
**Descrição:** Em segundos, identificamos receita, margem, custos e riscos que passam despercebidos.

### Passo 3
**Ícone:** diagnóstico/relatório
**Título:** Você recebe o diagnóstico
**Descrição:** Em linguagem simples. Com o que está bom, o que precisa de atenção e o que fazer primeiro.

### CTA
> **Entendido. Fazer upload agora →**

---

## TELA 3 — UPLOAD DE DRE

### Headline (acima da área de upload)
> Seu DRE pode estar escondendo oportunidades — ou alertas.
> Vamos descobrir juntos.

### Instrução primária
> Arraste o arquivo aqui ou clique para selecionar

### Formatos aceitos (sub-label)
> Aceita: PDF, .xlsx, .xls, .csv
> Tamanho máximo: 10 MB

### Tooltip (hover no ícone de dúvida)
> **O que é o DRE?**
> DRE (Demonstração do Resultado do Exercício) é o relatório que mostra se sua empresa lucrou ou teve prejuízo em um período. Seu contador gera mensalmente. Se não tiver, fale com a Sofia — ela te ajuda a montar.

### Estado sem arquivo
> **Ainda não tem o DRE?**
> [Falar com a Sofia →] (abre chat)

### Aviso de privacidade (rodapé da área)
> 🔒 Seus dados são criptografados e nunca compartilhados. Só você vê a análise.

### CTA (após arquivo carregado)
> **Analisar meu DRE agora →**

---

## TELA 4 — LOADING / ANÁLISE EM PROGRESSO

### Headline animada (rotaciona a cada 3s)
1. "Lendo sua receita bruta e líquida…"
2. "Calculando sua margem de contribuição…"
3. "Identificando os maiores custos…"
4. "Verificando alertas de rentabilidade…"
5. "Montando seu diagnóstico…"

### Sub-linha (fixa)
> Sofia está analisando seu DRE. Isso leva menos de 30 segundos.

### Micro-copy motivacional (abaixo do loading)
> Empresários que leem o DRE todo mês aumentam a margem em média 8 pontos percentuais em 6 meses.
> *Você já está no caminho certo.*

---

## TELA 5 — DIAGNÓSTICO PRONTO (primeira entrega)

### Headline
> Seu diagnóstico está pronto, [Nome].

### Subtítulo dinâmico (baseado no resultado)

**Variante A — resultado positivo:**
> Boas notícias: sua margem bruta está acima da média do setor. Mas encontrei 2 pontos de atenção que merecem seu olhar hoje.

**Variante B — resultado de alerta:**
> Encontrei 3 alertas importantes no seu DRE. A boa notícia: todos são corrigíveis — e agora você sabe onde agir.

**Variante C — resultado crítico:**
> Seu DRE mostra sinais de pressão financeira. Não é pânico — é diagnóstico. Veja o que está acontecendo e o que fazer primeiro.

### Bloco de indicadores (cards resumo)
```
┌─────────────────────────────────────────┐
│  📊 RECEITA BRUTA         R$ [valor]    │
│  ✅ Dentro do esperado                  │
├─────────────────────────────────────────┤
│  📉 MARGEM BRUTA            [X]%        │
│  ⚠️ Abaixo do ideal para o setor        │
├─────────────────────────────────────────┤
│  💸 MAIORES CUSTOS         [item 1]     │
│  ⚠️ Representa [Y]% da receita          │
├─────────────────────────────────────────┤
│  🔴 LUCRO LÍQUIDO           [Z]%        │
│  🚨 Atenção: margem abaixo de 5%        │
└─────────────────────────────────────────┘
```

### Destaque do diagnóstico (bloco principal)
> **O que a Sofia encontrou:**
> [Parágrafo em linguagem simples — gerado pela IA com base no DRE]

### CTA primário
> **Ver diagnóstico completo →**

### CTA secundário
> **Perguntar para a Sofia sobre esse resultado →** (abre chat com contexto do DRE carregado)

### Nudge de upgrade (apenas para plano Gratuito)
> 💡 *No plano Pro, você desbloqueia: comparativo mês a mês, análise de tendência e alertas automáticos toda vez que o DRE mudar.*
> [Quero o Pro por R$97/mês →]

---

## TOOLTIPS DO DASHBOARD (Onboarding Hotspots)

Exibidos na primeira visita ao Dashboard, em sequência.

**Hotspot 1 — Widget Receita do Mês**
> Este é o seu faturamento bruto do período. Compare com o mês anterior para ver se está crescendo.

**Hotspot 2 — Widget Margem Bruta**
> A margem bruta mostra quanto sobra depois de descontar o custo do produto ou serviço. Abaixo de 30% é sinal de alerta.

**Hotspot 3 — Widget Alerta DRE**
> Quando o DRE tiver um alerta, aparece aqui com a ação recomendada. Você nunca vai ser pego de surpresa.

**Hotspot 4 — Botão Sofia**
> Tem dúvida sobre qualquer número? Fale com a Sofia. Ela explica em português, sem enrolação.

**Hotspot 5 — Botão Nova Análise**
> Todo mês, faça upload do DRE atualizado. A Sofia compara com o anterior e mostra o que mudou.

### Botão final dos hotspots
> **Entendi, quero explorar →**

---

## EMPTY STATE — Dashboard sem DRE

*(Quando o usuário acessa o Dashboard sem ter feito nenhum upload)*

### Ícone
📊 (gráfico vazio, cinza)

### Título
> Seu painel está esperando pelo primeiro DRE.

### Descrição
> Faça o upload do seu DRE e em segundos você vai ter um diagnóstico financeiro completo — sem precisar entender de contabilidade.

### CTA
> **Fazer meu primeiro upload →**

### Link alternativo
> Ainda não tenho o DRE — [falar com a Sofia]

---

## COPY PARA NOTIFICAÇÕES IN-APP

### Notificação 1 — DRE analisado com sucesso
> ✅ **Análise concluída!** Seu DRE de [mês/ano] está pronto. [Ver diagnóstico →]

### Notificação 2 — Lembrete mensal
> 📅 **Já chegou o DRE de [mês]?** Quanto antes você fizer o upload, mais cedo sabe como foi o mês. [Fazer upload →]

### Notificação 3 — Margem em queda (alerta automático)
> 🚨 **Alerta:** sua margem bruta caiu [X]% vs. o mês anterior. A Sofia já identificou os motivos. [Ver agora →]

### Notificação 4 — Nudge de upgrade (Gratuito)
> 💡 **Desbloqueie o comparativo mensal.** Com o Pro, você vê a evolução de todos os indicadores mês a mês. [Conhecer o Pro →]

---

## TOKENS PARA DEV

```
// Variáveis dinâmicas para implementar
{userName}         → nome do usuário logado
{dreMonth}         → mês/ano do DRE analisado
{receitaBruta}     → valor da receita bruta formatado (R$ X.XXX)
{margemBruta}      → percentual da margem bruta
{lucroLiquido}     → percentual do lucro líquido
{topCusto}         → maior item de custo identificado
{alertCount}       → número de alertas encontrados
{diagnosticoText}  → parágrafo gerado pela IA (Sofia)
{planType}         → "gratuito" | "pro" | "business"
```

---

## NOTAS DE IMPLEMENTAÇÃO

- **Tela de Loading:** usar Framer Motion ou CSS keyframes. Textos rotativos a cada 3s. NÃO mostrar barra de progresso (gera ansiedade). Manter animação até análise concluída.
- **Diagnóstico pronto:** variante de subtítulo baseada no `lucroLiquido`: ≥15% = Variante A, 5–14% = Variante B, <5% = Variante C.
- **Hotspots:** biblioteca recomendada: Intro.js ou Shepherd.js. Salvar estado `onboarding_completed` no Supabase para não repetir.
- **Nudge upgrade:** exibir apenas se `planType === "gratuito"` e após a primeira análise concluída.
- **Empty state:** exibir quando `dreuploads.count === 0` para o usuário logado.

---

*Bella — Turno da Noite — 17/05/2026*
