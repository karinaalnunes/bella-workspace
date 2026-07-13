# Página de Vendas — Seção: Upsell Pós-Cadastro (Upgrade para Pro)
*Turno da noite — 13/07/2026 | Bella*

---

## CONTEXTO DE USO

Esta página aparece **imediatamente após o empresário criar a conta gratuita**.
Objetivo: converter para o plano Pro (R$97/mês) enquanto a motivação está no pico.

---

## COPY — PÁGINA DE UPSELL

---

### HEADLINE PRINCIPAL

**Você já deu o passo mais difícil.**
**Agora deixa a Máxima Finance IA trabalhar de verdade por você.**

---

### SUBHEADLINE

Sua conta gratuita está ativa. Mas tem uma coisa que separar o empresário que só **vê os números** do que **age sobre eles** — e você pode ter isso hoje.

---

### BLOCO DE TENSÃO (O QUE A CONTA GRÁTIS NÃO FAZ)

No plano gratuito você vai conseguir:
- ✅ Fazer upload de 1 DRE
- ✅ Ver o diagnóstico básico da Sofia

Mas não vai conseguir:
- ❌ Comparar meses e enxergar a tendência real do seu negócio
- ❌ Perguntar "por que meu lucro caiu em março?" e receber uma análise real
- ❌ Receber alertas quando um indicador sair do limite saudável
- ❌ Exportar relatórios para mostrar pro contador ou sócio

---

### PROPOSTA DE VALOR (PRO)

## Com o Plano Pro, a Sofia vira sua CFO particular — por R$97/mês.

**O que você desbloqueia agora:**

📊 **DREs ilimitados** — carregue quantos meses quiser e veja a evolução completa

💬 **Chat Sofia sem limite** — pergunte qualquer coisa sobre suas finanças, sem restrição

📈 **Comparativo mensal automático** — a IA identifica variações e explica em português

🔔 **Alertas inteligentes** — quando sua margem cair abaixo do saudável, você sabe antes de sentir no caixa

📄 **Relatórios para exportar** — PDF pronto para reunião com contador, banco ou sócio

---

### ANCORAGEM DE PREÇO

> Um contador cobra **R$500 a R$2.000/mês** para fazer o que a Máxima Finance IA faz em segundos.
>
> Um analista financeiro? **R$5.000/mês no mínimo.**
>
> Você está tendo acesso a esse nível de análise por **R$97/mês** — menos do que uma janta de negócios.

---

### URGÊNCIA / OFERTA DE ATIVAÇÃO

**Oferta especial para novos usuários:**

Você acabou de criar sua conta. Nas próximas **24 horas**, o plano Pro está disponível por:

~~R$97/mês~~
# **R$77/mês** no primeiro mês

**Só para quem fizer o upgrade direto agora.**

---

### CTA PRINCIPAL

[BOTÃO VERDE GRANDE]

**→ Sim, quero o Pro por R$77 neste mês**
*Cancele quando quiser. Sem fidelidade.*

---

### LINK DE SAÍDA (abaixo do botão)

→ Não, prefiro continuar no plano gratuito por enquanto.

*(Texto pequeno, neutro — sem culpa, mas sem destaque)*

---

### PROVA SOCIAL RÁPIDA (3 depoimentos curtos)

> *"Em 15 minutos entendi por que minha empresa estava lucrando no papel e sem dinheiro no banco. Isso eu nunca consegui com o contador."*
> — **Marcos A., distribuidor de alimentos, SP**

> *"A Sofia me apontou que meu CMV estava 6% acima do ideal. Ajustei o preço de dois produtos e recuperei R$4.800 no mês seguinte."*
> — **Fernanda C., clínica estética, BH**

> *"Uso todo dia antes da reunião com meu sócio. Chegamos na reunião falando a mesma língua."*
> — **Ricardo T., indústria de embalagens, PR**

---

### GARANTIA (reforço)

**🛡️ 30 dias de garantia. Se não gostar, devolvemos 100%.**
Sem burocracia, sem pergunta, sem julgamento.

---

### CTA FINAL (repetição)

[BOTÃO VERDE]

**→ Ativar Pro agora por R$77 no primeiro mês**

---

## NOTAS DE IMPLEMENTAÇÃO (para dev)

- Esta página aparece na rota `/welcome-pro` após confirmação de cadastro
- Timer de 24h sincronizado com timestamp do cadastro (armazenado no Supabase)
- Botão principal → checkout Stripe (plano Pro com desconto de onboarding)
- Link de saída → `/dashboard` (sem desconto na próxima visita)
- A/B test sugerido: testar R$77 vs. "1º mês grátis, depois R$97"
