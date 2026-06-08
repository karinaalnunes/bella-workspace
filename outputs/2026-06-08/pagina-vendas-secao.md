# Página de Vendas — Seção: Landing Page de Trial / Diagnóstico Gratuito
*Noite 08/06/2026 — Bella*

---

## OBJETIVO DA SEÇÃO

Converter **tráfego frio** (Meta Ads, YouTube, orgânico) em **cadastros gratuitos**, mostrando valor imediato antes do pedido de cartão.
Público: empresário que nunca ouviu falar da Máxima e chegou por um anúncio ou vídeo.

---

## URL SUGERIDA

`maximafinance.com.br/diagnostico-gratuito`
ou
`maximafinance.com.br/gratis`

---

## ESTRUTURA DA LANDING PAGE DE TRIAL

---

### BLOCO 1 — HEADLINE PRINCIPAL

```
Descubra em 5 minutos
se sua empresa está
realmente lucrando.
```

**Subtítulo:**
```
Faça upload do seu DRE (ou cole os números)
e a IA da Máxima Finance entrega um
diagnóstico gratuito — em português, sem jargão.
```

**CTA primário:**
```
→ Fazer meu diagnóstico grátis
   (não precisa de cartão)
```

---

### BLOCO 2 — COMO FUNCIONA (3 PASSOS)

```
01  Você sobe o DRE
    PDF, Excel ou preenche um formulário simples.
    Leva menos de 2 minutos.

02  A IA analisa
    Sofia lê seus números, identifica os pontos
    críticos e monta o diagnóstico.

03  Você recebe o relatório
    Direto no app: o que está bom,
    o que precisa de atenção, o que é urgente.
```

**Visual sugerido:** 3 cards lado a lado com ícone + número + descrição breve.

---

### BLOCO 3 — O QUE VOCÊ RECEBE NO DIAGNÓSTICO GRÁTIS

```
✅  Análise da sua Margem Bruta
    (você está cobrindo os custos certos?)

✅  Diagnóstico de Despesas Fixas
    (qual % do faturamento vai para custos
    que você não controla?)

✅  Ponto de equilíbrio calculado
    (quanto precisa vender só para não perder?)

✅  Semáforo financeiro
    🟢 Saudável  🟡 Atenção  🔴 Crítico
    Para cada indicador do seu DRE.

✅  Conversa com Sofia
    3 perguntas liberadas para esclarecer
    qualquer dúvida sobre o resultado.
```

**Nota de rodapé do bloco:**
```
Diagnóstico gerado por IA treinada para PMEs brasileiras.
Dados protegidos por criptografia de ponta a ponta.
```

---

### BLOCO 4 — PROVA RÁPIDA (MICROTESTEMUNHO)

```
"Sempre achei que minha empresa tava bem.
O diagnóstico gratuito mostrou que minha
margem real era 4% — não os 18% que eu acreditava.
Agora, sei exatamente onde estou perdendo."

— Rodrigo S., distribuidora, São Paulo
   (usuário do plano Pro)
```

---

### BLOCO 5 — FORMULÁRIO DE CADASTRO

**Campos mínimos (atrito baixo):**
- Nome
- E-mail corporativo
- WhatsApp (opcional — para receber o relatório por lá também)
- Segmento: Comércio / Serviços / Indústria / Outro

**Botão:**
```
→ Começar meu diagnóstico grátis agora
```

**Abaixo do botão:**
```
🔒 Seus dados não serão compartilhados.
   Sem spam. Cancele quando quiser.
```

---

### BLOCO 6 — MICRO-OBJEÇÕES (ABAIXO DO FORMULÁRIO)

```
"Preciso ter um contador?"
→ Não. A Máxima é feita para o empresário ler
  sem depender de ninguém.

"Meus dados estão seguros?"
→ Sim. Criptografia AES-256. Conformidade LGPD.
  Seus números nunca saem do seu painel.

"O diagnóstico grátis tem algum limite?"
→ Sim: 1 DRE mensal, 3 perguntas para Sofia
  e relatório de 5 indicadores. O plano Pro
  libera tudo sem limite.
```

---

### BLOCO 7 — COMPARATIVO TRIAL VS. PRO (tabela simples)

| Recurso | Grátis (Trial) | Pro — R$97/mês |
|---|---|---|
| Análise de DRE | 1 por mês | Ilimitado |
| Indicadores monitorados | 5 | Todos |
| Perguntas para Sofia | 3 | Ilimitado |
| Alertas automáticos | ✗ | ✅ |
| Histórico mensal | ✗ | 24 meses |
| Comparativo de períodos | ✗ | ✅ |
| Suporte | ✗ | E-mail + chat |

**CTA da tabela:**
```
→ Começar pelo diagnóstico grátis
   (faço upgrade quando quiser)
```

---

### BLOCO 8 — RODAPÉ DE CONFIANÇA

```
🏅 Desenvolvida no Brasil para PMEs brasileiras
🔒 LGPD Compliant
📊 Baseada no padrão DRE Gerencial (CVM + CFC)
🤖 Powered by Claude AI (Anthropic)
```

---

## TOKENS PARA DESENVOLVIMENTO

```tsx
// Rota
export const TRIAL_LANDING_ROUTE = '/diagnostico-gratuito'

// Formulário de cadastro — Supabase
await supabase.from('trial_signups').insert({
  name: formData.name,
  email: formData.email,
  whatsapp: formData.whatsapp || null,
  segment: formData.segment,           // 'commerce' | 'services' | 'industry' | 'other'
  source: utm_source,                  // tracking de origem do anúncio
  utm_campaign: utm_campaign,
  created_at: new Date().toISOString()
})

// E-mail de boas-vindas do trial — Resend
await resend.emails.send({
  from: 'sofia@maximafinance.com.br',
  to: formData.email,
  subject: 'Seu diagnóstico gratuito está pronto — acesse agora',
  react: TrialWelcomeEmail({ name: formData.name })
})

// Evento de conversão — Meta Ads Pixel
fbq('track', 'Lead', {
  content_name: 'trial_signup',
  content_category: formData.segment,
  value: 0,
  currency: 'BRL'
})

// Componentes sugeridos
<TrialLandingHero />
<HowItWorks steps={3} />
<DiagnosticIncludes items={5} />
<MicroTestimonial />
<TrialSignupForm />
<MicroObjections />
<TrialVsProTable />
<TrustFooter />
```

---

## VARIANTE A/B SUGERIDA

**Versão A (atual):** "Diagnóstico gratuito" — foco em resultado e aprendizado.
**Versão B:** "Teste 7 dias grátis" — foco em experimentar o produto completo com trial.

Testar qual converte mais para qualificação de leads (B pode trazer leads menos comprometidos).

---

## MÉTRICAS PARA ACOMPANHAR

| Métrica | Meta |
|---|---|
| CTR anúncio → landing page | > 3% |
| Conversão landing → cadastro | > 25% |
| Cadastro → upload DRE (ativação) | > 40% |
| Ativação → conversão Pro (30d) | > 15% |

---

*Bella — Turno da noite 08/06/2026*
