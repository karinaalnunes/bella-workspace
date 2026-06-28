# Seção Página de Vendas — E-mails de Ativação Pós-Cadastro
*Turno da noite — 28/06/2026 | Bella*

---

## CONTEXTO DA SEÇÃO

**Onde entra:** Fluxo de automação de e-mail — acionado automaticamente quando o lead cria conta no plano Gratuito.
**Objetivo:** Transformar o cadastro gratuito em assinatura Pro (R$97/mês) nos primeiros 14 dias.
**Tom:** Parceiro financeiro que fala a língua do empresário — direto, sem jargão, orientado a resultado.

---

## SEQUÊNCIA — 5 E-MAILS / 14 DIAS

---

### E-MAIL 1 — Imediato após cadastro (Dia 0)
**Assunto:** Bem-vindo(a) ao Máxima Finance — 3 coisas para fazer agora

---

Oi, [NOME]!

Você acabou de entrar. Agora o trabalho começa de verdade.

Aqui estão 3 coisas para fazer nos próximos 15 minutos:

**1. Faça upload do seu DRE**
Pode ser o mais recente. PDF, Excel, foto — qualquer formato.
→ [botão: Fazer upload agora]

**2. Leia o diagnóstico da Sofia**
Ela vai te mostrar os 3 números que mais importam no seu resultado.
Não é relatório de contador. É análise em português.

**3. Salve sua senha**
Parece óbvio, mas você vai querer voltar aqui amanhã.

Tem dúvida? Responde esse e-mail. Eu leio tudo.

— Karina Alnunes
Fundadora, Máxima Finance IA

---

P.S.: Se ainda não tem o DRE do último mês, tudo bem. Sobe o de dois meses atrás. O diagnóstico já vai surpreender você.

---

### E-MAIL 2 — Dia 2
**Assunto:** [NOME], seu DRE já está aqui — você viu o que ele diz?

---

[NOME],

A maioria dos empresários que faz upload do DRE tem a mesma reação:

*"Não sabia que estava assim."*

Não porque a empresa vai mal necessariamente.
Mas porque ninguém nunca mostrou os números de forma simples.

O Máxima Finance faz uma coisa:
**Traduzir o DRE para decisões concretas.**

Se você ainda não subiu o seu DRE, clica aqui agora:
→ [botão: Fazer análise gratuita]

Se já fez o upload — parabéns. Você já está à frente de 80% dos donos de PME do Brasil.

Amanhã eu te mando o número que mais empresários ignoram no DRE.

— Karina

---

### E-MAIL 3 — Dia 5
**Assunto:** O número que está devorando sua margem (e você não sabe)

---

[NOME],

Tem um número no DRE que a maioria dos empresários ignora completamente.

Não é o faturamento.
Não é o lucro líquido.

É a **margem de contribuição por produto ou serviço**.

Sabe o que acontece quando você não acompanha isso?

Você descobre que está vendendo muito do que mais te custa e pouco do que mais te rende.

No plano **Máxima Pro** (R$97/mês), a Sofia identifica exatamente isso para você:
- Qual produto ou linha está sustentando a empresa
- Qual está comendo a margem sem você perceber
- E o que fazer para virar isso nos próximos 30 dias

Essa semana, se você assinar o Pro, tem **7 dias de garantia** — se não gostar, devolvemos tudo.

→ [botão: Quero assinar o Pro agora — R$97/mês]

— Karina

---

P.S.: Tem empresa que descobriu, depois de anos, que o produto mais vendido era o que menos rentabilizava. Hoje isso leva 5 minutos para descobrir.

---

### E-MAIL 4 — Dia 9
**Assunto:** Uma pergunta direta, [NOME]

---

[NOME],

Só uma pergunta:

**Você sabe, agora, quanto a sua empresa sobrou no último mês — depois de pagar tudo?**

Não o saldo no banco.
Não o que o contador enviou.
O lucro líquido real, com pró-labore, impostos e reservas no cálculo.

Se a resposta é "não sei ao certo" — o Máxima Finance foi feito para você.

