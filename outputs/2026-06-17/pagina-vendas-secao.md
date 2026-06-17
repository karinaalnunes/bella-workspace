# Seção — Pop-up de Urgência: Virada de Semestre
*Produzido por Bella — Turno da Noite — 17/06/2026*

---

## CONTEXTO DE USO

**Onde aparece:** pop-up de saída (exit-intent) e banner fixo no topo da landing page  
**Janela de ativação:** 17 a 30 de junho de 2026  
**Gatilho principal:** virada de semestre (julho começa em 14 dias) + coupon real expirando em 30/jun  
**Evento competitivo:** Omie captou R$ 885M — urgência de lançamento Máxima Finance é máxima  

---

## VERSÃO 1 — POP-UP DE SAÍDA (EXIT-INTENT)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   Espera — antes de fechar.                                 │
│                                                             │
│   Você está a 14 dias da virada de semestre.                │
│                                                             │
│   A maioria dos empresários vai entrar em julho             │
│   sem saber se o 1º semestre deu lucro de verdade           │
│   — ou só faturou.                                          │
│                                                             │
│   Com a Máxima Finance IA, você sabe em minutos.            │
│                                                             │
│   🔓 REVISÃO_SEMESTRAL_JUNHO                                │
│   40% OFF no Plano Pro — só até 30/jun                      │
│                                                             │
│   [QUERO ENTENDER MEU SEMESTRE →]                           │
│                                                             │
│   ✗ Não, prefiro continuar sem saber os números             │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**Token dev:** `<ExitIntentModal triggerOn="exitIntent" coupon="REVISAO_SEMESTRAL_JUNHO" discount="40" expiryDate="2026-06-30" />`

---

## VERSÃO 2 — BANNER FIXO NO TOPO (STICKY TOP BAR)

```
🔔  Semestre está fechando. Você sabe se lucrou de verdade?
→ 40% OFF no Plano Pro — código REVISAO_SEMESTRAL_JUNHO — expira 30/jun   [ATIVAR AGORA]
```

**Token dev:** `<StickyBanner startDate="2026-06-17" expiryDate="2026-06-30" coupon="REVISAO_SEMESTRAL_JUNHO" discount="40" ctaText="ATIVAR AGORA" ctaUrl="/planos" />`

---

## VERSÃO 3 — POP-UP TEMPORIZADOR (COUNTDOWN)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ⏱️  Esta oferta expira em:                                │
│                                                             │
│       [DD]   [HH]   [MM]   [SS]                            │
│       dias  horas  minutos segundos                         │
│                                                             │
│   40% OFF — Plano Pro  R$ 97 → R$ 58,20/mês               │
│   Código: REVISAO_SEMESTRAL_JUNHO                           │
│                                                             │
│   O que você recebe:                                        │
│   ✅ Análise de DRE com IA em português simples             │
│   ✅ Chat Sofia — tire dúvidas financeiras 24h              │
│   ✅ Dashboard com seus indicadores em tempo real           │
│   ✅ Relatório mensal automático                            │
│                                                             │
│   [GARANTIR MEU DESCONTO AGORA →]                           │
│                                                             │
│   🔒 Cancele quando quiser. Sem multa.                      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**Token dev:** `<CountdownModal expiryDate="2026-06-30T23:59:00-03:00" coupon="REVISAO_SEMESTRAL_JUNHO" originalPrice={97} discountPct={40} features={["Análise de DRE com IA em português simples","Chat Sofia — tire dúvidas financeiras 24h","Dashboard com indicadores em tempo real","Relatório mensal automático"]} />`

---

## VERSÃO 4 — POP-UP MOBILE (TOAST / BOTTOM SHEET)

```
┌───────────────────────────────────────┐
│  📊 Virada de semestre chegando       │
│                                       │
│  40% OFF só até 30/jun                │
│  Código: REVISAO_SEMESTRAL_JUNHO      │
│                                       │
│  [QUERO O DESCONTO]   [Agora não]     │
└───────────────────────────────────────┘
```

**Token dev:** `<MobileToast device="mobile" position="bottom" coupon="REVISAO_SEMESTRAL_JUNHO" discount="40" expiryDate="2026-06-30" />`

---

## SEGMENTAÇÃO SUGERIDA

| Segmento | Versão | Trigger |
|---|---|---|
| Visitante novo (1ª visita) | Versão 1 (exit-intent) | Movimento de saída |
| Visitante recorrente (2ª+ visita) | Versão 3 (countdown) | Após 30s na página |
| Usuário gratuito logado | Versão 2 (sticky bar) | Sempre visível 17–30/jun |
| Mobile (qualquer) | Versão 4 (toast) | Após scroll 60% da página |

---

## COPY ALTERNATIVA — E-MAIL DE REATIVAÇÃO (para base gratuita)

**Assunto:** O semestre está quase acabando — você sabe o resultado?

---

[NOME],

Faltam 13 dias para fechar o primeiro semestre.

A maioria dos empresários vai entrar em julho sem saber se cresceu de verdade ou só correu no lugar.

O DRE responde isso em uma análise — mas a maioria nunca olhou.

A Máxima Finance analisa o DRE da sua empresa e entrega o diagnóstico em português simples, sem precisar de contador.

Hoje, com o código **REVISAO_SEMESTRAL_JUNHO**, você garante o Plano Pro com **40% de desconto** — válido só até 30 de junho.

[→ ANALISAR MEU SEMESTRE COM IA]

Até amanhã,  
Sofia — Máxima Finance IA

---

P.S. O desconto expira às 23h59 de 30/jun. Depois disso, volta para R$ 97.

---

**Token dev (automação):** `<ReactivationEmail segment="freeUsers" subject="O semestre está quase acabando — você sabe o resultado?" coupon="REVISAO_SEMESTRAL_JUNHO" sendDate="2026-06-23" />`

---

## NOTAS DE IMPLEMENTAÇÃO

- Coupon `REVISAO_SEMESTRAL_JUNHO` deve estar criado no Stripe com 40% off, tipo `percent_off`, expiry `2026-06-30T23:59:00-03:00`
- O sticky bar deve sumir automaticamente em 1º/julho (usar `expiryDate` no componente)
- A/B teste recomendado: testar Versão 1 (dor/semestre) vs Versão 3 (countdown) para medir conversão
- Prioridade máxima de implementação: coupon no Stripe leva 15 minutos e pode estar rodando hoje

---

*Bella — Turno da Noite — 17/06/2026*
