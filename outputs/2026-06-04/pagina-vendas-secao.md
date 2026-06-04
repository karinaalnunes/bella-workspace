# E-mails de Fechamento da Oferta do Webinar — Últimas 48h
## Sequência de Urgência: D+1 (Lembrete) → D+2 Manhã (Penúltima Chance) → D+2 Tarde (Fechamento)
*Máxima Finance IA | Turno da noite 04/06/2026 — Bella*

---

> **Contexto:** A oferta exclusiva do webinar de 03/jun (20h) fecha em **05/jun às 20h**.
> Estes 3 e-mails são disparados via Resend com gatilho baseado no campo `webinar_attended = true` e `stripe_customer_id IS NULL` no Supabase.

---

## E-MAIL 1 — D+1 (04/jun, 10h)
### Lembrete + Reforço de Valor

**Assunto:** Ainda dá tempo (mas não por muito)
**Preview:** O DRE do seu negócio está esperando você agir.

---

Oi, [primeiro_nome].

Ontem você passou [duração_sessão] min aprendendo a ler o DRE do jeito certo.

Você viu que dá pra saber, em 15 minutos, se sua empresa está de fato lucrando — ou só girando dinheiro.

A pergunta agora é simples:

**Você vai continuar olhando pro saldo da conta como indicador financeiro?**

Ou vai ter a ferramenta que faz isso por você, todo mês?

A oferta de lançamento que apresentei ontem ainda está aberta:

---

**Máxima Finance IA — Plano Pro**
~~R$ 97/mês~~ → **R$ 67/mês** por 3 meses (desconto de lançamento)

✅ Upload ilimitado de DRE
✅ Diagnóstico IA em português simples
✅ Chat Sofia (suas dúvidas financeiras, respondidas na hora)
✅ Alertas automáticos de margem e despesa
✅ Acesso vitalício à comunidade de empresários

**→ [QUERO GARANTIR MEU ACESSO COM DESCONTO]**
*(botão/link: `checkout_url_pro_lancamento`)*

---

Essa oferta fecha em **amanhã, 05/jun às 20h**.

Não porque é truque de marketing. Porque o preço de lançamento é válido só para o grupo do webinar.

A partir de 06/jun o Plano Pro volta para R$ 97/mês.

Até logo,
**Karina Alnunes**
Fundadora, Máxima Finance IA

---
*P.S. — Se você ficou com alguma dúvida do webinar, responda esse e-mail. Leio todos.*

---
**Tokens dev:**
- `[primeiro_nome]` → `user.full_name.split(' ')[0]` do Supabase
- `[duração_sessão]` → campo `webinar_attendance_minutes` (Supabase)
- `checkout_url_pro_lancamento` → link Stripe com `coupon: LANCAMENTO_WEBINAR_JUNHO`
- **Gatilho Resend:** 14h após fim do webinar (`webinar_attended = true` e `purchased = false`)
- **Segmentação:** apenas quem ficou ≥ 20 min no webinar

---

## E-MAIL 2 — D+2 Manhã (05/jun, 9h)
### Penúltima Chance + Objeção Principal

**Assunto:** "Mas será que funciona pro meu negócio?"
**Preview:** A dúvida mais comum — e a resposta honesta.

---

Oi, [primeiro_nome].

A pergunta que mais aparece depois do webinar é essa:

> *"Karina, mas e se meu DRE for diferente? E se eu não tiver contador? E se minha empresa for pequena demais?"*

Vou ser direta:

**A Máxima Finance IA foi construída exatamente para quem está nessa situação.**

Não para a empresa que já tem um CFO.
Não para quem entende de finanças.

Para o empresário que fatura entre R$ 30 mil e R$ 500 mil por mês, que sabe que precisaria olhar mais os números — mas não sabe por onde começar.

Se você tem uma planilha que ninguém preenche direito ou depende do contador para saber se lucrou no mês...

A Máxima foi feita pra você.

---

**Como funciona na prática:**

1. Você exporta o DRE do seu sistema atual (ERP, planilha, PDF do contador — aceita qualquer formato)
2. Faz upload na plataforma
3. Em menos de 2 minutos a IA entrega um diagnóstico em português, com os 5 indicadores mais importantes do seu mês
4. Você faz perguntas para a Sofia — ela responde como uma analista financeira, sem jargão

**Resultado:** Você sai sabendo exatamente o que os números dizem sobre sua empresa.

---

**Máxima Finance IA — Plano Pro**
~~R$ 97/mês~~ → **R$ 67/mês** por 3 meses

