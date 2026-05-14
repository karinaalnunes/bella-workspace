# Sequência de E-mails de Retenção — Máxima Finance IA
*Noite 14/05/2026 — Bella*

> **Objetivo:** Reduzir churn e aumentar LTV de usuários pagantes (Pro e Business).
> **Quando enviar:** Automatizado via Supabase + ferramenta de e-mail (Resend / Loops.so).
> 3 e-mails essenciais: Semana 1 → Mês 1 → Reativação pós-inatividade.

---

## E-MAIL 1 — DIA 7 APÓS O PAGAMENTO
**Assunto:** Você usou o Máxima essa semana?

---

Olá, [NOME].

Faz 7 dias que você ativou o plano [PRO / BUSINESS].

Quero ter certeza que você já extraiu o primeiro diagnóstico do seu DRE — porque é aí que a maioria dos nossos usuários tem o primeiro "momento de clareza".

**Você ainda não fez o upload?**

Leva menos de 3 minutos. Basta ter o DRE do mês passado em PDF ou planilha.

→ [Fazer minha primeira análise agora]

**Já fez? Ótimo.**

Aqui estão os 3 próximos passos para aproveitar ao máximo o plano [PRO]:

1. **Pergunte para a Sofia:** "Qual meu maior risco financeiro este mês?"
2. **Compare dois meses:** Faça upload do mês anterior e compare a evolução da margem.
3. **Compartilhe com seu contador:** Baixe o relatório em PDF e mostre o diagnóstico.

Qualquer dúvida, é só responder este e-mail.

Estou aqui,
**Karina Alnunes**
Fundadora, Máxima Finance IA

---

*Você recebe este e-mail porque é assinante do plano [PRO / BUSINESS]. Para cancelar, acesse Configurações → Plano.*

---

## E-MAIL 2 — DIA 30 APÓS O PAGAMENTO
**Assunto:** 1 mês de Máxima — o que mudou na sua empresa?

---

Olá, [NOME].

Há exatamente 1 mês você assinou o Máxima Finance IA.

Quero te fazer uma pergunta direta:

**Você tomou alguma decisão financeira diferente este mês por causa do que viu no DRE?**

Se sim — ótimo. Você está usando a ferramenta do jeito certo.

Se não ainda — deixa eu te mostrar o que os melhores usuários fizeram no primeiro mês:

---

**O que usuários como você fizeram no mês 1:**

✅ Identificaram 1 produto ou serviço com margem negativa (e pararam de vendê-lo)
✅ Descobriram que o pró-labore não estava no DRE — e corrigiram
✅ Levaram o relatório para negociar com fornecedor e conseguiram desconto
✅ Usaram a Sofia para simular: "o que acontece se eu contratar mais um funcionário?"

---

**Sua missão do mês 2:**

Faça upload do DRE de [MÊS ANTERIOR] e compare com [MÊS MAIS ANTIGO].
Peça para a Sofia: *"O que mudou na minha margem bruta nos últimos 2 meses?"*

→ [Abrir meu painel agora]

Até o próximo mês,
**Karina**

P.S. — Se tiver interesse em ter acesso a [RECURSO EXCLUSIVO DO BUSINESS], o upgrade custa apenas R$[DIFERENÇA]/mês. → [Ver plano Business]

---

## E-MAIL 3 — REATIVAÇÃO PÓS-INATIVIDADE (30 dias sem login)
**Assunto:** Você sumiu — e seu DRE está te chamando

---

Olá, [NOME].

Faz [X] dias que você não acessa o Máxima.

Entendo — a rotina de PME é pesada. Mas deixa eu ser direta:

**Cada mês sem analisar o DRE é um mês que você toma decisão no escuro.**

Não precisa de 1 hora. Precisa de 5 minutos.

---

**O que aconteceu na sua empresa no mês passado:**
_(Este bloco pode ser dinâmico se houver dados no perfil do usuário)_

- Você tem [X] análises salvas
- Seu último diagnóstico foi em [DATA]
- A Sofia está esperando sua próxima pergunta

---

**Vamos retomar?**

→ [Abrir o Máxima e fazer upload do DRE de [MÊS]]

Se por algum motivo o produto não está te ajudando, quero saber.
Responda este e-mail com uma palavra: o que travou?

Vou ler pessoalmente.

**Karina**

---

*Se quiser pausar sua assinatura em vez de cancelar, acesse Configurações → Plano → Pausar.*

---

## NOTAS DE IMPLEMENTAÇÃO (para o dev)

| Gatilho | Ferramenta | Campo |
|---|---|---|
| 7 dias após `subscription.created` | Webhook Stripe → Resend | `user.name`, `plan.name` |
| 30 dias após `subscription.created` | Job agendado (Supabase cron) | `user.name`, `analyses_count` |
| 30 dias sem `user_session` | Job agendado | `last_login_date`, `analyses_count` |

**Stack sugerida:** Resend (transacional) + Loops.so (sequências) ou Supabase Edge Functions + Resend direto.

---

*Produzido por Bella — Assistente Autônoma Máxima Finance IA*
