# Copy para Checkout / Tela de Pagamento — Máxima Finance IA
*Turno da noite — 13/05/2026*

---

## CONTEXTO DE USO

Este arquivo entrega toda a microcopy da tela de pagamento (Stripe Checkout + página de planos interativa).  
Dev pode usar diretamente no componente de planos e no redirect pós-Stripe.

---

## HEADLINE DA TELA DE PLANOS

> **Escolha seu plano e comece a entender seus números hoje**
> Sem fidelidade. Cancele quando quiser. Garantia de 7 dias.

*Subtítulo (opcional, menor):*
> Mais de 1.200 empresários brasileiros já usam a Máxima Finance IA para tomar decisões com segurança.

---

## CARDS DOS PLANOS

### PLANO GRATUITO
**Nome no card:** `Explorar`
**Preço:** R$ 0 / sempre gratuito

**Tagline:** *"Para conhecer antes de decidir"*

**O que inclui:**
- ✅ 1 análise de DRE por mês
- ✅ Diagnóstico básico (receita, despesa, resultado)
- ✅ Chat Sofia — 10 perguntas/mês
- ✅ Relatório em PDF (1 página)
- ❌ Comparativo histórico
- ❌ Alertas automáticos
- ❌ Exportação completa
- ❌ Suporte prioritário

**CTA do card:** `Começar grátis →`
**Microcopy abaixo do CTA:** *Sem cartão de crédito*

---

### PLANO PRO ⭐ MAIS POPULAR
**Nome no card:** `Pro`
**Preço:** ~~R$ 127~~ **R$ 97/mês**
**Ênfase visual:** Badge "Mais popular" + borda destacada

**Tagline:** *"Para o empresário que quer decidir com números, não com achismo"*

**O que inclui:**
- ✅ DREs ilimitados por mês
- ✅ Diagnóstico completo com IA (receita, margem, custos, tendências)
- ✅ Chat Sofia ilimitado — perguntas em linguagem natural
- ✅ Comparativo mês a mês (últimos 12 meses)
- ✅ Alertas automáticos de margem e caixa
- ✅ Relatório executivo em PDF (completo)
- ✅ Exportação para Excel/CSV
- ✅ Suporte por e-mail (resposta em 24h)
- ❌ Multi-CNPJ
- ❌ API de integração
- ❌ Gerente de conta dedicado

**CTA do card:** `Assinar Pro por R$ 97 →`
**Microcopy abaixo do CTA:** *7 dias de garantia. Cancele a qualquer momento.*

---

### PLANO BUSINESS
**Nome no card:** `Business`
**Preço:** **R$ 297/mês**

**Tagline:** *"Para empresas que gerenciam múltiplas unidades ou precisam de relatórios para sócios e bancos"*

**O que inclui:**
- ✅ Tudo do Pro
- ✅ Até 5 CNPJs na mesma conta
- ✅ Dashboard multi-empresa (visão consolidada)
- ✅ Relatório de EBITDA e valuation básico
- ✅ Exportação formatada para apresentação a banco/investidor
- ✅ API de integração (ERP/planilhas)
- ✅ Suporte prioritário por WhatsApp (resposta em 4h úteis)
- ✅ Onboarding guiado com especialista (1 sessão de 30 min)

**CTA do card:** `Assinar Business por R$ 297 →`
**Microcopy abaixo do CTA:** *7 dias de garantia. Cancele a qualquer momento.*

---

## FAIXA DE CONFIANÇA (abaixo dos cards)

```
🔒 Pagamento 100% seguro via Stripe
🔁 Cancele quando quiser, sem multa
📋 Nota fiscal emitida automaticamente
🇧🇷 Suporte em português
```

---

## FAQ RÁPIDO DA TELA DE CHECKOUT

**"Posso mudar de plano depois?"**
Sim. Upgrade ou downgrade a qualquer momento, com cobrança proporcional automática.

**"O que é a garantia de 7 dias?"**
Se não gostar por qualquer motivo nos primeiros 7 dias, devolvemos 100% do valor. Sem perguntas.

**"Preciso instalar alguma coisa?"**
Não. A Máxima Finance IA é 100% online. Funciona em qualquer navegador.

**"Meus dados financeiros estão seguros?"**
Sim. Todos os dados são criptografados e nunca compartilhados com terceiros. Seguimos a LGPD.

---

## MICROCOPY DO STRIPE CHECKOUT

### Título da sessão de pagamento:
> **Máxima Finance IA — Plano [nome do plano]**

### Descrição (aparece no resumo):
> Acesso completo à análise de DRE com inteligência artificial. Renovação mensal. Cancele quando quiser.

### Botão final de confirmação:
> `Confirmar assinatura — R$ [valor]/mês`

### Texto abaixo do botão:
> *Cobrado mensalmente. Você pode cancelar a qualquer momento no painel da sua conta. Ao confirmar, você concorda com os Termos de Uso e a Política de Privacidade.*

---

## PÁGINA DE UPGRADE (usuário Gratuito → Pro)

**Headline:**
> Você já viu o que a Máxima pode fazer. Agora imagine com os dados completos.

**Subheadline:**
> Seus 10 créditos do Chat Sofia acabaram. No plano Pro, as perguntas são ilimitadas — e os diagnósticos também.

**CTA principal:** `Fazer upgrade para Pro — R$ 97/mês →`
**CTA secundário (link):** *Talvez mais tarde*

**Microcopy de urgência (opcional, A/B):**
> ⚡ Empresários que analisam o DRE mensalmente reduzem custos em média 18% em 90 dias.

---

## TOKENS DE PERSONALIZAÇÃO PARA O DEV

| Token | Onde usar |
|---|---|
| `{{first_name}}` | Headline da tela de upgrade, e-mail de confirmação |
| `{{plan_name}}` | Título Stripe Checkout, e-mail de boas-vindas |
| `{{amount}}` | Botão de confirmação Stripe, nota fiscal |
| `{{trial_end_date}}` | E-mail de lembrete (D-2 da garantia) |
| `{{next_billing_date}}` | Painel do usuário, e-mail pré-cobrança |

---

*Próximo passo para o dev: implementar componente `<PlansGrid>` com estes cards e conectar ao Stripe Checkout via `stripe.redirectToCheckout()` com os price_ids de cada plano.*
