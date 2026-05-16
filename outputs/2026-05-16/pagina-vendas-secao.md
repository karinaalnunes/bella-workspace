# Página de Vendas — Seção: Programa de Indicação (Referral)
*Turno da noite — 16/05/2026 | Bella*

---

## CONTEXTO DE USO

Inserir esta seção **após** a Thank You Page (pós-cadastro) e também como módulo dentro do painel do usuário logado (dashboard). Objetivo: transformar clientes satisfeitos em canal de aquisição orgânica — especialmente relevante no segmento PME onde a indicação de contador, parceiro de negócio ou grupo de empresários tem alto peso.

---

## SEÇÃO: INDIQUE E GANHE

### Headline principal
**Você economizou. Agora ajuda um amigo a economizar também.**

### Subheadline
Indique a Máxima Finance para outros empresários e os dois ganham.

---

### Bloco de benefícios (card visual)

```
┌─────────────────────────────────────────────┐
│  💜  PROGRAMA DE INDICAÇÃO MÁXIMA FINANCE   │
│                                             │
│  Você indica →  amigo assina → vocês dois   │
│               ganham 1 mês grátis           │
│                                             │
│  Sem limite de indicações.                  │
│  Cada indicação que vira assinante =        │
│  +1 mês grátis na sua conta.               │
└─────────────────────────────────────────────┘
```

---

### Como funciona (3 passos)

**1. Copie seu link exclusivo**
Cada conta tem um link único. Compartilhe com quem você quiser — WhatsApp, grupo de empresários, LinkedIn, de boca em boca.

**2. Seu amigo experimenta grátis por 14 dias**
Quando ele se cadastrar pelo seu link, começa com 14 dias de acesso ao plano Pro — sem cartão.

**3. Ele assinou? Os dois ganham 1 mês grátis**
Quando a assinatura do seu amigo confirmar, você ganha 1 mês grátis automaticamente. E ele também.

---

### Copy do bloco de link (dentro do painel)

```
SEU LINK DE INDICAÇÃO:
maximafinance.com.br/ref/[código]

[  COPIAR LINK  ]   [  COMPARTILHAR NO WHATSAPP  ]

Indicações realizadas: 0
Assinaturas confirmadas: 0
Meses grátis acumulados: 0
```

---

### Mensagem pronta para WhatsApp (copy sugerido no painel)

> "Oi! Eu tô usando uma ferramenta que analisa o DRE da minha empresa com IA e explica o resultado em português simples — sem precisar de contador.
>
> Te manda um diagnóstico completo: onde tá sangrando, onde dá pra melhorar, o que fazer primeiro.
>
> Você pode testar 14 dias grátis pelo meu link:
> maximafinance.com.br/ref/[código]
>
> Se você assinar, a gente ganha um mês grátis cada um."

---

### FAQ do Programa de Indicação

**Tem limite de indicações?**
Não. Você pode indicar quantos empresários quiser. Cada assinatura confirmada = +1 mês grátis.

**O amigo precisa usar cartão para testar?**
Não. Os 14 dias de teste são completamente grátis, sem cartão cadastrado.

**Quando recebo o mês grátis?**
Assim que o pagamento do seu amigo for confirmado (geralmente em até 24h após o trial terminar).

**Posso acumular meses grátis?**
Sim. Se você indicar 3 pessoas e as 3 assinarem, você recebe 3 meses grátis — usados em sequência.

**O programa tem prazo de validade?**
O link não expira. Mas o período de trial do amigo começa no momento do cadastro.

**Vale para plano Gratuito também?**
O bônus de 1 mês grátis é creditado no plano Pro. Se você estiver no Gratuito, o mês será reservado e ativado quando você fizer upgrade.

---

### Microcopy de urgência / reforço social

> *"Mais de [X] empresários já descobriram o que o DRE deles estava escondendo. Agora é a vez do seu amigo."*

*(Preencher X com número real de usuários cadastrados — atualizar dinamicamente)*

---

### CTA final da seção

```
[  COPIAR MEU LINK AGORA  ]
```
*Cada indicação que assinar = 1 mês grátis. Sem limite.*

---

## TOKENS PARA DEV

```
{{referral_link}}       — link único do usuário logado
{{referral_count}}      — total de indicações feitas
{{confirmed_signups}}   — indicações que viraram assinatura
{{free_months_earned}}  — meses grátis acumulados
{{whatsapp_share_url}}  — link pré-formatado para WhatsApp
```

---

## NOTAS DE IMPLEMENTAÇÃO

- **Stripe:** Usar `coupon` + `promotion_code` para aplicar mês grátis automaticamente via webhook `customer.subscription.created` com `referral_code` no metadata.
- **Supabase:** Tabela `referrals (id, referrer_id, referee_id, status, created_at)` — status: `pending` → `confirmed` → `rewarded`.
- **Edge Function:** Ao confirmar pagamento do amigo → atualizar status → criar cupom de 1 mês grátis no Stripe para o indicador.
- **Analytics:** Rastrear `referral_link_copied`, `whatsapp_share_clicked`, `referral_signup`, `referral_converted`.
