# Kit Open Cart — Semana de Lançamento Máxima Finance IA
*Produzido por Bella | Turno da noite 22/05/2026*

---

## VISÃO GERAL

**Objetivo:** Copy completo para a semana de abertura oficial da Máxima Finance IA.
**Data sugerida:** 03–09/jun/2026 (webinar dia 03 ou 04/jun → abertura imediata)
**Estrutura:** 5 e-mails sequenciais + countdown stories (3 dias) + copy de abertura para WhatsApp/SMS + tokens dev

---

## E-MAIL 1 — ABERTURA (Dia D — hora H)
**Assunto:** Está aberto. Você foi um dos primeiros a saber.
**Preview text:** A Máxima Finance IA acabou de abrir para os primeiros empresários

---

[PRIMEIRO NOME],

Durante meses eu trabalhei num problema que me tirava o sono:

*Por que empresários que faturam R$100 mil por mês ainda não sabem se estão tendo lucro de verdade?*

A resposta estava no DRE — mas ninguém nunca traduziu esse documento para o português que o empresário entende.

**Hoje isso muda.**

A **Máxima Finance IA** está oficialmente aberta.

Você envia o DRE da sua empresa, e em minutos recebe:
- Diagnóstico completo em linguagem simples
- Os 5 indicadores que definem a saúde do seu negócio
- Chat com a Sofia — sua analista financeira IA, disponível 24h

**→ [ACESSAR AGORA — TESTE GRÁTIS]**

Sem contrato. Sem cartão de crédito. Sem precisar entender de contabilidade.

Só o que você precisa saber sobre a sua empresa.

Até dentro,
Karina

*P.S. As primeiras [X] vagas do plano Pro têm 30% de desconto. Depois que preencher, o preço volta ao normal.*

---
**Tokens dev:**
- `{{first_name}}` — nome do assinante
- `{{cta_url}}` — link de cadastro (configurar no Supabase Auth)
- `{{discount_deadline}}` — prazo do desconto inaugural
- **Trigger:** `waitlist_status = 'open_cart'` → disparar via Resend

---

## E-MAIL 2 — DIA D+1 (Prova / Urgência leve)
**Assunto:** O que acontece quando o empresário olha o DRE pela primeira vez
**Preview text:** Spoiler: eles ficam em choque. E depois ficam aliviados.

---

[PRIMEIRO NOME],

Ontem abrimos as portas da Máxima Finance IA.

E já temos empresários usando.

A reação mais comum até agora?

*"Eu achava que estava lucrando. O DRE mostrou que eu estava enganando a mim mesmo."*

Não é surpresa. É clareza. E clareza dói um pouco — mas salva o negócio.

**A Máxima faz três coisas que nenhum software financeiro faz:**

1. **Lê o seu DRE** → não só armazena, interpreta
2. **Fala o que significa** → em português, sem jargão contábil
3. **Responde suas perguntas** → "posso contratar?" "posso investir?" "estou no lucro de verdade?"

Se você ainda não entrou ontem:

**→ [ENTRAR AGORA — AINDA TEM DESCONTO INAUGURAL]**

O desconto de 30% para os primeiros usuários fecha [DATA].
Depois disso, volta para R$97/mês.

Karina

*P.S. O plano Gratuito não precisa de cartão. Entra, testa, vê com os próprios olhos.*

---
**Tokens dev:**
- `{{discount_deadline}}` — data de encerramento do desconto
- `{{promo_price}}` — R$67,90 (70% de R$97)
- **Trigger:** `open_cart_day = 1` AND `user_status != 'converted'`

---

## E-MAIL 3 — DIA D+3 (Conteúdo + Reengajamento)
**Assunto:** 3 números do DRE que todo empresário deve saber de cor
**Preview text:** Se você não souber esses três, está gerindo no escuro

---

[PRIMEIRO NOME],

Vou te dar uma aula rápida — de graça.

Os **3 números do DRE** que separam empresários que crescem dos que ficam no lugar:

**1. Margem Bruta %**
→ O que sobra depois de pagar o custo direto do produto/serviço
→ Referência saudável: acima de 40% para serviços, 25% para comércio

**2. Índice de Despesas Fixas**
→ Quanto das suas despesas fixas come o faturamento
→ Acima de 30%? Você é vulnerável a qualquer queda de receita

**3. Lucro Líquido %**
→ O que realmente sobrou no final do mês
→ Abaixo de 5%? Você está trabalhando para pagar conta

Esses três números estão no seu DRE agora.
O problema é que provavelmente estão enterrados em linhas que não fazem sentido.

**A Máxima Finance IA extrai esses números, calcula os percentuais e explica o que cada um significa para o SEU negócio.**

→ [TESTE GRÁTIS — ENTRAR AGORA]

Karina

---
**Tokens dev:**
- **Trigger:** `open_cart_day = 3` AND `user_status != 'converted'`
- Sem token dinâmico de preço — e-mail de conteúdo puro para reengajamento

---

## E-MAIL 4 — DIA D+5 (Urgência real — desconto fecha amanhã)
**Assunto:** O desconto fecha amanhã às 23h59
**Preview text:** Depois disso, R$97/mês. Sem exceção.

---

[PRIMEIRO NOME],

Amanhã às 23h59 o desconto inaugural da Máxima Finance IA encerra.

Sem extensão. Sem segunda chance.

De R$97 vai para R$97. Mas os primeiros usuários pagam R$[PROMO_PRICE]/mês pelo mesmo plano.

Faz sentido entrar agora? Só se você se encaixa em um desses casos:

