# Copy para DashboardPage — Widgets, Mensagens Vazias, Tooltips e Alertas do DRE
*Máxima Finance IA — Turno da noite 14/06/2026*
*Seção: UX Copy completo para implementação imediata no DashboardPage*

---

## POR QUE ESTA SEÇÃO AGORA

O DashboardPage é o maior gargalo para o deploy. Esta entrega dá ao dev todo o copy pronto para implementar os 3 widgets MVP + estados vazios + tooltips + alertas — sem precisar inventar texto na hora. Copiar e colar.

---

## 1. HEADER / SAUDAÇÃO DINÂMICA

```
Bom dia, [primeiro_nome] 👋
Seu DRE de [mês/ano] está disponível. Veja o que os números dizem sobre sua empresa.
```

```
Boa tarde, [primeiro_nome] 👋
Continue de onde parou. Seus indicadores do mês estão atualizados.
```

```
Boa noite, [primeiro_nome] 👋
Feche o dia sabendo como está a saúde financeira da sua empresa.
```

**Variante — sem DRE carregado:**
```
Olá, [primeiro_nome]! Para começar, faça o upload do seu DRE.
Leva menos de 2 minutos e a Sofia já explica tudo pra você.
```

---

## 2. WIDGET 1 — RECEITA DO MÊS

### Label
```
Receita do Mês
```

### Valor principal
```
R$ [valor]
```

### Subtexto comparativo
```
↑ +12% em relação ao mês anterior
```
```
↓ –8% em relação ao mês anterior
```
```
→ Igual ao mês anterior
```

### Tooltip (ícone ?)
```
Receita do mês = total das vendas (Receita Bruta) que sua empresa registrou no DRE do período selecionado. 
Atenção: receita não é o dinheiro no banco. É o que foi gerado — recebido ou a receber.
```

### Estado vazio
```
📋 Nenhum DRE carregado ainda.
Faça o upload do seu extrato ou DRE para ver a receita do mês.
[Botão: Carregar DRE]
```

---

## 3. WIDGET 2 — MARGEM BRUTA %

### Label
```
Margem Bruta
```

### Valor principal
```
[XX]%
```

### Subtexto semáforo
**Verde (acima de 40%):**
```
Margem saudável para o seu segmento. Continue monitorando.
```

**Amarelo (25% a 40%):**
```
Atenção: margem abaixo do ideal. Revise seus custos diretos.
```

**Vermelho (abaixo de 25%):**
```
Alerta: margem crítica. Fale com a Sofia sobre o que está pesando nos seus custos.
[Botão: Falar com a Sofia]
```

### Tooltip (ícone ?)
```
Margem Bruta = (Receita – Custos Diretos) ÷ Receita × 100.
Indica quanto sobra de cada R$1 vendido antes das despesas fixas.
Referência: varejo ~30–40%, serviços ~50–70%, indústria ~25–40%.
```

### Estado vazio
```
📊 Sua margem bruta aparece aqui após o upload do DRE.
[Botão: Carregar DRE]
```

---

## 4. WIDGET 3 — ALERTA DRE PENDENTE

### Label
```
Status do Diagnóstico
```

### Estado: DRE analisado (positivo)
```
✅ Diagnóstico concluído
Análise de [mês/ano] pronta. Veja os insights completos.
[Botão: Ver análise]
```

### Estado: DRE pendente há menos de 7 dias
```
⏳ Aguardando DRE de [mês/ano]
Você ainda não carregou o resultado deste mês.
[Botão: Carregar agora]
```

### Estado: DRE pendente há mais de 7 dias (urgência)
```
⚠️ [X] dias sem análise
Empresas que monitoram o DRE mensalmente tomam decisões 3× mais rápido.
[Botão: Carregar DRE agora]
```

### Estado: DRE em processamento
```
🔄 Analisando seu DRE...
A Sofia está interpretando os números. Isso leva alguns segundos.
```

### Tooltip (ícone ?)
```
O diagnóstico é gerado automaticamente quando você faz o upload do DRE.
A Sofia interpreta os números e entrega um relatório em linguagem simples.
```

---

## 5. MENSAGENS DE ESTADO VAZIO — TELA INICIAL SEM DRE

### Versão curta (widget pequeno)
```
Nenhum dado ainda.
Carregue seu DRE para começar.
```

### Versão completa (primeiro acesso)
```
Bem-vindo(a) à Máxima Finance IA 🎉

Aqui você vai entender sua empresa de verdade — sem precisar ser contador.

Próximo passo: faça o upload do DRE do seu último mês.
A Sofia analisa tudo e entrega um diagnóstico em menos de 1 minuto.

[Botão primário: Carregar meu primeiro DRE]
[Link: Como funciona?]
```