No plano **Pro**, você tem:
✅ Diagnóstico ilimitado de DRE
✅ Chat com a Sofia — perguntas em português, respostas em segundos
✅ Histórico comparativo mês a mês
✅ Alertas automáticos quando um indicador foge do padrão

Tudo por **R$97/mês**.
Menos que uma hora de consultoria financeira.

→ [botão: Assinar Pro — R$97/mês]

Caso queira falar antes de decidir, responde esse e-mail.
Eu respondo pessoalmente.

— Karina

---

### E-MAIL 5 — Dia 14
**Assunto:** Seus 14 dias gratuitos estão chegando ao fim

---

[NOME],

Dois semanas atrás você criou sua conta no Máxima Finance.

Você tem feito a pergunta certa para a sua empresa?

Empresários que usam o Máxima Pro por 30 dias geralmente chegam no segundo mês sabendo:
- O custo real por R$1 faturado
- Qual mês vai ser difícil (antes de chegar nele)
- Por onde cortar sem demitir
- Qual produto/serviço crescer primeiro

O plano gratuito te deu um gostinho.
O Pro te dá o mapa completo.

→ [botão: Assinar Pro agora — R$97/mês — 7 dias de garantia]

Se tiver qualquer dúvida, responde esse e-mail.
Não tem vendedor. Tem a Karina.

— Karina Alnunes
Fundadora, Máxima Finance IA

---

P.S.: Se ainda não é o momento, tudo bem. Sua conta gratuita continua ativa. Mas quando a pergunta for "por onde começo?", o DRE sempre é a resposta — e o Máxima vai continuar aqui.

---

## TOKENS DE DESENVOLVIMENTO

```json
{
  "email_sequence": {
    "trigger": "user_signup_free_plan",
    "emails": [
      {
        "id": "onboarding_d0",
        "delay_hours": 0,
        "subject": "Bem-vindo(a) ao Máxima Finance — 3 coisas para fazer agora",
        "cta_url": "/dashboard/upload",
        "cta_label": "Fazer upload agora"
      },
      {
        "id": "activation_d2",
        "delay_days": 2,
        "subject": "[NOME], seu DRE já está aqui — você viu o que ele diz?",
        "cta_url": "/dashboard/upload",
        "cta_label": "Fazer análise gratuita"
      },
      {
        "id": "education_d5",
        "delay_days": 5,
        "subject": "O número que está devorando sua margem (e você não sabe)",
        "cta_url": "/planos?utm_source=email&utm_campaign=upsell_d5",
        "cta_label": "Quero assinar o Pro agora — R$97/mês"
      },
      {
        "id": "direct_d9",
        "delay_days": 9,
        "subject": "Uma pergunta direta, [NOME]",
        "cta_url": "/planos?utm_source=email&utm_campaign=upsell_d9",
        "cta_label": "Assinar Pro — R$97/mês"
      },
      {
        "id": "urgency_d14",
        "delay_days": 14,
        "subject": "Seus 14 dias gratuitos estão chegando ao fim",
        "cta_url": "/planos?utm_source=email&utm_campaign=upsell_d14",
        "cta_label": "Assinar Pro agora — R$97/mês — 7 dias de garantia"
      }
    ],
    "stop_trigger": "user_upgrades_to_pro",
    "personalization_vars": ["NOME", "empresa_faturamento", "ultimo_dre_data"]
  }
}
```

---

## NOTAS DE IMPLEMENTAÇÃO

- **Ferramenta sugerida:** Resend, Loops.so ou Brevo (integração nativa com Supabase)
- **Personalização:** Usar `user.name` do Supabase Auth; opcional: `company_name` do onboarding
- **UTM tracking:** Cada e-mail com parâmetro único para rastrear conversão por e-mail
- **Suppression:** Cancelar sequência automaticamente ao detectar `plan = 'pro'` ou `plan = 'business'` no Supabase
- **Horário de envio:** E-mails 1 e 2 sem delay; 3, 4 e 5 idealmente às 8h (horário de Brasília) no dia configurado
