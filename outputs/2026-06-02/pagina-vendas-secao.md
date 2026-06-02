# Seção: Oferta de Lançamento D-Day — Bônus Exclusivos do Webinar
*Produzido por Bella | Turno da noite | 02/06/2026*
*Contexto: D-1 do webinar de lançamento (03/jun, 20h)*

---

## OBJETIVO DESTA SEÇÃO

Copy completo para a **oferta especial do webinar** — slide de oferta, CTA ao vivo e copy do checkout.
Karina apresenta essa oferta durante o webinar (final da aula, ~21h30).
Cria escassez real (72h) e bônus que expiram com o webinar.

---

## ESTRUTURA DO SLIDE DE OFERTA (para o Canva/apresentação)

### Slide 1 — REVELAÇÃO DO PREÇO

**Headline:**
> "Isso que eu acabei de te ensinar… existe uma IA que faz por você. Toda semana. Automaticamente."

**Subheadline:**
> Apresento o **Máxima Finance IA** — o primeiro SaaS que lê o DRE da sua empresa e te entrega um diagnóstico financeiro em linguagem humana.

---

### Slide 2 — O QUE VOCÊ LEVA HOJE

**Plano Pro — R$ 97/mês**
*(ou R$ 970/ano — economize 2 meses)*

✅ Análise mensal de DRE com IA
✅ Diagnóstico em linguagem simples — sem jargão de contador
✅ Chat Sofia: tire dúvidas financeiras a qualquer hora
✅ Alertas automáticos quando um indicador sai do normal
✅ Histórico comparativo mês a mês
✅ Dashboard com os 5 indicadores que você aprendeu hoje

---

### Slide 3 — BÔNUS EXCLUSIVOS (APENAS PARA QUEM ASSINAR HOJE)

**🎁 BÔNUS 1 — Checklist "DRE em 5 Minutos"**
PDF com os 5 números que você precisa olhar todo mês.
*Valor: R$ 47 | Hoje: GRÁTIS*

**🎁 BÔNUS 2 — Acesso antecipado ao relatório de Benchmarking Setorial**
Compare sua margem com empresas do seu setor.
Disponível em julho — você entra na lista VIP agora.
*Valor: R$ 97 | Hoje: GRÁTIS*

**🎁 BÔNUS 3 — 30 dias no Plano Business grátis**
Multi-usuários, relatório para sócios, exportação em PDF.
*Valor: R$ 297 | Hoje: GRÁTIS por 30 dias*

---

### Slide 4 — ESCASSEZ E URGÊNCIA

**Esta oferta expira em:**
```
⏰ 72 HORAS
```

> Após 05/jun às 20h, o Plano Pro volta para R$ 97/mês **sem os bônus**.
> Os 3 bônus somam R$ 441 em valor entregue — e desaparecem com o fechamento do carrinho.

**Vagas com preço de lançamento:** 50 empresas
*(justificativa: onboarding personalizado das primeiras análises)*

---

### Slide 5 — GARANTIA

**30 dias de garantia incondicional.**

> Se em 30 dias você não tiver mais clareza sobre o resultado financeiro da sua empresa do que tinha antes — eu devolvo 100% do que você pagou. Sem perguntas. Sem burocracia.
> *Você não está comprando. Você está testando.*

---

## CTA AO VIVO (script para Karina falar)

```
"Agora eu quero te dar uma chance de colocar isso pra trabalhar 
na sua empresa — não amanhã, hoje.

O link está no chat. Você vai para uma página simples, 
escolhe o plano Pro, e em menos de 3 minutos já tem acesso 
ao dashboard e ao Chat Sofia.

Mas atenção: os 3 bônus que eu mencionei aqui só existem 
para quem assinar até quinta-feira às 20h. 

Depois disso — produto continua, bônus somem.

O link está no chat. [pausa 5 segundos]

Enquanto vocês acessam, eu vou responder perguntas aqui."
```

---

## COPY DO CHECKOUT (tela de pagamento — Stripe)

### Header da página:
> **Máxima Finance IA — Plano Pro**
> Oferta de lançamento · Válida até 05/jun às 20h

### Card do plano:
```
PLANO PRO — OFERTA DE LANÇAMENTO

R$ 97/mês
ou R$ 970/ano (economize R$ 194)

[ASSINAR AGORA — GARANTIA 30 DIAS] ← botão principal

Bônus incluídos:
☑ Checklist DRE em 5 Minutos (PDF)
☑ Acesso VIP ao Benchmarking Setorial
☑ 30 dias no Business grátis

Oferta expira em: [CONTADOR 72H]
```

### Microcopy abaixo do botão:
> 🔒 Pagamento seguro via Stripe · Cancele quando quiser · Garantia de 30 dias

### Trust signals (abaixo do card):
> "Eu não sabia o que eram despesas fixas e variáveis. Depois de 1 mês com a Máxima, entendi por que minha loja sempre quebrava em julho." — Carlos, dono de loja de roupas

---

## TOKENS PARA DEV

```typescript
// Criar coupon de bônus no Stripe
const coupon = await stripe.coupons.create({
  name: 'LANCAMENTO_WEBINAR_JUNHO',
  duration: 'once',
  percent_off: 0, // sem desconto de preço, bônus são serviços
  redeem_by: Math.floor(new Date('2026-06-05T23:00:00-03:00').getTime() / 1000),
  max_redemptions: 50,
});

// Webhook: ao completar checkout com esse coupon
// → inserir registro em supabase.bonuses (user_id, bonus_checklist, bonus_benchmarking, bonus_business_trial_30d)
// → disparar e-mail "seus bônus estão chegando" via Resend

// Banner de escassez: mostrar contagem regressiva
// Data de expiração: 2026-06-05T23:00:00-03:00
const expiresAt = new Date('2026-06-05T23:00:00-03:00');
```

---

## MÉTRICAS PARA ACOMPANHAR

| Métrica | Meta | Como medir |
|---|---|---|
| Taxa de conversão do webinar | ≥ 5% dos presentes | Acessos no checkout / inscritos presentes |
| Tempo médio na checkout page | < 3 min | Google Analytics / Vercel |
| Carrinhos abandonados | < 40% | Webhook `checkout.session.expired` no Stripe |
| Conversão de e-mail de carrinho (48h) | ≥ 15% dos abandonados | Resend metrics |

---

*Arquivo: `outputs/2026-06-02/pagina-vendas-secao.md`*
*Próximo uso: Karina apresenta durante o webinar em 03/jun, ~21h30*
