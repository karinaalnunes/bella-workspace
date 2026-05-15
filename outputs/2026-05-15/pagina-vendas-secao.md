# Máxima Finance IA — Seção: Popup de Exit-Intent + E-mail de Carrinho Abandonado
*Turno da noite — 15/05/2026 | Bella*

---

## CONTEXTO

Visitantes que chegam à landing page e saem sem cadastrar ou pagar representam 80-90% do tráfego. Esta seção resolve isso com dois mecanismos de recuperação:

1. **Popup de Exit-Intent** — aparece quando o cursor se move para fechar a aba
2. **E-mail de Carrinho Abandonado** — para quem iniciou checkout mas não pagou

---

## 1. POPUP DE EXIT-INTENT

### Quando disparar
- Usuário move cursor para fechar aba (desktop)
- Usuário rola para cima rapidamente (mobile)
- Exibir apenas 1x por visita, nunca para quem já pagou

---

### Variante A — Para visitantes frios (ainda não cadastrou)

**Headline:**
> Espera. Antes de ir embora…

**Subheadline:**
> Você sabe quanto sua empresa realmente lucrou nos últimos 3 meses?

**Corpo:**
> A maioria dos empresários responde "mais ou menos" — e isso custa caro.
>
> Baixe grátis o **Checklist DRE em 5 Minutos** e descubra os 3 números que você precisa olhar toda semana.

**Campo:**
```
[ Seu melhor e-mail              ] [Quero o Checklist →]
```

**Microcopy abaixo do botão:**
> Grátis. Sem cartão. Você recebe agora.

**Link de saída:**
> *Não, prefiro continuar no escuro sobre meu lucro.*

---

### Variante B — Para quem já está no plano Gratuito (logado, nunca pagou)

**Headline:**
> Você ainda não desbloqueou o diagnóstico completo.

**Corpo:**
> No plano Pro, a Sofia analisa cada linha do seu DRE e aponta exatamente onde o lucro está sumindo.
>
> Experimente 7 dias por R$0. Cancele quando quiser.

**CTA principal:**
> [Testar Pro por 7 dias grátis →]

**CTA secundário:**
> *Continuar no plano Gratuito*

---

### Variante C — Para quem visitou a página de planos (intenção de compra)

**Headline:**
> O Pro por R$97 te paga de volta no primeiro mês.

**Corpo:**
> Uma decisão baseada no seu DRE — cortar um custo errado, ajustar um preço — já cobre o valor da assinatura.
>
> Se não fizer sentido em 7 dias, a gente devolve.

**CTA:**
> [Começar agora com garantia de 7 dias →]

**Urgência (opcional A/B):**
> *Esta oferta expira quando você fechar esta janela.*

---

## 2. E-MAIL DE CARRINHO ABANDONADO

### Sequência de 2 e-mails (disparada via webhook Stripe — evento `checkout.session.expired`)

---

### E-mail 1 — Enviado 1 hora após abandono

**Assunto:** Você esqueceu alguma coisa, [Nome]

**Preview text:** Seu acesso à Máxima Finance ainda está reservado.

---

**Corpo:**

Oi, [Nome].

Você estava tão perto.

Começou o cadastro no Máxima Finance IA mas não finalizou — e está tudo bem, acontece.

Só queria garantir que você sabe o que fica pra trás se não voltar:

- ✅ Diagnóstico automático do seu DRE em linguagem simples
- ✅ Chat Sofia para tirar dúvidas financeiras a qualquer hora
- ✅ Alertas quando seus indicadores fogem do saudável
- ✅ Histórico comparativo mês a mês

Tudo isso por **R$97/mês** — menos que uma consultoria por hora.

[→ Voltar e finalizar minha assinatura]

Se tiver alguma dúvida antes de assinar, responda este e-mail. Estou aqui.

— Equipe Máxima Finance

*P.S.: Seu acesso fica reservado por 24 horas. Depois disso, a vaga some.*

---

### E-mail 2 — Enviado 24 horas após abandono (último aviso)

**Assunto:** Última chance — sua vaga expira hoje

**Preview text:** Não quero que você fique mais um mês no escuro sobre seu lucro.

---

**Corpo:**

[Nome], vou ser direto.

A maioria dos empresários que não conclui o cadastro continua tomando decisões financeiras no chute — e pagando caro por isso.

Não precisa ser assim.

O Máxima Finance IA analisa seu DRE e te diz, em português claro:
- O que está consumindo sua margem
- Onde você pode cortar sem prejudicar o crescimento
- Quando o caixa vai apertar antes que aperte de verdade

**Garantia de 7 dias:** se não trouxer clareza pro seu financeiro, a gente devolve cada centavo. Sem perguntas.

[→ Finalizar minha assinatura agora]

Esse link expira em **3 horas**.

— Karina Alencarnunes
Fundadora, Máxima Finance IA

*P.S.: Se não é o momento certo, tudo bem. Mas guarda o link — quando for, o acesso vai ser mais rápido.*

---

## IMPLEMENTAÇÃO TÉCNICA

### Popup Exit-Intent
```javascript
// Disparar com: mouseleave no document (desktop) + scroll velocity (mobile)
// Biblioteca sugerida: exitintent.js ou custom event listener
// Variante decidida por: auth state (não logado → A, logado free → B, visitou /planos → C)
// Cookie: exit_shown=1 (TTL: 24h) para não re-exibir
```

### Carrinho Abandonado (Stripe Webhook)
```
Evento: checkout.session.expired
→ Extrair: customer_email, customer_name, plan_id
→ Disparar: e-mail 1 via Resend (delay: 1h)
→ Se não converteu em 24h: disparar e-mail 2 (delay: 23h adicionais)
→ Se converteu: cancelar sequência (checar evento payment_intent.succeeded)
```

### Métricas para acompanhar
| Métrica | Meta |
|---|---|
| Popup — taxa de opt-in (Variante A) | ≥ 8% |
| Popup — taxa de upgrade (Variante B) | ≥ 3% |
| E-mail 1 — taxa de abertura | ≥ 40% |
| E-mail 1 — taxa de clique | ≥ 12% |
| E-mail 2 — taxa de conversão | ≥ 5% |

---

*Prioridade de implementação: E-mail de carrinho abandonado primeiro (alto ROI, baixa complexidade). Popup em seguida, começando pela Variante A.*
