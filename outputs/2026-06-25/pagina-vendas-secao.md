# Página de Vendas — Copy de Onboarding In-App
## Empty States + Tooltips + Primeiro Uso + Nudges de Ativação
*Entregue por Bella — Turno da noite 25/06/2026*

---

## CONTEXTO

Esta seção suporta diretamente a implementação da **DashboardPage** e **AnalisePage** (gargalo crítico do lançamento). São os textos que o usuário vê desde o momento em que faz login pela primeira vez até completar a primeira análise de DRE. Cada palavra aqui impacta a taxa de ativação.

**Arquivo de destino no código:** copiar os tokens diretamente para `src/pages/DashboardPage.tsx` e `src/pages/AnalisePage.tsx`.

---

## 1. EMPTY STATE — DASHBOARD (Primeiro Login)

*Situação: usuário acabou de criar a conta. Nenhum DRE foi enviado ainda.*

```
// components/EmptyDashboard.tsx

HEADLINE:
"Seu painel está esperando o primeiro DRE"

SUBTÍTULO:
"Em menos de 3 minutos você vai saber exatamente onde está o lucro — e onde está indo embora."

CTA PRIMÁRIO:
"Enviar meu primeiro DRE →"

LINK SECUNDÁRIO:
"Ver exemplo de análise" [abre modal com análise demonstrativa]

ÍCONE/ILUSTRAÇÃO: gráfico vazio com linha pontilhada subindo
```

---

## 2. TELA DE UPLOAD — ANTECIPAÇÃO DE VALOR

*Situação: usuário clica em "Enviar DRE". Aparece a tela de upload.*

```
// components/UploadDRE.tsx

TÍTULO:
"Envie o DRE da sua empresa"

INSTRUÇÃO CURTA:
"Formatos aceitos: PDF, Excel (.xlsx) ou CSV. Pode ser o relatório do seu contador — exatamente como ele te enviou."

PLACEHOLDER DA ÁREA DE DRAG-AND-DROP:
"Arraste o arquivo aqui ou clique para selecionar"

MICRO-COPY ABAIXO DO BOTÃO:
"Suas informações são criptografadas e nunca compartilhadas. Só você vê seus dados."

TOOLTIP (ícone de interrogação ao lado de "DRE"):
"DRE = Demonstração do Resultado do Exercício. É o relatório que mostra quanto sua empresa faturou, quais foram os custos e quanto sobrou de lucro em um período. Se não sabe o que é, não se preocupe — a Sofia explica tudo depois da análise."
```

---

## 3. LOADING STATE — ANÁLISE EM ANDAMENTO

*Situação: DRE foi enviado. IA está processando. Dura 10–30 segundos.*

```
// components/AnalysisLoading.tsx

MENSAGEM PRINCIPAL (rotaciona a cada 5s):
① "Lendo seu DRE..."
② "Calculando sua margem bruta real..."
③ "Identificando os principais custos..."
④ "Comparando com benchmarks do setor..."
⑤ "Preparando seu diagnóstico em linguagem simples..."

MICRO-COPY ABAIXO DO SPINNER:
"A Sofia está transformando números em decisões. Já já."

TEMPO ESTIMADO:
"Isso leva menos de 30 segundos."
```

---

## 4. EMPTY STATE — ANÁLISE PRONTA (Primeiro Resultado)

*Situação: análise concluída. Usuário vê o resultado pela primeira vez.*

```
// components/AnalysisComplete.tsx

BANNER DE BOAS-VINDAS (aparece uma única vez — primeiro uso):
"✅ Seu primeiro diagnóstico está pronto"

HEADLINE DO DIAGNÓSTICO:
"Aqui está o que o DRE da [NOME_EMPRESA] revela sobre [MÊS/ANO]"

CTA PARA CHAT SOFIA:
"Agora pergunte qualquer coisa para a Sofia →"

EXEMPLO DE PERGUNTAS SUGERIDAS (chips clicáveis abaixo do CTA):
- "Qual foi minha margem de lucro real?"
- "Quais são meus maiores custos?"
- "Estou crescendo ou regredindo?"
- "O que precisa melhorar primeiro?"
```

---

## 5. TOOLTIP PROGRESSIVO — DASHBOARD PÓS-PRIMEIRA ANÁLISE

*Situação: usuário está navegando no Dashboard pela primeira vez com dados.*

```
// Tooltip Sequence (tour guiado — aparece uma vez, pode ser dispensado)

TOOLTIP #1 — Card Receita Bruta:
"Este é o total que sua empresa faturou no período. Mas atenção: faturamento não é lucro."

TOOLTIP #2 — Card Margem Bruta:
"Depois de descontar o custo direto do que você vendeu, quanto sobrou? Abaixo de 30%? Precisa conversar com a Sofia."

TOOLTIP #3 — Card Lucro Líquido:
"O que realmente ficou no bolso depois de pagar tudo — impostos, salários, custos fixos. Este é o número que importa."

TOOLTIP #4 — Chat Sofia:
"Tem dúvida sobre qualquer número aqui? É só perguntar para a Sofia em português mesmo. Ela não julga e não cobra extra."

BOTÃO SKIP DO TOUR:
"Entendi, pode fechar o guia"
```

