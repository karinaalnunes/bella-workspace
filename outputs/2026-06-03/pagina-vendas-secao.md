# Página de Vendas — Seção: E-mails Pós-Compra do Webinar (Novos Clientes D+0 / D+1 / D+3)
*Produzido por Bella — Turno da noite 03/06/2026*

---

## CONTEXTO

Hoje foi o webinar de lançamento (03/jun, 20h). Quem comprou durante o evento precisa receber onboarding imediato para ativar e ter resultado rápido — isso reduz churn e gera prova social. Esta sequência cobre os 3 primeiros dias do novo cliente.

---

## E-MAIL 1 — D+0 (imediato, após confirmação de pagamento Stripe)

**Assunto:** Bem-vindo(a) ao Máxima Finance IA — seu acesso está pronto 🎉  
**Preview:** Você acaba de tomar a melhor decisão financeira do semestre.

---

Olá, [NOME]!

Você acabou de dar o passo que a maioria dos empresários demora anos para dar.

A partir de agora, você tem acesso ao **Máxima Finance IA** — a ferramenta que transforma qualquer DRE em decisões claras, sem precisar de contador, planilha ou MBA.

**Seu acesso:**
→ Link: [URL_DO_APP]  
→ Login: [EMAIL]  
→ Senha provisória: [SENHA_PROVISÓRIA]

---

**Seu primeiro passo (leva menos de 5 minutos):**

1. Acesse o app pelo link acima  
2. Faça o upload do DRE do mês passado (PDF ou planilha)  
3. Aguarde a análise da Sofia (nossa IA) — ela vai te entregar o diagnóstico em segundos  

Se você não tiver o DRE agora, tudo bem — pode fazer upload de qualquer período. O app aceita dados dos últimos 36 meses.

---

**Bônus do webinar que você ganhou:**
- ✅ [BÔNUS 1: nome]
- ✅ [BÔNUS 2: nome]
- ✅ [BÔNUS 3: nome]

Esses bônus já estão disponíveis na sua área de membros.

---

Qualquer dúvida, responda este e-mail ou fale com a Sofia diretamente no chat do app. Ela está lá para isso.

Bem-vindo(a) à Máxima. Agora você vai saber, de verdade, quanto sobra.

Karina Alnunes  
Fundadora — Máxima Finance IA

---
*Você recebeu este e-mail porque comprou o Máxima Finance IA durante o webinar de 03/06/2026. [Acesse sua conta](URL)*

---
**Tokens Dev:**
- Gatilho: `stripe.checkout.session.completed` + `plan ≠ free`
- Template ID: `welcome_buyer_webinar`
- Variáveis: `{{first_name}}`, `{{app_url}}`, `{{login_email}}`, `{{temp_password}}`, `{{bonus_1_name}}`, `{{bonus_2_name}}`, `{{bonus_3_name}}`
- Delay: 0 min (imediato)
- Tabela Supabase: `profiles.onboarding_step = 'email_sent'`

---

## E-MAIL 2 — D+1 (24h após a compra)

**Assunto:** Você já fez o upload? [NOME], essa é a parte mais importante  
**Preview:** 87% dos nossos clientes que fazem o primeiro upload nos primeiros 24h chegam ao resultado em menos de uma semana.

---

Olá, [NOME]!

Ontem você tomou uma decisão importante. Hoje é hora de dar o segundo passo.

Se você ainda não fez o upload do seu DRE, este é o momento.

---

**Por que o primeiro upload é tão importante?**

A Sofia precisa de dados reais da sua empresa para te entregar um diagnóstico personalizado. Sem o upload, ela só consegue te mostrar demonstrações.

Com o upload, em menos de 60 segundos você vai saber:
- Qual é a sua margem bruta real (não o que você acha que é)
- Onde o dinheiro está sumindo
- Quais linhas do DRE estão puxando o resultado para baixo

---

**Se você travar em alguma etapa:**

→ O DRE precisa estar em PDF ou Excel (.xlsx)  
→ Pode ser do mês passado, do trimestre ou do ano inteiro  
→ Se o seu contador enviar em outro formato, [clique aqui para ver os formatos aceitos](URL)