**→ [GARANTIR MEU ACESSO AGORA]**
*(botão/link: `checkout_url_pro_lancamento`)*

---

A oferta fecha **hoje às 20h**.

Se quiser testar antes de decidir, o Plano Gratuito está disponível sem cartão.
Mas o desconto de 30% é exclusivo para quem comprar hoje.

Karina

---
*P.S. — Garantia de 7 dias. Se não resolver, devolvemos tudo. Sem perguntas.*

---
**Tokens dev:**
- Mesmo template do E-mail 1
- **Horário de envio:** 9h do dia D+2 (`created_at` do registro de inscrição + 37h)
- **Condição:** `purchased = false` (não comprou ainda)
- **Versão alternativa (A/B):** Substituir bloco "Como funciona" por depoimento inline com foto (quando tiver prova real)

---

## E-MAIL 3 — D+2 Tarde (05/jun, 17h)
### Fechamento Real — Última Hora

**Assunto:** Fecha em 3 horas ⏱️
**Preview:** Não é contagem regressiva falsa. O preço muda às 20h.

---

Oi, [primeiro_nome].

Em **3 horas** o preço de lançamento encerra.

Às 20h de hoje o sistema atualiza automaticamente: o Plano Pro volta para R$ 97/mês, sem desconto.

Não tem extensão. Não tem "só mais 24h". Não tem segunda chance.

---

Eu sei que você pode estar pensando: *"Vou esperar um pouco mais."*

Mas aqui está o que acontece quando a gente espera:

Você fecha mais um mês sem saber se lucrou de verdade.
Você toma mais uma decisão de contratar (ou cortar) baseada em feeling.
Você deixa mais um DRE acumulando na pasta do WhatsApp do contador.

**Enquanto isso, seus custos não esperam.**

---

A oferta que fecha hoje:

**Plano Pro — R$ 67/mês por 3 meses** (economiza R$ 90 no trimestre)

→ Upload de DRE ilimitado
→ Diagnóstico IA + Chat Sofia
→ Alertas automáticos
→ Suporte prioritário
→ Garantia de 7 dias

**→ [GARANTIR MEU ACESSO — ÚLTIMAS HORAS]**
*(botão/link: `checkout_url_pro_lancamento`)*

---

Se você preferir começar pelo Plano Gratuito, tudo bem — ele não tem prazo.
Mas o desconto de 30% vai com as 20h de hoje.

Karina Alnunes
Máxima Finance IA

---
*"Entrei no plano gratuito primeiro, mas depois de ver o diagnóstico do meu DRE no primeiro mês migrei pro Pro na hora. Não sabia que estava operando com margem negativa em um dos meus produtos há 4 meses."*
— Validar com depoimento real quando disponível

---
**Tokens dev:**
- **Horário de envio:** 17h do dia D+2 (3h antes do fechamento)
- **Condição:** `purchased = false` (não comprou ainda)
- **Subject line A/B:** Variante B — *"Você tem 3 horas. (Sério)"*
- **Urgência técnica:** Confirmar que o cupom `LANCAMENTO_WEBINAR_JUNHO` está configurado para expirar às 20h do dia 05/06 no Stripe Dashboard → Products → Coupons → Edit → Expiration date
- **Webhook pós-pagamento:** `stripe.checkout.session.completed` → Resend: cancelar E-mail 3 se já pagou antes de 17h

---

## RESUMO DA SEQUÊNCIA — ÚLTIMAS 48H

| E-mail | Horário | Assunto | Objetivo |
|--------|---------|---------|----------|
| E-mail 1 | 04/jun 10h | Ainda dá tempo (mas não por muito) | Reengajar quem saiu do webinar animado mas não comprou |
| E-mail 2 | 05/jun 9h | "Mas será que funciona pro meu negócio?" | Destruir a objeção principal; reforçar fit |
| E-mail 3 | 05/jun 17h | Fecha em 3 horas ⏱️ | Urgência real + CTA final |

**Gatilho de saída:** `purchased = true` → parar a sequência imediatamente (não enviar próximos e-mails para quem já comprou)

**Métricas esperadas (benchmark SaaS brasileiro, lançamento via webinar):**
- Open rate E-mail 1: 45–55%
- Open rate E-mail 3: 35–45% (urgência aumenta abertura)
- Conversão total da sequência: 8–15% dos que abriram E-mail 1

---
*Produzido por Bella — Turno da Noite 04/06/2026*
