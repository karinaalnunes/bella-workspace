# PÁGINA DE VENDAS — SEÇÃO: BUMP DE PEDIDO NO CHECKOUT
*Noite 05/07/2026 — Bella*

---

## CONTEXTO DE USO

Esta seção é um **Order Bump** — oferta de impulso exibida dentro do checkout,
antes de o usuário clicar em "Confirmar pagamento". É a peça que falta para
elevar o ticket médio no momento de maior intenção de compra.

**Onde implementar:** logo acima do botão final de pagamento no Stripe Checkout.
**Ticket do plano base:** Pro R$97/mês.
**Objetivo do bump:** elevar para Business R$297/mês (uplift de R$200/mês).

---

## BUMP PARA PLANO PRO (adicionar Business durante checkout)

---

### CAIXA DE BUMP — VERSÃO PRINCIPAL

```
╔══════════════════════════════════════════════════════════════╗
║  ☑  SIM! Quero turbinar meu plano com o Business             ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║  Adicione o PLANO BUSINESS por apenas +R$200/mês             ║
║  e ganhe tudo que o Pro tem, mais:                           ║
║                                                              ║
║  ✅ DREs ilimitados (Pro tem 3/mês)                          ║
║  ✅ Relatórios de sazonalidade automáticos                   ║
║  ✅ Comparativo de períodos (mês a mês / ano a ano)          ║
║  ✅ Exportação em PDF + Excel com sua marca                  ║
║  ✅ Chat Sofia com memória dos seus DREs anteriores          ║
║  ✅ Acesso prioritário a novas funcionalidades               ║
║                                                              ║
║  💡 Clientes Business economizam em média 4h/semana          ║
║     de reuniões sobre números financeiros.                   ║
║                                                              ║
║  [ ☐ Marque aqui para adicionar o Business — R$297/mês ]    ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

---

### MICROCOPY ABAIXO DO BUMP

> *Você pode cancelar ou mudar de plano a qualquer momento.
> A diferença de R$200 será cobrada mensalmente junto com o Pro.
> Você pode testar o Business por 7 dias sem custo adicional.*

---

## BUMP PARA PLANO GRATUITO (adicionar Pro durante checkout)

---

### CAIXA DE BUMP — UPGRADE GRATUITO → PRO

```
╔══════════════════════════════════════════════════════════════╗
║  ⚡ OFERTA EXCLUSIVA PARA NOVOS USUÁRIOS                     ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║  Ative o PLANO PRO com 30 dias grátis                        ║
║  (sem cobrar nada agora)                                     ║
║                                                              ║
║  Com o Pro você terá:                                        ║
║                                                              ║
║  ✅ 3 DREs analisados por mês (Gratuito tem só 1)            ║
║  ✅ Diagnóstico completo com recomendações                   ║
║  ✅ Chat Sofia sem limite de perguntas                       ║
║  ✅ Histórico de 12 meses de análises                        ║
║  ✅ Relatório PDF para compartilhar com sócios               ║
║                                                              ║
║  Após 30 dias: R$97/mês. Cancele quando quiser.              ║
║                                                              ║
║  [ ☐ Sim, quero 30 dias Pro grátis — ativar agora ]          ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

---

### MICROCOPY ABAIXO DO BUMP

> *Sem cartão de crédito por 30 dias. Cobrado automaticamente apenas
> se você não cancelar antes do fim do período gratuito.
> Lembretes automáticos 3 dias antes do vencimento.*

---

## COPY DE URGÊNCIA (exibir se usuário desmarca o bump)

> **"Tem certeza?"**
> Esta oferta aparece apenas uma vez, durante o cadastro.
> Depois disso, o Pro custa R$97/mês sem o período gratuito.
> [Deixar sem Pro] [Aproveitar 30 dias grátis]

---

## COPY DE CONFIRMAÇÃO (após marcar o bump)

> ✅ **Plano Business adicionado!**
> Você vai ver a diferença já na primeira análise.
> [Continuar para pagamento →]

---

## TOKENS DE IMPLEMENTAÇÃO (Stripe + React)

```javascript
// Produto Bump — Pro → Business (mensal)
const BUMP_PRODUCT_ID = "prod_BUSINESS_BUMP";
const BUMP_PRICE_ID = "price_business_monthly_R297";

// Lógica de exibição do bump
const showBump = (currentPlan) => {
  if (currentPlan === "pro") return "bump_pro_to_business";
  if (currentPlan === "free") return "bump_free_to_pro_trial";
  return null;
};

// Adicionar item ao Stripe Checkout Session
const addBumpToSession = async (sessionId, bumpPriceId) => {
  const session = await stripe.checkout.sessions.retrieve(sessionId);
  // Adicionar line_item do bump via update ou novo session
  return stripe.checkout.sessions.create({
    ...session,
    line_items: [
      ...session.line_items.data,
      { price: bumpPriceId, quantity: 1 }
    ]
  });
};
```

---

## ANALYTICS — O QUE MEDIR

| Métrica | Definição | Meta |
|---|---|---|
| Bump Conversion Rate | % que marcou o bump | ≥ 20% |
| Bump Attach Rate | (compras com bump) / (total compras) | ≥ 15% |
| AOV lift | Ticket médio com bump vs. sem | +R$150 mín. |
| Rejeição do bump | % que desmarcou | < 80% |

---

## NOTAS PARA DEV

- Exibir caixa de bump **dentro** do layout do checkout, antes do resumo final.
- Usar checkbox grande (acessível no mobile).
- Animação suave ao marcar (verde + ✅).
- Se o usuário marcar e desmarcar 2×: exibir pop-up de urgência.
- Não exibir bump se o usuário já está no Business.
- A/B test: versão com foto do app vs. versão só texto.
