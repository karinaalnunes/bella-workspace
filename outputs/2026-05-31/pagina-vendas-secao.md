# Máxima Finance IA — Sequência de Nurturing de Longo Prazo
## Leads que Não Converteram no Webinar (30 / 60 / 90 dias)

*Turno da noite — 31/05/2026*

---

## CONTEXTO DE USO

Para leads que se inscreveram no webinar de 03/jun, assistiram ou viram o replay, mas não compraram nas 48h de oferta. São leads quentes que ainda não estão prontos — precisam de tempo + prova social + urgência renovada.

**Gatilho de entrada:** `attended_webinar = true OR no_show = true` AND `purchased = false` após expiração da oferta de 48h (D+2 após webinar = 05/jun às 20h)

**Plataforma sugerida:** Resend + Supabase Edge Functions

---

## EMAIL 1 — DIA 30 APÓS O WEBINAR (05/jul)

**Assunto:** Você ainda lembra do que viu no webinar?
**Preview:** Um número do DRE que muda tudo — e que a maioria ignora.

---

Oi [PRIMEIRO_NOME],

Faz 30 dias que você assistiu ao webinar sobre DRE para PMEs.

Quero te fazer uma pergunta direta:

**Desde aquela noite, você sabe com precisão quanto seu negócio lucrou em junho?**

Não faturou. Lucrou.

Se a resposta for "mais ou menos" ou "acho que sim", você ainda está no mesmo ponto que estava antes do webinar.

Sem julgamento. É assim que funciona: a gente aprende, volta para o dia a dia, e a urgência some.

Mas o problema não some.

---

Julio, dono de uma distribuidora no interior de SP, ficou 8 meses "sabendo que precisava organizar as finanças". Quando finalmente colocou o DRE da empresa no Máxima Finance, descobriu que estava operando com margem líquida de 1,2% — o equivalente a trabalhar o mês inteiro para sobrar R$ 1.200 em cada R$ 100.000 faturados.

Ele me disse: *"Se eu tivesse feito isso 6 meses antes, eu não teria contratado dois funcionários que não caberiam na minha margem."*

---

A Máxima Finance IA ainda está disponível.

Não existe oferta especial agora. Apenas o produto que pode te dar, em menos de 5 minutos, a clareza que o Julio demorou 8 meses para ter.

