# Copy Anti-Churn / Cancelamento — Sequência de Salvamento
*Máxima Finance IA — Turno da noite 27/05/2026*

---

## CONTEXTO DE USO

Acionada quando o usuário clica em "Cancelar plano" ou "Downgrade" dentro do app.
Objetivo: reduzir churn voluntário em 20–40% antes de processar o cancelamento no Stripe.

---

## 1. TELA DE CANCELAMENTO (Offboarding Modal — Passo 1 de 3)

**Token dev:** `<CancelModal step="reason" />`

---

**Headline:**
> Antes de ir, deixa a gente entender o que aconteceu.

**Subtítulo:**
> Sua resposta leva 20 segundos e nos ajuda a melhorar. Prometemos honrar sua escolha.

**Opções de motivo (radio buttons):**

- [ ] Não estou usando o suficiente
- [ ] Está caro para mim agora
- [ ] Não entendi como funciona direito
- [ ] Encontrei outra solução
- [ ] Minha empresa está passando por um momento difícil
- [ ] Outro motivo

**CTA primário:** `Continuar cancelamento →`
**CTA secundário (link):** `Quero continuar no plano`

---

## 2. TELA DE CANCELAMENTO (Offboarding Modal — Passo 2 de 3)
*Resposta dinâmica conforme o motivo selecionado*

**Token dev:** `<CancelModal step="save_offer" reason={selectedReason} />`

---

### Variante A — "Não estou usando o suficiente"

**Headline:**
> E se a gente te mostrasse o que você está perdendo?

**Corpo:**
> Empresas que leem o DRE mensalmente tomam decisões 3x mais rápidas.
>
> Que tal um **diagnóstico gratuito do seu último mês** agora mesmo?
>
> Em 5 minutos você vai ver onde está perdendo dinheiro sem perceber.

**CTA primário (verde):** `Sim, quero ver meu diagnóstico`
**CTA secundário (link):** `Não, quero cancelar mesmo`

---

### Variante B — "Está caro para mim agora"

**Headline:**
> Entendemos. Momentos difíceis existem.

**Corpo:**
> Que tal ficar no **plano Gratuito** por enquanto?
> Você não perde seu histórico de análises e pode voltar ao Pro quando quiser — sem burocracia.
>
> Ou, se preferir: **pause por 1 mês por R$ 0** e a Máxima te avisa quando retomar.

**CTA primário (verde):** `Ir para o Gratuito — manter meu histórico`
**CTA secundário (azul):** `Pausar por 1 mês`
**CTA terciário (link):** `Cancelar mesmo assim`

**Token Stripe:** `subscription.pause_collection` / `subscription.cancel_at_period_end`

---

### Variante C — "Não entendi como funciona"

**Headline:**
> Isso é culpa nossa, não sua.

**Corpo:**
> A Máxima Finance foi feita para ser simples — e ainda não chegamos lá 100%.
>
> **Que tal 30 minutos com nossa equipe?** A gente configura tudo contigo, ao vivo, de graça.
>
> Nenhuma pressão de venda. Só resultado.

**CTA primário (verde):** `Agendar atendimento gratuito`
**CTA secundário (link):** `Cancelar mesmo assim`

**Token dev:** `<CalendlyEmbed url="maximafinance.com.br/suporte-ao-vivo" />`

---

### Variante D — "Minha empresa está passando por um momento difícil"

**Headline:**
> Justamente para isso a Máxima Finance existe.

**Corpo:**
> Quando o caixa aperta, é hora de ler o DRE — não de fechar as ferramentas.
>
> Fica com a gente no **plano Gratuito** até você estabilizar. Seu histórico fica salvo, e a IA continua do seu lado.

**CTA primário (verde):** `Migrar para o Gratuito agora`
**CTA secundário (link):** `Cancelar mesmo assim`

---

### Variante E — "Encontrei outra solução"

**Headline:**
> Sério? Qual ferramenta interpreta seu DRE em português simples?

**Corpo:**
> Se você encontrou algo melhor, ótimo — torcemos pelo seu crescimento.
>
> Mas se quiser comparar antes de decidir: teste o diagnóstico completo do seu último DRE agora. **Gratuito, sem compromisso.**

**CTA primário (verde):** `Ver diagnóstico completo antes de ir`
**CTA secundário (link):** `Cancelar mesmo assim`

---

## 3. TELA DE CANCELAMENTO (Offboarding Modal — Passo 3 de 3)
*Confirmação final — só aparece se o usuário insistiu em cancelar*

**Token dev:** `<CancelModal step="final_confirmation" />`

---

**Headline:**
> Tudo bem. Cancelamento confirmado.

**Corpo:**
> Seu acesso continua até **[data_fim_periodo]**.
> Depois disso, você fica no plano Gratuito — sem perder seu histórico de análises.
>
> *Se mudar de ideia, é só reativar. Sua conta nunca some.*