---

## 6. NUDGE DE ATIVAÇÃO — E-MAIL "DIA 1"

*Situação: usuário criou conta mas ainda não enviou o primeiro DRE. Dispara 24h após o cadastro.*

**Assunto:** `Seu painel está esperando, [NOME]`
**Pré-header:** `Menos de 3 minutos para o seu primeiro diagnóstico`

```
Oi, [NOME]!

Ontem você criou sua conta no Máxima Finance.

Mas seu DRE ainda não chegou por aqui.

E é exatamente esse arquivo — que provavelmente está na sua caixa de entrada em algum e-mail do contador — que vai revelar onde está indo o seu dinheiro.

Uma análise. Menos de 3 minutos. Em português.

[BOTÃO: "Enviar meu DRE agora →"]

Se quiser, eu posso te mostrar um exemplo de análise antes de você enviar o seu.

[LINK: "Ver análise de exemplo"]

Até mais,
Sofia — sua analista financeira com IA

---
Máxima Finance IA | maximafinance.com.br
Para cancelar: [unsubscribe]
```

---

## 7. NUDGE DE REATIVAÇÃO — PUSH NOTIFICATION "DIA 3"

*Situação: usuário fez upload do DRE mas não voltou ao app. Dispara 72h após a última análise.*

```
// Push notification / SMS

TÍTULO: "Sofia tem algo para te mostrar"
CORPO: "Você não voltou desde [DATA]. Tem 1 insight novo sobre sua margem te esperando."
CTA: "Ver agora →" [deeplink para DashboardPage]
```

---

## 8. MODAL DE UPSELL — GRATUITO → PRO

*Situação: usuário gratuito tentou acessar recurso bloqueado (ex: análise histórica, relatório completo).*

```
// components/UpgradeModal.tsx

HEADLINE:
"Esse recurso está no plano Pro"

BENEFÍCIO IMEDIATO:
"Com o Pro você vê análises de até 12 meses, compara semestres e recebe alertas automáticos quando algo muda no seu resultado."

ÂNCORA DE PREÇO:
"Por R$ 97/mês — menos de R$ 3,24 por dia."

COMPARAÇÃO RÁPIDA:
"Uma consultoria financeira cobra R$ 500/hora. A Sofia está disponível 24h por dia."

CTA PRIMÁRIO:
"Quero o Pro agora →"

CTA SECUNDÁRIO:
"Continuar no plano gratuito"

GATILHO DE URGÊNCIA (se coupon ativo):
"🔖 Use REVISAO_SEMESTRAL_JUNHO e ganhe [X]% de desconto — expira em [DIAS] dias."
```

---

## TOKENS DE IMPLEMENTAÇÃO — VARIÁVEIS DE AMBIENTE

```javascript
// constants/onboarding.ts

export const ONBOARDING_COPY = {
  emptyDashboard: {
    headline: "Seu painel está esperando o primeiro DRE",
    subtitle: "Em menos de 3 minutos você vai saber exatamente onde está o lucro — e onde está indo embora.",
    ctaPrimary: "Enviar meu primeiro DRE →",
    ctaSecondary: "Ver exemplo de análise",
  },
  uploadScreen: {
    title: "Envie o DRE da sua empresa",
    instruction: "Formatos aceitos: PDF, Excel (.xlsx) ou CSV.",
    dragDropPlaceholder: "Arraste o arquivo aqui ou clique para selecionar",
    securityNote: "Suas informações são criptografadas e nunca compartilhadas.",
  },
  loadingMessages: [
    "Lendo seu DRE...",
    "Calculando sua margem bruta real...",
    "Identificando os principais custos...",
    "Comparando com benchmarks do setor...",
    "Preparando seu diagnóstico em linguagem simples...",
  ],
  analysisComplete: {
    banner: "✅ Seu primeiro diagnóstico está pronto",
    suggestedQuestions: [
      "Qual foi minha margem de lucro real?",
      "Quais são meus maiores custos?",
      "Estou crescendo ou regredindo?",
      "O que precisa melhorar primeiro?",
    ],
  },
  upgradeModal: {
    headline: "Esse recurso está no plano Pro",
    benefit: "Análises de até 12 meses, comparação de semestres e alertas automáticos.",
    priceAnchor: "Por R$ 97/mês — menos de R$ 3,24 por dia.",
    ctaPrimary: "Quero o Pro agora →",
    ctaSecondary: "Continuar no plano gratuito",
  },
}
```

---

## PRIORIDADE DE IMPLEMENTAÇÃO

| Componente | Impacto | Esforço | Prioridade |
|---|---|---|---|
| EmptyState Dashboard | 🔥 Crítico (ativação) | Baixo | **1** |
| Loading messages | Alto (engajamento) | Baixo | **2** |
| Suggested questions (chips) | Alto (retenção) | Baixo | **3** |
| Tooltip tour | Médio (onboarding) | Médio | **4** |
| Upgrade modal | Alto (receita) | Médio | **5** |
| E-mail D+1 | Alto (ativação) | Baixo | **6** |

---

*Total de copy: 8 componentes prontos para implementação imediata.*
*Estimativa de implementação: 3–4h para todos os componentes.*