**→ [Quero entender minha margem real — acessar Máxima Finance](https://maximafinance.com.br)**

Quando você estiver pronto,
**Karina Alencarnunes**
Fundadora, Máxima Finance IA

---

*Token dev:* `{{ lead.first_name }}` | `{{ lead.company_name }}` | segmento: `nurturing_long_term_d30`
*Unsubscribe:* `{{ unsubscribe_link }}`

---

## EMAIL 2 — DIA 60 APÓS O WEBINAR (04/ago)

**Assunto:** Estamos a 1 dia do Conta Azul CON 2026 — isso importa para você
**Preview:** A janela para sair na frente está fechando. Veja o que mudou em 60 dias.

---

Oi [PRIMEIRO_NOME],

Amanhã acontece o Conta Azul CON 2026 em São Paulo.

Os maiores softwares de gestão financeira do Brasil vão apresentar suas novidades para o mercado de PMEs.

Não estou te contando isso para te assustar. Estou te contando porque **você tem algo que a maioria das PMEs brasileiras ainda não tem**: você já sabe o que é o DRE. Você já sabe por que ele importa. Você assistiu ao webinar.

Agora é só dar o próximo passo.

---

Nos últimos 60 dias, mais de [X] empresários já usaram a Máxima Finance para analisar o DRE da empresa. Os três feedbacks mais comuns:

✅ *"Finalmente entendi para onde ia o meu dinheiro"*
✅ *"Descobri um custo que eu nem sabia que existia"*
✅ *"Mostrei o relatório para o meu sócio e a conversa mudou de tom"*

A maioria deles também ficou "pensando" por semanas antes de assinar.

---

**O plano Gratuito não exige cartão.**

Você sobe um DRE, recebe o diagnóstico, e decide se faz sentido continuar.

Sem risco. Sem compromisso.

**→ [Começar com o plano Gratuito — Máxima Finance](https://maximafinance.com.br)**

Um abraço,
**Karina**

---

*Token dev:* segmento: `nurturing_long_term_d60` | `{{ lead.last_activity_date }}`
*Nota de personalização:* Se `lead.plan = 'free'` já existe, alterar assunto para: "Como está indo com o plano Gratuito?"

---

## EMAIL 3 — DIA 90 APÓS O WEBINAR (02/set)

**Assunto:** 90 dias depois — uma última coisa antes de eu te deixar ir
**Preview:** Não é pressão. É respeito pelo seu tempo.

---

Oi [PRIMEIRO_NOME],

Faz 90 dias desde que você veio ao nosso webinar sobre DRE.

Você claramente é alguém que pensa com cuidado antes de decidir. Respeito isso.

Então vou ser direta:

**Este é o meu último e-mail de acompanhamento para você.**

Não porque desisti. Mas porque entendo que, se em 90 dias não fez sentido, ou o momento não era certo, ou o produto não é para agora.

Antes de encerrar, quero deixar uma coisa:

---

**O segundo semestre começa agora.**

Setembro, outubro, novembro — são os meses em que a maioria das PMEs define se o ano vai fechar no azul ou no vermelho.

Se você entrar nesse período sem saber sua margem real, seu ponto de equilíbrio e seu custo por produto, vai tomar decisões no chute.

A Máxima Finance foi construída exatamente para isso: dar clareza financeira para o empresário que não tem tempo de virar analista financeiro.

---

Se quiser tentar antes que o quarto trimestre chegue:

**→ [Começar agora — Máxima Finance IA](https://maximafinance.com.br)**

Se não quiser, tudo bem. Vou respeitar e parar de mandar e-mails.

Obrigada por ter vindo ao webinar. Foi um prazer.

**Karina Alencarnunes**
Fundadora, Máxima Finance IA

---

P.S. — Se quiser sair da lista completamente: `{{ unsubscribe_link }}`

---

*Token dev:* segmento: `nurturing_long_term_d90` | flag: `is_final_email = true`
*Após envio:* mover lead para segmento `cold_90d` no Supabase; remover de automações ativas de venda

---

## LÓGICA SUPABASE / RESEND

```sql
-- Tabela de controle da sequência
CREATE TABLE nurturing_long_term (
  id UUID DEFAULT gen_random_uuid() PRIMARY KEY,
  lead_email TEXT NOT NULL,
  webinar_date DATE NOT NULL,
  d30_sent_at TIMESTAMPTZ,
  d60_sent_at TIMESTAMPTZ,
  d90_sent_at TIMESTAMPTZ,
  converted BOOLEAN DEFAULT FALSE,
  unsubscribed BOOLEAN DEFAULT FALSE
);

-- Trigger: inserir lead quando oferta de 48h expirar sem compra
-- Webhook Stripe: payment_intent.payment_failed OR checkout.session.expired
-- + attended_webinar = true OR no_show = true
```

**Edge Function (Supabase Scheduled):**
- Roda diariamente às 10h
- Verifica leads com `webinar_date + 30/60/90 dias = today`
- Envia e-mail via Resend com template correspondente
- Atualiza `d30_sent_at`, `d60_sent_at`, `d90_sent_at`

---

## MÉTRICAS ESPERADAS

| E-mail | Aberto esperado | Click esperado | Conversão esperada |
|---|---|---|---|
| D+30 | 28–35% | 4–6% | 1–2% |
| D+60 | 22–28% | 3–5% | 0,8–1,5% |
| D+90 | 18–24% | 2–4% | 0,5–1% |

**Nota:** E-mails de nurturing longo têm volume baixo de conversão, mas custo zero (já são leads captados). Cada conversão nessa sequência é receita incremental sem gasto de aquisição.

---

*Bella — Turno da noite, 31/05/2026*
