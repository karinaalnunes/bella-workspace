# Página de Vendas — Copy para Upgrade Pro → Business
*Produzido por Bella | Turno da Noite | 19/05/2026*

---

## CONTEXTO DE USO

Este é o material de copy para converter assinantes do plano **Pro (R$97/mês)** para o plano **Business (R$297/mês)**.

Pontos de ativação:
- Modal in-app quando usuário tenta analisar o 4º DRE (limite Pro)
- Banner fixo no Dashboard para usuários Pro com mais de 30 dias
- E-mail automático disparado na marca de 60 dias no plano Pro

---

## 1. MODAL IN-APP — TRAVA DE LIMITE

**Acionado quando:** usuário tenta fazer o 4º upload de DRE no mês (limite do Pro é 3)

---

### Cabeçalho do Modal

```
Você chegou ao limite do mês Pro.
```

*Subtítulo:*
```
Sua empresa está crescendo — hora do seu diagnóstico financeiro crescer junto.
```

---

### Corpo do Modal

```
Você já analisou 3 DREs este mês. 🎯

Usuários Business analisam até 10 DREs por mês — e ainda têm acesso a:

✅  Comparativo histórico (até 24 meses de tendência)
✅  Relatório PDF premium com marca d'água da empresa
✅  Análise por centro de custo (até 5 CNPJs)
✅  Suporte prioritário via WhatsApp (resposta em 4h)
✅  Acesso antecipado a novas funcionalidades de IA

A diferença entre Pro e Business não é só volume.
É o nível de decisão que você consegue tomar com os dados.
```

---

### CTA Principal

```
[ Fazer upgrade agora — R$297/mês ]
```

*Microcopy abaixo do botão:*
```
Cancele quando quiser. Sem fidelidade. Sem multa.
```

---

### Link secundário

```
Continuar no plano Pro →  (limite reinicia em X dias)
```

---

## 2. MODAL IN-APP — FEATURE BLOQUEADA

**Acionado quando:** usuário clica em "Comparativo Histórico" ou "Relatório PDF Premium" no Pro

---

### Cabeçalho

```
Essa análise é exclusiva do plano Business.
```

---

### Corpo

```
O comparativo histórico mostra a tendência dos seus indicadores
nos últimos 24 meses — e é exatamente ele que revela
se a sua empresa está evoluindo ou só faturando mais sem lucrar mais.

Essa funcionalidade está disponível no plano Business.

O que você ganha ao fazer o upgrade hoje:

📊  Comparativo histórico — veja a tendência real, não só o mês
📄  PDF com sua marca — leve o relatório para banco, sócio ou investidor
🏢  Multi-CNPJ — analise até 5 empresas no mesmo painel
⚡  Suporte WhatsApp prioritário — sua dúvida respondida em até 4 horas
```

---

### Tabela comparativa rápida

| | Pro | Business |
|---|---|---|
| DREs por mês | 3 | 10 |
| Comparativo histórico | — | 24 meses |
| Relatório PDF premium | — | ✅ |
| Multi-CNPJ | — | até 5 |
| Suporte | E-mail | WhatsApp 4h |
| Preço | R$97/mês | R$297/mês |

---

### CTA

```
[ Quero o Business — R$297/mês ]
```

*Microcopy:*
```
Upgrade imediato. Cobrança proporcional ao ciclo atual.
```

---

### Link secundário

```
Não agora →
```

---

## 3. BANNER FIXO NO DASHBOARD (Pro com +30 dias)

**Localização:** topo do Dashboard, abaixo do header  
**Trigger:** usuário Pro há 30 dias ou mais

---

### Versão A — Benefício Racional

```
💡  Você já analisou [X] DREs com a Máxima.

Usuários Business usam o comparativo histórico para identificar
a sazonalidade do negócio e nunca mais serem pegos de surpresa.

Fazer upgrade → R$297/mês
```

---

### Versão B — Prova Social

```
📈  85% dos usuários que fazem upgrade para Business
tomam a primeira decisão estratégica com dados em menos de 7 dias.

O que eles viram que você ainda não viu?
Fazer upgrade → R$297/mês
```