### Versão reengajamento (usuário inativo >14 dias)
```
Sua empresa mudou desde a última vez. 📈
Carregue o DRE de [mês mais recente] para ver o que mudou.
[Botão: Retomar análise]
```

---

## 6. ALERTAS IN-APP (notificações dentro do dashboard)

### Alerta de margem crítica
```
🔴 Atenção: sua margem bruta caiu para [X]%
Isso pode indicar aumento de custos diretos ou queda no mix de produtos.
Pergunte à Sofia: "O que está pesando na minha margem?"
[Botão: Falar com Sofia]
```

### Alerta de receita em queda
```
📉 Receita de [mês] caiu [X]% em relação a [mês anterior]
Sazonalidade ou perda de clientes? O DRE tem a resposta.
[Botão: Ver análise completa]
```

### Alerta de mês fechando (dia 25–31)
```
📅 [X] dias para fechar [mês]
Você já tem os números do mês para análise? Não deixe para a última hora.
[Botão: Carregar DRE]
```

### Alerta de plano gratuito (upsell suave)
```
🔓 Você está no plano Gratuito
No plano Pro, você acessa análise histórica de 12 meses, comparativo de margens e muito mais.
[Botão: Conhecer o Pro — R$97/mês]
```

---

## 7. TOOLTIPS GLOSSÁRIO — TERMOS DO DRE

*(Para exibir ao passar o mouse sobre termos técnicos na análise)*

```
Receita Bruta
Total das vendas, sem descontar impostos ou devoluções.
```

```
Receita Líquida
Receita Bruta menos impostos sobre vendas, devoluções e abatimentos. 
É o que a empresa efetivamente recebeu de direito.
```

```
CMV / CPV
Custo da Mercadoria Vendida (comércio) ou Custo do Produto Vendido (indústria).
Tudo que foi gasto diretamente para produzir ou comprar o que você vendeu.
```

```
Margem de Contribuição
Receita Líquida – Custos Variáveis.
Quanto cada produto contribui para pagar os custos fixos e gerar lucro.
```

```
EBITDA
Lucro antes de juros, impostos, depreciação e amortização.
É o indicador que bancos e investidores olham para avaliar o potencial operacional.
```

```
Lucro Líquido
O que sobra depois de pagar absolutamente tudo: custos, despesas, impostos e juros.
Esse é o número real. Não o saldo da conta.
```

```
Despesas Fixas
Custos que você paga todo mês independente de vender ou não: aluguel, folha, internet.
```

```
Despesas Variáveis
Custos que aumentam ou diminuem conforme o volume de vendas: comissões, embalagens, frete.
```

---

## 8. MICROCOPY DE BOTÕES E AÇÕES

| Ação | Texto do botão |
|---|---|
| Upload DRE | Carregar DRE |
| Análise completa | Ver diagnóstico completo |
| Chat Sofia | Falar com a Sofia |
| Upgrade plano | Desbloquear Pro |
| Histórico | Ver meses anteriores |
| Exportar | Exportar relatório (PDF) |
| Compartilhar | Enviar para contador |

---

## 9. MENSAGENS DE ERRO (UX)

```
Upload com falha
Não conseguimos ler esse arquivo. Tente um PDF ou Excel (.xlsx) de até 10 MB.
[Botão: Tentar novamente]
```

```
Formato não reconhecido
Esse arquivo não parece um DRE padrão. Se precisar de ajuda, fale com a Sofia.
[Botão: Falar com Sofia] [Link: Ver formatos aceitos]
```

```
Sessão expirada
Sua sessão foi encerrada por segurança. Faça login novamente para continuar.
[Botão: Entrar]
```

---

## TOKENS PARA DEV

```jsx
// Saudação dinâmica
const hora = new Date().getHours();
const saudacao = hora < 12 ? "Bom dia" : hora < 18 ? "Boa tarde" : "Boa noite";

// Semáforo de margem bruta
const margemStatus = (margem) => {
  if (margem >= 40) return { cor: "green", texto: "Margem saudável para o seu segmento." };
  if (margem >= 25) return { cor: "yellow", texto: "Atenção: margem abaixo do ideal." };
  return { cor: "red", texto: "Alerta: margem crítica. Fale com a Sofia." };
};

// Alerta DRE pendente
const diasSemDRE = (ultimaAnalise) => {
  const diff = Math.floor((new Date() - new Date(ultimaAnalise)) / 86400000);
  if (diff <= 0) return "analisado";
  if (diff <= 7) return "pendente";
  return "urgente";
};
```

---

*Próximo passo: dev implementa `<DashboardPage>` usando estes textos diretamente. Zero texto improvisado.*
