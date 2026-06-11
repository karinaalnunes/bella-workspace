# Máxima Finance IA — Campanha de Meio de Ano
*Seção: Kit de Peças "Revisão Semestral" — E-mail + SMS + Stories + Push Notification*
*Produzido por Bella — Turno da Noite — 11/06/2026*

---

## CONTEXTO ESTRATÉGICO

**Timing:** Junho é o mês em que empresários naturalmente fazem balanço — "o que aconteceu nos últimos 6 meses?" Essa janela de intenção é ouro para prospecção e conversão. Nenhum concorrente está aproveitando esse gatilho agora. A Máxima está.

**Objetivo desta campanha:** Capturar leads quentes (empresários em modo revisão) e converter trials/leads frios que estão estagnados no funil.

---

## PEÇA 1 — E-MAIL CAMPANHA DE MEIO DE ANO
**Assunto:** Metade do ano foi. Você sabe o que sobrou?

---

[NOME],

Amanhã começa a segunda metade de 2026.

Mas antes de planejar o que vem por aí, tem uma pergunta que precisa de resposta:

**Você sabe exatamente o que os últimos 6 meses deixaram para trás?**

Não o faturamento. Não o saldo do banco.

O lucro real. A margem real. O custo que cresceu sem você perceber.

A maioria dos empresários chega em junho com uma sensação: "trabalhei muito, faturei bem — mas o dinheiro some."

Essa sensação tem nome. E o DRE mostra com precisão de onde ela vem.

---

**É exatamente para isso que a Máxima Finance IA existe.**

Em menos de 5 minutos você carrega o DRE do 1º semestre e recebe:

✅ Diagnóstico dos 5 indicadores que mais impactam sua margem
✅ Comparativo mês a mês — onde cresceu e onde sangrou
✅ 3 ações práticas para o 2º semestre (não teorias — ações)
✅ Chat com Sofia, sua IA financeira — tire dúvidas em linguagem simples

---

**Só em junho:** acesse o plano Pro por 7 dias grátis. Sem cartão. Sem compromisso.

👉 [BOTÃO: Quero minha revisão semestral grátis]

*"Melhor decisão que tomei foi parar de olhar só o extrato bancário." — Empresária do varejo, SP*

— Karina
Fundadora, Máxima Finance IA

---

## PEÇA 2 — SMS / WHATSAPP (curto, para base de leads frios)

> 🗓️ Metade do ano foi.
> Seu DRE sabe o que sobrou — você sabe?
> 7 dias grátis no Máxima Finance IA para descobrir antes do 2º semestre começar.
> → [LINK]

*(160 caracteres. Funciona como SMS ou mensagem WhatsApp.)*

---

## PEÇA 3 — STORY INSTAGRAM (sequência 3 slides)

**Slide 1 — Gancho**
> Caixa cheio não significa lucro.
> (e o DRE prova isso em 5 minutos)

*[Visual: fundo escuro, fonte grande, sem foto. Texto como gancho único.]*

---

**Slide 2 — Dor**
> Você chegou em junho e não sabe responder:
>
> ❓ Qual produto te deu mais margem no 1º sem?
> ❓ Qual despesa cresceu mais que o faturamento?
> ❓ Você está no lucro ou no ilusório faturamento?
>
> Se não sabe responder, o DRE sabe.

*[Visual: fundo escuro. Perguntas com espaço entre elas. Sem imagens.]*

---

**Slide 3 — CTA com urgência**
> Revisão de Meio de Ano com IA.
> 7 dias grátis. Só em junho.
>
> 👆 Link na bio → Máxima Finance IA

*[Visual: CTA em destaque. Cor de contraste.]*

---

## PEÇA 4 — PUSH NOTIFICATION IN-APP (para usuários do plano gratuito)

**Título:** Metade do ano foi — sua margem sobreviveu?
**Texto:** Faça a revisão semestral agora. Upgrade Pro com 7 dias grátis só em junho.
**CTA:** Ver minha análise

*(Disparar: 11/06 às 19h → 14/06 às 10h se não converteu → 30/06 às 17h última chamada)*

---

## PEÇA 5 — BANNER DENTRO DO APP (plano gratuito)

```
┌─────────────────────────────────────────────────────────────────┐
│  📊  REVISÃO DE MEIO DE ANO                                     │
│                                                                  │
│  Você chegou até aqui. Mas sabe quanto sobrou de verdade?       │
│                                                                  │
│  Com o Pro você vê a análise completa do 1º semestre em 5 min. │
│                                                                  │
│  [Quero ver minha análise →]          Oferta válida até 30/jun  │
└─────────────────────────────────────────────────────────────────┘
```

---

## PEÇA 6 — SUBJECT LINES ALTERNATIVAS (teste A/B)

| # | Assunto | Ângulo |
|---|---|---|
| A | Metade do ano foi. Você sabe o que sobrou? | Curiosidade + urgência |
| B | Seu 1º semestre em 5 minutos (antes que comece o 2º) | Velocidade + praticidade |
| C | O número que todo empresário deveria ver agora | Mistério + FOMO |
| D | Trabalhei 6 meses — lucrei quanto de verdade? | Identificação + dor |
| E | A revisão semestral que o contador não vai te dar | Autoridade + gap de mercado |

**Recomendação:** Testar A vs. D na base fria. C vs. E para leads engajados.

---

## CRONOGRAMA DE DISPARO

| Data | Peça | Canal | Segmento |
|---|---|---|---|
| 11/06 (hoje) | Push notification | In-app | Usuários free ativos nos últimos 30 dias |
| 12/06 | E-mail completo (Peça 1) | E-mail | Base total |
| 12/06 | Story (Peça 3) | Instagram | Público orgânico |
| 14/06 | SMS/WhatsApp (Peça 2) | WhatsApp | Leads frios (sem abertura em 30 dias) |
| 14/06 | Banner in-app (Peça 5) | App | Todos os free |
| 21/06 | Reenvio do e-mail (assunto D) | E-mail | Não-abridores do dia 12 |
| 28/06 | Último aviso — oferta encerra 30/06 | E-mail + WhatsApp | Não-convertidos |

---

## TOKENS PARA DEV

```typescript
// Campanha de Meio de Ano — flags e lógica de exibição

// Mostrar banner in-app apenas para plano gratuito e período da campanha
const showMidYearBanner = 
  userPlan === 'free' && 
  isWithinDateRange('2026-06-11', '2026-06-30');

// Segmento para push notification
const midYearPushSegment = {
  plan: 'free',
  lastActive: { gte: subDays(new Date(), 30) },
  convertedToProAfterJune11: false
};

// Coupon Stripe para a campanha
const coupon = 'REVISAO_SEMESTRAL_JUNHO';
// trial_period_days: 7, valid_until: '2026-06-30'

// Rota de destino do CTA da campanha
const campaignCTARoute = '/upgrade?promo=revisao-semestral&utm_campaign=junho2026';
```

---

## POR QUE ESSA CAMPANHA AGORA

1. **Timing natural:** Empresários fazem revisão semestral em junho — intenção de compra alta
2. **Concorrência parada:** Nenhum concorrente está capitalizando esse momento com IA
3. **Urgência real:** 2º semestre começa e quem não agiu ficou para trás
4. **Reativação + aquisição:** Funciona para leads frios E para novos visitantes orgânicos
5. **Baixo custo:** Nenhuma peça precisa de anúncio — orgânico + CRM + in-app

---

*Bella — Turno da Noite — 11/06/2026*