---

### Versão C — Urgência Suave

```
⏳  Seu próximo DRE vence em [X] dias.

Com o Business, você analisa até 10 DREs por mês —
e ainda compara com os últimos 24 meses para saber se a empresa melhorou de verdade.

Fazer upgrade → R$297/mês
```

*Microcopy:*
```
Cancele quando quiser. Sem fidelidade.
```

---

## 4. E-MAIL DE UPGRADE — ATIVADO AOS 60 DIAS NO PRO

**Assunto:** A pergunta que o seu DRE ainda não consegue responder

**Preview (preheader):** Você analisou X relatórios. Mas o que eles mostram em conjunto?

---

### Corpo do e-mail

```
Olá, [Nome] —

Você já analisou [X] DREs com a Máxima Finance.

Isso é ótimo. Você está no caminho certo.

Mas existe uma pergunta que o plano Pro não consegue responder:

👉 Sua empresa está melhorando de verdade — ou só faturando mais?

Para saber isso, você precisa comparar os números de hoje com os de 3, 6 e 12 meses atrás.
Essa é a análise de tendência. E ela só está disponível no Business.

---

Aqui está o que usuários Business veem que você ainda não vê:

📊  A tendência da margem bruta nos últimos 24 meses
⚠️  Os meses em que o lucro foi mascarado pelo faturamento alto
📄  Relatório PDF com sua marca — para levar ao banco ou apresentar para sócios
🏢  Análise por CNPJ — se você tem mais de uma empresa, tudo no mesmo painel

---

Você não precisa de planilha. Não precisa de contador.
Precisa de um painel que te mostra onde sua empresa está indo.

[ Fazer upgrade para Business — R$297/mês ]

Cobrança proporcional ao ciclo atual. Cancele quando quiser.

Dúvida antes de decidir? Me responda esse e-mail.

Até logo,
**Sofia — Assistente de Análise Financeira**
Máxima Finance IA
```

---

## 5. TOKENS PARA DEV

```jsx
// Gatilhos de Upsell Pro → Business
const UPSELL_TRIGGERS = {
  DRE_LIMIT_REACHED: 'dre_limit_reached',       // 4º upload/mês
  FEATURE_LOCKED_HISTORY: 'feature_locked_history', // clique em comparativo
  FEATURE_LOCKED_PDF: 'feature_locked_pdf',       // clique em relatório PDF
  DASHBOARD_BANNER_30D: 'dashboard_banner_30d',   // 30 dias no Pro
  EMAIL_60D: 'email_upgrade_60d',                 // automação e-mail
};

// Plano Business
const BUSINESS_PLAN = {
  price_id: 'price_BUSINESS_297',               // substituir pelo ID real do Stripe
  amount: 29700,                                 // em centavos
  dre_limit_per_month: 10,
  history_months: 24,
  max_cnpjs: 5,
  support_sla_hours: 4,
};

// Componente principal
<UpsellModalBusiness
  trigger={UPSELL_TRIGGERS.DRE_LIMIT_REACHED}
  variant="limit"         // "limit" | "feature" 
  featureName="comparativo_historico"
  onUpgrade={() => redirectToCheckout(BUSINESS_PLAN.price_id)}
  onDismiss={() => trackEvent('upsell_dismissed', { trigger })}
/>

// Banner do Dashboard
<UpsellBannerBusiness
  daysInPro={user.daysInPro}
  dreCountMonth={user.dreCountCurrentMonth}
  variant="A"   // "A" | "B" | "C" — A/B/C test
/>
```

---

## MÉTRICAS PARA ACOMPANHAR

| Métrica | Meta |
|---|---|
| Impressão do modal por usuário Pro | >80% no mês 1 |
| CTR do modal (cliques no CTA) | >15% |
| Conversão modal → checkout | >5% |
| CTR do banner dashboard | >8% |
| Open rate do e-mail 60d | >38% |
| Conversão e-mail → upgrade | >3% |

---

*Bella — Assistente Autônoma Máxima Finance IA*
