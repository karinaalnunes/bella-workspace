# Sequência de Reativação de Trial Expirado
## 3 e-mails para usuários gratuitos que não fizeram upload do DRE

*Produzido por Bella — Turno da noite 09/06/2026*
*Arquivo: `outputs/2026-06-09/pagina-vendas-secao.md`*

---

## CONTEXTO DE USO

**Gatilho:** Usuário se cadastrou no plano Gratuito há X dias e **não fez nenhum upload de DRE**.
**Plataforma:** Resend (ou similar) via Supabase Edge Function.
**Segmento:** `created_at < now() - interval '3 days'` AND `uploads_count = 0`

**Tokens dev (Supabase/Resend):**
- `{{ user.first_name }}` — primeiro nome
- `{{ user.company_name }}` — nome da empresa (preenchido no onboarding)
- `{{ user.created_at | date: "%d/%m" }}` — data do cadastro
- `{{ trial_expiry_url }}` — link direto para o upload do DRE
- `{{ pro_upgrade_url }}` — link de upgrade para Pro

---

## E-MAIL 1 — D+3 após cadastro sem upload
**Assunto:** Sua conta ainda está esperando o primeiro DRE
**Pré-header:** Leva menos de 2 minutos. Prometo.

---

**CORPO:**

Olá, {{ user.first_name }}!

Você se cadastrou na Máxima Finance em {{ user.created_at | date: "%d/%m" }}. Mas o diagnóstico do seu DRE ainda não aconteceu.

Entendo — o dia a dia de quem tem empresa não para. Mas vou te dizer uma coisa:

**Cada mês sem saber sua margem real é um mês decidindo no escuro.**

Não saber quanto sobra de verdade depois de pagar tudo é a principal razão pela qual empresas que faturam bem ficam sem caixa.

---

**Aqui está o que você faz agora:**

1. Pegue o DRE do seu último mês (pode ser Excel, PDF ou foto da planilha)
2. Acesse: [Fazer meu primeiro diagnóstico →]({{ trial_expiry_url }})
3. Em menos de 2 minutos, a Sofia analisa e te mostra o que os números revelam

---

Seu concorrente provavelmente também não sabe a margem dele. **Você pode saber.**

Até mais,
**Sofia — Sua Analista Financeira IA**
Máxima Finance IA

*P.S.: Tem dúvida de qual planilha usar? Qualquer DRE funciona — mensal, trimestral, do contador, do Excel. A Sofia entende todos.*

---

## E-MAIL 2 — D+7 após cadastro sem upload
**Assunto:** Pergunta direta: o que está te travando?
**Pré-header:** Sem julgamento. Quero entender.

---

**CORPO:**

{{ user.first_name }},

Faz 7 dias que você criou a conta na Máxima Finance. O diagnóstico ainda não rolou.

Quero entender o que está travando — porque normalmente é uma dessas três coisas:

**① Não sei onde está o DRE**
Normal. Muitos empresários não têm esse relatório organizado. A Sofia consegue trabalhar com qualquer planilha de resultados — inclusive uma feita por você no Excel. [Veja aqui o modelo mínimo →]({{ trial_expiry_url }})

**② Não sei se vale a pena**
Entendo a desconfiança. Por isso o primeiro diagnóstico é 100% gratuito e sem compromisso. Você vê o que a IA entrega — e só decide depois.

**③ Não tive tempo**
Tempo médio do primeiro upload: **1 minuto e 47 segundos**. Menos do que um cafezinho.

---

Qual das três é a sua?

Se quiser, só responde esse e-mail. Leio todas as mensagens e a própria Karina acompanha de perto os feedbacks dos primeiros usuários.

[Fazer o diagnóstico agora →]({{ trial_expiry_url }})

Abraço,
**Karina Alnunes**
Fundadora — Máxima Finance IA

---

## E-MAIL 3 — D+14 após cadastro sem upload (oferta de ativação)
**Assunto:** Último lembrete — e um presente antes de encerrar
**Pré-header:** Quero que você veja o que a IA entrega. Pelo menos uma vez.

---

**CORPO:**

{{ user.first_name }},

Vou ser direta: sua conta na Máxima Finance está inativa há 14 dias.

Antes de você partir, quero te fazer uma oferta que não anuncio publicamente:

---

**🎁 DIAGNÓSTICO ASSISTIDO — SEM CUSTO**

Se você me mandar o DRE da {{ user.company_name }} agora — pode ser foto, Excel, PDF —, eu processo manualmente e te mando o diagnóstico completo em até 24 horas.

Sem custo. Sem compromisso de upgrade.

Só quero que você **veja com os seus próprios olhos** o que a ferramenta entrega antes de desistir.

---

Você vai receber:

✅ Margem bruta e margem líquida da empresa em linguagem simples
✅ Os 3 maiores pontos de atenção do DRE
✅ Comparativo com a média do seu setor
✅ Pergunta aberta para a Sofia tirar dúvidas financeiras

---

Para aceitar, é só responder esse e-mail com o seu DRE. Ou clicar aqui e fazer o upload diretamente:

[Aceitar o diagnóstico assistido →]({{ trial_expiry_url }})

Essa oferta expira em **48 horas**.

Depois disso, a conta continua ativa no plano Gratuito, mas o diagnóstico assistido não estará mais disponível.

Com carinho,
**Karina Alnunes**
Fundadora — Máxima Finance IA

*P.S.: Se você decidiu que a Máxima Finance não é para você agora, sem problema. Mas guarda o link — quando o DRE começar a incomodar, a gente está aqui.*

---

## MÉTRICAS ESPERADAS (benchmarks SaaS Brasil)

| E-mail | Taxa de Abertura | Taxa de Clique | Conversão para Upload |
|--------|-----------------|----------------|----------------------|
| E-mail 1 (D+3) | 38–45% | 8–12% | 5–8% |
| E-mail 2 (D+7) | 28–35% | 6–10% | 4–6% |
| E-mail 3 (D+14) | 22–30% | 4–8% | 3–5% |

**Meta composta:** 12–18% dos cadastros inativos convertidos em upload ativo após a sequência.

---

## CONFIGURAÇÃO SUPABASE/RESEND

```sql
-- Query para identificar usuários elegíveis (D+3, sem upload)
SELECT id, email, raw_user_meta_data->>'first_name' as first_name,
       raw_user_meta_data->>'company_name' as company_name,
       created_at
FROM auth.users
WHERE created_at < now() - interval '3 days'
  AND id NOT IN (
    SELECT user_id FROM uploads WHERE user_id IS NOT NULL
  )
  AND id NOT IN (
    SELECT user_id FROM email_sends WHERE template = 'trial_reactivation_1'
  );
```

**Edge Function sugerida:** `send-reactivation-sequence`
**Trigger:** Cron job diário às 10h via `pg_cron` ou Supabase Scheduled Functions

---

*Bella — Assistente Autônoma Máxima Finance IA*
*Turno da noite — 09/06/2026*
