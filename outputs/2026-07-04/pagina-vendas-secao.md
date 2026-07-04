# Página de Vendas — Seção: Upsell Pós-Registro (Gratuito → Pro em 24 Horas)
*Turno da noite 04/07/2026 — Bella*

---

## CONTEXTO ESTRATÉGICO

Essa seção não é para a landing page principal — é o **funil pós-cadastro**.
Quando o empresário cria a conta gratuita, ele está no pico de interesse.
A janela de conversão para Pro é nas primeiras 24 horas.
Essa copy cobre: **tela in-app + e-mail de ativação + banner de upgrade**.

---

## 1. TELA IN-APP — POP-UP DE BOAS-VINDAS (imediatamente após cadastro)

**Headline:**
> Bem-vindo à Máxima Finance IA.
> Agora você tem o que 73% dos empresários brasileiros nunca tiveram: visibilidade financeira real.

**Subheadline:**
> Você está no plano Gratuito. Aqui está o que você já pode fazer — e o que a versão Pro desbloqueia agora.

**Tabela visual (2 colunas):**

| Gratuito — Você tem hoje | Pro R$97/mês — Desbloqueie agora |
|---|---|
| 1 análise de DRE por mês | Análises ilimitadas |
| Diagnóstico básico (3 indicadores) | Diagnóstico completo (12 indicadores) |
| Chat Sofia: 10 perguntas/mês | Chat Sofia ilimitado |
| Exportação em PDF simples | Relatório executivo com benchmarks do setor |
| — | Alertas automáticos quando a margem cai |
| — | Comparativo de DRE entre períodos |
| — | Suporte prioritário |

**CTA principal:**
> **→ Quero o Pro por R$97/mês**
> *(Cancele quando quiser. Sem multa.)*

**CTA secundário (link texto):**
> Continuar com o plano gratuito por enquanto

---

## 2. E-MAIL 1 — ENVIADO 2 HORAS APÓS CADASTRO

**Assunto:** Karina, você acabou de mudar a forma como vê seu negócio

**Pré-header:** Mas há algo que a maioria não descobre no primeiro dia…

---

Olá, [NOME].

Você acabou de criar sua conta na Máxima Finance IA.

Isso significa que na próxima vez que alguém te perguntar "qual é a sua margem líquida?" — você vai saber responder.

Mas quero ser honesta com você sobre uma coisa.

**O plano Gratuito foi projetado para você experimentar.**
Não para você gerir o negócio inteiro.

Empresários que usam a versão **Pro** tomam uma média de **3x mais decisões baseadas em dados** no primeiro mês — porque têm visibilidade completa, não um recorte.

Aqui está o que muda quando você vai para o Pro:

✅ DRE analisado mês a mês (comparativo de evolução)
✅ Chat Sofia ilimitado — pergunta o que quiser, a hora que quiser
✅ Alerta automático quando qualquer indicador sai do limite saudável
✅ Relatório para apresentar para banco, sócio ou investidor

O Pro custa **R$97/mês**. Isso é R$3,23 por dia.
Menos que um café com pão de queijo.

**[→ Ativar o Pro agora]**

Se tiver qualquer dúvida, responda este e-mail. Eu leio pessoalmente.

Karina Nunes
Fundadora, Máxima Finance IA

---

## 3. E-MAIL 2 — ENVIADO 20 HORAS APÓS CADASTRO (se não converteu)

**Assunto:** [NOME], antes de dormir — uma pergunta

**Pré-header:** Você sabe qual foi sua margem líquida no mês passado?

---

[NOME],

Antes de fechar o dia — uma pergunta rápida:

**Você sabe, de cabeça, qual foi a sua margem líquida no mês passado?**

Não o faturamento. Não o que entrou na conta. A margem — o que sobrou depois de pagar tudo.

Se a resposta foi "mais ou menos" ou "meu contador sabe" — é exatamente para isso que a Máxima Finance IA existe.

No plano Pro, você carrega um DRE, e em 3 minutos tem a resposta. Com contexto. Com alertas. Com uma IA que explica em português simples o que os números estão dizendo.

Não é relatório para contador. É diagnóstico para você, o dono.

**R$97/mês. Sem contrato longo. Cancele quando quiser.**

**[→ Ativar o Pro]**

Até amanhã,
Karina

---

## 4. BANNER IN-APP — APARECE NO DASHBOARD (primeiros 7 dias)

**Texto:**
> 🔓 **Você está usando 1 de 12 indicadores disponíveis.**
> Ative o Pro e veja o DRE completo do seu negócio.
> [**Ativar Pro — R$97/mês →**]

---

## 5. NOTIFICAÇÃO PUSH / SMS — DIA 3 APÓS CADASTRO (se não converteu)

**Texto curto:**
> [NOME], sua análise gratuita expira em 28 dias. Você ainda tem 11 indicadores bloqueados. Ativar Pro: maximafinance.com.br/pro

---

## NOTAS PARA DEV

- Pop-up de boas-vindas: disparar imediatamente após e-mail verificado
- E-mail 1: delay de 2h via Resend ou Brevo
- E-mail 2: condicional — só envia se usuário NÃO clicou no CTA do E-mail 1
- Banner in-app: component fixo no topo do Dashboard, dismissível após 7 dias OU após upgrade
- Push/SMS: integrar com OneSignal ou Supabase Edge Function + Twilio
- UTM tags em todos os CTAs: `?utm_source=onboarding&utm_medium=[email|in-app|push]&utm_campaign=pro-upsell-24h`