---

**Uma dica que ninguém te conta:**

O segundo DRE que você analisa é sempre mais revelador que o primeiro. Porque no segundo, você já sabe o que procurar — e começa a ver padrões que o seu negócio repete todo mês.

Acesse agora: [BOTÃO — Fazer meu primeiro upload]

Qualquer dúvida, a Sofia responde no chat do app.

Karina

---
**Tokens Dev:**
- Gatilho: `D+1 após compra` + `profiles.onboarding_step ≠ 'first_upload_done'`
- Template ID: `onboarding_d1_no_upload`
- Variáveis: `{{first_name}}`, `{{app_url}}`
- Delay: 24h após `checkout.session.completed`
- Condição de parada: se `first_upload_done = true` → skip e-mail

---

## E-MAIL 3 — D+3 (72h após a compra)

**Assunto:** [NOME], vi que você está explorando o app — aqui vai uma dica avançada  
**Preview:** A função que 9 em 10 clientes ignoram nos primeiros dias (mas que faz toda a diferença no mês 2).

---

Olá, [NOME]!

Você já está dentro do Máxima há 3 dias. Isso é ótimo — os clientes que chegam até aqui quase sempre ficam.

Hoje quero te mostrar algo que vai além do diagnóstico inicial.

---

**A função que todo empresário deveria usar primeiro: o Chat com a Sofia**

A maioria dos novos clientes faz o upload, vê o diagnóstico e para por aí. Mas o maior valor do Máxima não é a análise automática — é a conversa.

A Sofia foi treinada para responder perguntas como:

- *"Sofia, por que minha margem caiu de 28% para 19% em março?"*
- *"Sofia, se eu contratar mais 2 funcionários, qual o impacto no ponto de equilíbrio?"*
- *"Sofia, meu resultado financeiro está positivo mas o caixa está no negativo — o que está acontecendo?"*

Ela cruza os dados do seu DRE com o contexto do seu setor e responde em português claro, sem jargão contábil.

---

**Pergunta de presente para você começar:**

Abra o chat e pergunte:

> *"Sofia, quais são os 3 pontos mais críticos do meu DRE agora?"*

Você vai se surpreender com a resposta.

[BOTÃO — Falar com a Sofia agora]

---

Se tiver alguma dúvida sobre o plano, bônus ou quiser fazer upgrade para o Business, basta responder este e-mail.

Karina

P.S.: Sua oferta do webinar (com os bônus exclusivos) está garantida. Se quiser indicar um colega empresário, [clique aqui para ver o programa de indicação](URL_REFERRAL) — você ganha créditos na plataforma para cada indicação que virar cliente.

---
**Tokens Dev:**
- Gatilho: `D+3 após compra`
- Template ID: `onboarding_d3_engagement`
- Variáveis: `{{first_name}}`, `{{app_url}}`, `{{referral_url}}`
- Delay: 72h após `checkout.session.completed`
- Condição de parada: nenhuma (enviar sempre)
- Ação pós-envio: `profiles.onboarding_step = 'd3_email_sent'`

---

## RESUMO DA SEQUÊNCIA

| E-mail | Quando | Objetivo | Condição de parada |
|---|---|---|---|
| D+0 — Boas-vindas | Imediato após compra | Ativar acesso + entregar bônus | Nenhuma |
| D+1 — Primeiro upload | 24h após compra | Converter visitante em usuário ativo | `first_upload_done = true` |
| D+3 — Chat Sofia | 72h após compra | Aprofundar engajamento + mostrar valor central | Nenhuma |

---

## MÉTRICAS DE SUCESSO (benchmark SaaS B2B)

- Taxa de abertura alvo: D+0 >75% / D+1 >45% / D+3 >35%
- Taxa de clique alvo: D+0 >40% / D+1 >20% / D+3 >15%
- Taxa de ativação (primeiro upload em 72h): alvo >60%
- Churn 30d de compradores sem upload: esperado >40% → objetivo: reduzir para <15%
