# Página de Vendas — Seção: Página de Obrigado (Thank You Page)
*Produzido por Bella — Turno da Noite 12/05/2026*

---

## CONTEXTO DE USO

Esta página é exibida **imediatamente após o cadastro** (gratuito ou pago).
Objetivo duplo: ativar o usuário no produto + semear a conversão para plano pago.

---

## ESTRUTURA COMPLETA

---

### [1] HEADER — CONFIRMAÇÃO + CELEBRAÇÃO

```
Você entrou. Agora sua empresa vai ter o que poucos têm.

Bem-vindo(a) ao Máxima Finance IA, [Nome].

Seu acesso está ativo. Em menos de 5 minutos você vai ter
o diagnóstico financeiro que seu contador nunca te deu.
```

*Visual sugerido: ícone de check verde animado + nome do usuário dinâmico*

---

### [2] O QUE ACONTECE AGORA — 3 PASSOS

```
Três passos para o seu primeiro diagnóstico:

① Acesse o painel → botão "Ir para o Dashboard"
② Faça upload do seu DRE (Excel, PDF ou planilha)
③ A Sofia analisa e te entrega o diagnóstico em linguagem simples

Leva menos de 5 minutos. Faça agora.

[BOTÃO] → Ir para o Dashboard  ←  CTA principal
```

---

### [3] GANCHO DO PLANO PRO — UPSELL SUTIL (para cadastros no plano gratuito)

```
No plano gratuito você já tem acesso à análise básica do DRE.

Mas se você quiser saber:
✔ Por que sua margem caiu nos últimos 3 meses
✔ Quais despesas estão destruindo o seu lucro
✔ O que fazer diferente no próximo trimestre

Isso é Pro.

Empresários que usam o plano Pro tomam decisões com 2 semanas de antecedência.
Os do gratuito descobrem o problema quando o dinheiro já foi.

[BOTÃO SECUNDÁRIO] → Conhecer o Plano Pro — R$97/mês
```

*(não exibir este bloco para quem já contratou o plano Pro ou Business)*

---

### [4] PROVA SOCIAL RÁPIDA — 1 DEPOIMENTO

```
"Eu achava que sabia como estava minha empresa.
Depois do diagnóstico da Sofia, descobri que estava
pagando R$ 8.400 por mês em despesas que eu nem rastreava.
Cortei. Recuperei a margem em 45 dias."

— Ricardo M., dono de distribuidora, SP
```

*Visual: foto fictícia ou avatar + nome + segmento*

---

### [5] GARANTIA — REFORÇO PÓS-COMPRA (para planos pagos)

```
Você tem 7 dias para testar sem nenhum risco.

Se a Sofia não te entregar pelo menos 1 insight financeiro
que você não sabia, peça reembolso.
Sem formulário. Sem burocracia. Palavra de quem construiu isso.

— Karina Alnunes, fundadora do Máxima Finance IA
```

*(exibir apenas para planos Pro e Business)*

---

### [6] PRÓXIMA AÇÃO — CTA FINAL

```
Seu diagnóstico está esperando você.

[BOTÃO PRINCIPAL] → Fazer meu primeiro upload agora
```

*Micro-copy abaixo do botão:*
```
Aceita DRE em Excel, PDF ou planilha do Google Sheets.
Qualquer período. Qualquer segmento.
```

---

### [7] RODAPÉ DA THANK YOU PAGE

```
Dúvidas? Fale com a Sofia direto no chat do painel.
Ela responde em segundos — e não julga pergunta básica.

Ou nos chame: suporte@maximafinance.com.br
```

---

## NOTAS PARA O DEV

| Elemento | Comportamento |
|---|---|
| `[Nome]` no header | Dinâmico — puxa do Supabase Auth |
| Bloco de upsell Pro | Condicional — ocultar se plano_id ≠ gratuito |
| Bloco de garantia | Condicional — exibir apenas se plano_id = pro ou business |
| Botão principal | Redireciona para `/dashboard` |
| Botão upsell | Redireciona para `/planos#pro` |
| Analytics | Disparar evento `thank_you_page_viewed` + `plan_type` no momento do load |

---

## POR QUE ESTA SEÇÃO É CRÍTICA

A thank you page é o momento de **maior receptividade** do usuário — ele acabou de tomar uma decisão.
Ignorar essa janela é deixar dinheiro na mesa.

- Usuário ativo no produto nas primeiras 24h → **3x mais chance de converter para pago**
- Upsell no momento pós-cadastro converte **2–5x mais** do que e-mail enviado depois
- A garantia reforçada pós-compra **reduz churn** nos primeiros 7 dias

*Implemente antes do primeiro anúncio pago. Tráfego sem Thank You Page otimizada = torneira aberta com ralo aberto.*