**CTA primário (verde):** `Voltar para o app`
**CTA secundário (link cinza):** `Encerrar conta completamente`

**Nota dev:** "Encerrar conta completamente" aciona GDPR soft-delete — confirmar por e-mail separado antes de executar.

---

## 4. SEQUÊNCIA DE E-MAILS ANTI-CHURN

### E-mail 1 — Imediato pós-cancelamento
**Assunto:** Seu cancelamento foi processado. Mas tem um recado.

**Corpo:**
> Olá, [nome].
>
> Cancelamento confirmado. Seu plano Pro fica ativo até [data].
>
> Antes de você ir, deixa eu te mostrar o que vai ficar disponível no Gratuito:
> - Análise de 1 DRE por mês ✓
> - Chat Sofia — 10 perguntas/mês ✓
> - Histórico dos seus DREs anteriores ✓
>
> O que você perde no Pro:
> - Análises ilimitadas ✗
> - Alertas automáticos de margem ✗
> - Comparativo mês a mês ✗
> - Chat Sofia ilimitado ✗
>
> Se o motivo foi financeiro — temos um cupom esperando por você.
> Se foi outro motivo — quero ouvir. Responde esse e-mail diretamente.
>
> — Karina, fundadora da Máxima Finance IA

**CTA:** `Reativar Pro com desconto de 30%` → `maximafinance.com.br/reativar`
**Token Stripe:** cupom `VOLTEI30` — válido 7 dias

---

### E-mail 2 — D+7 após cancelamento
**Assunto:** [nome], tem 1 insight do seu DRE que você precisa ver

**Corpo:**
> Oi, [nome].
>
> Faz uma semana que você cancelou. Não vim te pressionar.
>
> Vim te mostrar que no seu último DRE analisado, a Máxima identificou:
> **[insight_personalizado do último diagnóstico]**
>
> Esse número ainda vale. E vai continuar valendo no próximo mês.
>
> Se quiser uma análise atualizada de maio — está esperando por você.
>
> Reativar leva 1 clique.

**CTA:** `Ver análise de maio` → reativa o plano Pro
**Token dev:** `{{last_analysis_insight}}` — puxar do Supabase campo `analyses.key_insight`

---

### E-mail 3 — D+30 após cancelamento
**Assunto:** Como maio fechou para você?

**Corpo:**
> [nome],
>
> Maio acabou ontem. Como fechou para a sua empresa?
>
> Sabe aquela sensação de que "deu certo" mas você não tem certeza de quanto sobrou de verdade?
>
> É exatamente aí que o DRE fala mais alto.
>
> Se quiser fazer o fechamento de maio com a Máxima — o diagnóstico completo leva 5 minutos.
>
> Sem pressão. Só resultado.

**CTA:** `Fazer o fechamento de maio agora` → página de reativação
**Oferta:** 1º mês de volta por R$ 47 (50% off)
**Token Stripe:** cupom `MAIO47` — válido até 10/jun

---

## 5. MENSAGEM WHATSAPP — CHURN PREVENTION (D+3)

*Acionada se o usuário acessou o app ao menos 1x após cancelar*

**Token dev:** `whatsapp_template: churn_recovery_d3`

> Oi [nome]! Vi que você acessou a Máxima hoje. 👋
>
> Seu plano Pro ainda está ativo até [data]. Aproveitou para ver algo?
>
> Se quiser continuar — é só clicar aqui e reavaliar: [link]
>
> Se tiver qualquer dúvida, pode me chamar diretamente. Sou a Karina.

---

## MÉTRICAS PARA ACOMPANHAR

| Evento | Meta |
|---|---|
| Taxa de salvamento (modal passo 2) | ≥ 25% |
| Reativação via E-mail 1 | ≥ 8% |
| Reativação via E-mail 2 | ≥ 5% |
| Reativação via E-mail 3 | ≥ 3% |
| Churn rate mensal global | ≤ 5% |

---

## TOKENS DEV — RESUMO

```
// Modal
<CancelModal step="reason" />
<CancelModal step="save_offer" reason={selectedReason} />
<CancelModal step="final_confirmation" />

// Stripe
subscription.pause_collection — pausa cobrança, mantém acesso
subscription.cancel_at_period_end — cancela no fim do período
coupon: VOLTEI30 — 30% off, 7 dias de expiração
coupon: MAIO47 — R$ 47 primeiro mês, válido até 10/jun

// Supabase
table: cancellations (user_id, reason, step_reached, saved, created_at)
table: analyses (user_id, key_insight) — para personalização E-mail 2

// Resend triggers
cancel.confirmed → E-mail 1 imediato
cancel.confirmed + 7d → E-mail 2
cancel.confirmed + 30d → E-mail 3
app.accessed_after_cancel (D+1 a D+7) → WhatsApp D+3
```

---

*Bella — Turno da noite 27/05/2026*
