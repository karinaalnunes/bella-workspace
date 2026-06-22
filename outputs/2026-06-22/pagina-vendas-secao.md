# Página de Vendas — Seção: Pop-up de Reativação do 2º Semestre
*Produzido por Bella — Turno da noite — 22/06/2026*

---

## CONTEXTO DE USO

Esta seção é um **pop-up de saída (exit intent) + banner sticky** ativado especificamente na virada de semestre (22/jun–30/jun). Ativado para:
- Visitantes que chegaram mas não converteram
- Leads na lista que ainda não assinaram
- Anúncios de remarketing no Meta Ads

Coupon ativo: `REVISAO_SEMESTRAL_JUNHO` — expira 30/jun.

---

## POP-UP DE SAÍDA — VERSÃO PRINCIPAL

---

**[Gatilho: mouse move para fechar aba / 45s de inatividade]**

```
┌──────────────────────────────────────────────────────────────────┐
│                                                                    │
│   ⚡ Espera — o 2º semestre começa hoje.                          │
│                                                                    │
│   A maioria dos empresários vai entrar em julho                   │
│   igual ao ano passado: sem saber o que aconteceu                │
│   nos últimos 6 meses.                                            │
│                                                                    │
│   Você quer ser diferente?                                        │
│                                                                    │
│   Use o DRE de junho como ponto de partida —                     │
│   e deixa a IA da Sofia interpretar pra você.                    │
│                                                                    │
│   ┌─────────────────────────────────────────────┐                │
│   │   30% OFF nos próximos 8 dias               │                │
│   │   Cupom: REVISAO_SEMESTRAL_JUNHO            │                │
│   │   Válido até 30/jun — não prorroga          │                │
│   └─────────────────────────────────────────────┘                │
│                                                                    │
│   [QUERO COMEÇAR O 2º SEMESTRE CERTO →]                          │
│                                                                    │
│   Não, prefiro continuar no escuro.                               │
│                                                                    │
└──────────────────────────────────────────────────────────────────┘
```

---

## BANNER STICKY (TOPO DA PÁGINA)

**[Exibir de 22/jun a 30/jun — fixo no topo em todas as páginas]**

```
🗓️ Revisão Semestral — 8 dias para fechar o DRE de junho com desconto.
Cupom REVISAO_SEMESTRAL_JUNHO — 30% OFF · [ATIVAR DESCONTO →]
```

---

## VERSÃO MOBILE (POP-UP SIMPLIFICADO)

```
⚡ Só até 30/jun

Análise do DRE de junho com 30% OFF.
A Sofia interpreta seus números em minutos.

Cupom: REVISAO_SEMESTRAL_JUNHO

[APLICAR DESCONTO →]
```

---

## E-MAIL DE REATIVAÇÃO (1 disparo — enviar 22/jun)

**Assunto:** O 2º semestre começou. Seu DRE de junho está pronto?

**Pré-header:** 8 dias para fechar com desconto.

---

Oi, [NOME].

Hoje é o primeiro dia do segundo semestre.

E a maioria dos donos de empresa vai entrar em julho sem ter entendido o que aconteceu nos últimos 6 meses. Sem saber se a margem cresceu ou encolheu. Sem saber quais produtos estão drenando caixa.

Não precisa ser assim.

O DRE de junho é o mapa do seu 2º semestre. E a Sofia — a IA da Máxima Finance — lê esse mapa pra você em minutos, em português, sem planilha e sem contador.

**Para celebrar a virada de semestre, criamos o cupom:**

`REVISAO_SEMESTRAL_JUNHO`
**30% de desconto** no plano Pro ou Business.
**Válido até 30 de junho — não prorroga.**

[→ COMEÇAR AGORA COM DESCONTO]

Você vai entrar em julho com clareza ou com chute?

Bella
Assistente da Máxima Finance IA

---

**P.S.:** A Conta Azul está em produção com IA. O Omie declarou agente generativo no roadmap. A janela para sair na frente é agora — não em agosto.

---

## COPY PARA REMARKETING META ADS (3 variações)

### Ad 1 — Urgência Semestral

**Headline:** O 2º semestre começou hoje.
**Texto:** Você sabe o que aconteceu com a margem da sua empresa nos últimos 6 meses? A Sofia lê seu DRE de junho e te explica em minutos. 30% OFF até 30/jun.
**CTA:** Ver meu diagnóstico →

---

### Ad 2 — Dor da Incerteza

**Headline:** Entrar em julho no escuro é escolha.
**Texto:** Faturou, pagou contas, sobrou pouco — mas por quê? Sem ler o DRE de junho, você vai repetir o erro no 2º semestre. A Máxima Finance explica seus números em português simples.
**CTA:** Usar cupom REVISAO_SEMESTRAL_JUNHO →

---

### Ad 3 — Prova Social

**Headline:** "Finalmente entendi meu DRE."
**Texto:** Empresários de todo o Brasil estão usando a IA da Máxima Finance para interpretar o DRE sem precisar de contador. Você ainda vai entrar no 2º semestre na base do chute?
**CTA:** Testar 30% mais barato →

---

## NOTAS DE IMPLEMENTAÇÃO

- **Ativar pop-up:** 22/jun (hoje) — desativar automaticamente 30/jun 23:59
- **Criar coupon no Stripe:** `REVISAO_SEMESTRAL_JUNHO` — 30% off, validade 30/jun, limite de usos: sem limite
- **Segmento de e-mail:** leads que visitaram a landing page mas não converteram (últimos 30 dias)
- **Pixel Meta Ads:** criar audiência customizada de visitantes últimos 14 dias para remarketing
- **Banner sticky:** css `position: fixed; top: 0;` — incluir countdown até 30/jun

---

*Próximo passo: criar o coupon no Stripe (15 min) — prioridade máxima esta semana*