✓ Fatura entre R$30 mil e R$500 mil por mês
✓ Não tem clareza sobre se está lucrando de verdade
✓ Toma decisões baseadas no saldo do banco (e sabe que isso é arriscado)
✓ Tem um DRE guardado na gaveta que nunca entendeu

Se marcou pelo menos dois, a Máxima é para você.

**→ [GARANTIR DESCONTO AGORA — VÁLIDO ATÉ AMANHÃ 23H59]**

Karina

*P.S. O plano Gratuito não tem desconto porque já é grátis. Mas se quiser Pro, é hoje ou R$97.*

---
**Tokens dev:**
- `{{promo_deadline_date}}` — data/hora do encerramento
- `{{promo_price}}` — preço com desconto
- **Trigger:** `open_cart_day = 5` AND `user_status != 'converted'`
- **Linha de assunto alternativa (A/B):** "Última chance: 30% off fecha amanhã"

---

## E-MAIL 5 — DIA D+6 (Fechamento — último dia)
**Assunto:** Hoje é o último dia. Depois, preço cheio.
**Preview text:** 11 horas para garantir o desconto inaugural

---

[PRIMEIRO NOME],

Hoje é o último dia com o desconto inaugural da Máxima Finance IA.

Às 23h59 o sistema remove automaticamente o código e o plano Pro volta para R$97/mês.

Não vou fazer uma grande carta de vendas agora.

Só quero te fazer uma pergunta direta:

*Você sabe, com certeza, se sua empresa está lucrando de verdade esse mês?*

Se a resposta não for um "sim" imediato — a Máxima foi feita para você.

**→ [ENTRAR AGORA — DESCONTO VÁLIDO ATÉ 23H59]**

A partir de amanhã, vejo você dentro — ou no próximo ciclo de promoção (sem data definida).

Karina

*P.S. O diagnóstico gratuito não tem prazo. Mas o desconto tem.*

---
**Tokens dev:**
- `{{hours_remaining}}` — contador de horas (calcular no front ou via Resend)
- `{{promo_deadline_time}}` — "23h59 de hoje"
- **Trigger:** `open_cart_day = 6` AND `user_status != 'converted'`
- **Envio:** Disparar às 12h00 do último dia

---

## COUNTDOWN STORIES — 3 DIAS ANTES DA ABERTURA

### Story D-3
**Visual:** Fundo escuro, texto branco, detalhe em roxo/dourado
```
Em 3 dias, algo muda
para quem fatura R$30k–R$500k por mês.

Fica ligado. 👀

#MaximaFinanceIA
```

### Story D-2
**Visual:** Timer/relógio estilizado
```
Faltam 2 dias.

Você vai ser um dos primeiros a acessar
a IA que lê o seu DRE e fala
o que ele significa.

Lista VIP → link na bio
```

### Story D-1
**Visual:** "AMANHÃ" em grande, com gradiente
```
AMANHÃ abre.

Se você está na lista VIP,
vai receber o acesso em primeira mão.

Ainda dá tempo → link na bio 🔗
```

---

## COPY WHATSAPP/SMS — ABERTURA (Dia D)

**Versão curta (SMS/WhatsApp):**
```
Karina aqui 👋 A Máxima Finance IA abriu agora. Você está na lista VIP — acesso em primeira mão + desconto inaugural de 30%. Garanta: [LINK]
```

**Versão WhatsApp (mais longa):**
```
Oi [NOME]! 🎉

Chegou o dia.

A Máxima Finance IA está aberta — e você foi dos primeiros a saber porque estava na nossa lista.

O que você ganha agora:
✅ Análise do seu DRE com IA
✅ Chat com a Sofia (sua analista financeira IA)
✅ Diagnóstico em português, sem jargão contábil
✅ 30% de desconto só para quem estava na lista (válido por 7 dias)

→ [LINK DE ACESSO]

Qualquer dúvida, me manda aqui mesmo. 💜
Karina
```

---

## TOKENS DEV — RESUMO COMPLETO

| Token | Valor | Onde usar |
|---|---|---|
| `{{first_name}}` | Nome do lead | Todos os e-mails |
| `{{cta_url}}` | URL de cadastro | E-mails 1, 2, 3 |
| `{{promo_price}}` | Preço com desconto | E-mails 1, 2, 4, 5 |
| `{{discount_deadline}}` | Data do fim do desconto | E-mails 2, 4 |
| `{{promo_deadline_date}}` | Data+hora exata (E4) | E-mail 4 |
| `{{promo_deadline_time}}` | "23h59 de hoje" (E5) | E-mail 5 |
| `{{hours_remaining}}` | Horas restantes (E5) | E-mail 5 |
| `{{open_cart_day}}` | Número do dia desde abertura | Segmentação Resend |
| `{{user_status}}` | `converted` / `trial` / `none` | Trigger de envio |

**Tabela Supabase necessária:**
```sql
-- Adicionar campo à tabela existente de waitlist
ALTER TABLE waitlist ADD COLUMN IF NOT EXISTS
  open_cart_notified_at TIMESTAMPTZ;
```

**Webhooks Stripe a configurar:**
- `checkout.session.completed` → marcar `user_status = 'converted'` → parar sequência de e-mails
- `customer.subscription.created` → acionar e-mail de boas-vindas (da sequência `05-08`)

---

*Entrega: Kit Open Cart / Semana de Lançamento — 5 e-mails + 3 stories countdown + WhatsApp/SMS abertura + tokens dev + lógica Supabase/Stripe*
*Bella — Turno da noite 22/05/2026*
