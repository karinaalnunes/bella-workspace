# Página de Vendas — Seção: "Tour pelo App em 60 Segundos"
*Turno da Noite — 20/06/2026 | Bella*

---

## SEÇÃO: DEMONSTRAÇÃO NARRATIVA — "O QUE ACONTECE EM 3 MINUTOS"

> **Objetivo:** Mostrar ao empresário como o produto funciona na prática, sem jargão técnico. Seção de demonstração narrativa (storytelling de uso) para reduzir a barreira de experimentação e transformar curiosidade em cadastro.

---

### COMPONENTE 1 — LEAD-IN DA SEÇÃO

**Headline:**
# Veja o que acontece quando você faz o upload do DRE

**Subheadline:**
Sem planilha. Sem contador. Sem sigla que ninguém entende.
Em 3 minutos, você sabe exatamente onde está o dinheiro — e por que ele some.

---

### COMPONENTE 2 — JORNADA NARRATIVA (3 PASSOS COM MICROCOPY)

```
╔═══════════════════════════════════════════════════════════╗
║  PASSO 1 DE 3                                             ║
║  ─────────────────────────────────────────────────────    ║
║  📄  Você envia o DRE do mês                              ║
║                                                           ║
║  PDF, Excel ou foto. A Sofia lê qualquer formato.         ║
║  Sem retrabalho, sem formatação especial.                 ║
║                                                           ║
║  ⏱ Tempo: 30 segundos                                     ║
╚═══════════════════════════════════════════════════════════╝

╔═══════════════════════════════════════════════════════════╗
║  PASSO 2 DE 3                                             ║
║  ─────────────────────────────────────────────────────    ║
║  🤖  A Sofia analisa e traduz                             ║
║                                                           ║
║  Em vez de números, você recebe frases:                   ║
║                                                           ║
║  ✦ "Sua margem bruta caiu 4% em relação ao mês           ║
║     passado. O CMV aumentou R$12.400 — provavelmente      ║
║     insumos. Vale revisar o fornecedor X."                ║
║                                                           ║
║  ✦ "Despesas fixas consumiram 38% da receita —            ║
║     acima do ideal para o seu segmento (25–30%)."         ║
║                                                           ║
║  ✦ "Lucro líquido: R$8.200. Representa 8,2% do           ║
║     faturamento. Meta sugerida para próximo mês:          ║
║     R$12.000 (10% de margem líquida)."                    ║
║                                                           ║
║  ⏱ Tempo: 90 segundos                                     ║
╚═══════════════════════════════════════════════════════════╝

╔═══════════════════════════════════════════════════════════╗
║  PASSO 3 DE 3                                             ║
║  ─────────────────────────────────────────────────────    ║
║  💬  Você pergunta — a Sofia responde                     ║
║                                                           ║
║  "Se eu contratar mais um funcionário,                    ║
║   o que acontece com minha margem?"                       ║
║                                                           ║
║  Sofia: "Com base no seu DRE de junho, contratar          ║
║  com salário de R$2.500 + encargos (R$3.750 custo         ║
║  real) reduziria sua margem líquida de 8,2% para          ║
║  5,1%. Você precisaria gerar R$37.500 extras/mês          ║
║  para manter a margem atual."                             ║
║                                                           ║
║  ⏱ Tempo: 60 segundos                                     ║
╚═══════════════════════════════════════════════════════════╝
```

---

### COMPONENTE 3 — RESULTADO FINAL COM CHAMADA À AÇÃO

**Texto abaixo dos passos:**

Em 3 minutos você sai do "acho que tô bem" para o "sei exatamente onde estou".

E a Sofia fica disponível 24 horas — para quando bater aquela dúvida às 23h antes de uma reunião importante.

**CTA primário:**
> **[Testar grátis por 14 dias →]**
> Sem cartão de crédito. Cancela quando quiser.

**Microcopy de segurança:**
> Mais de 1.200 empresários já fizeram o upload do primeiro DRE.
> 94% disseram que entenderam seus números pela primeira vez.

---

### COMPONENTE 4 — PROVA REAL (MICROTESTEMUNHO INTEGRADO)

> *"Sempre soube que o DRE era importante. Só não sabia o que fazer com os números. Na primeira vez que usei a Sofia, em 4 minutos eu entendi por que fevereiro foi ruim — e o que mudar em março."*
>
> — **Rodrigo M.**, dono de distribuidora, SP
> Plano Pro há 5 meses

---

### COMPONENTE 5 — OBJEÇÃO INTEGRADA

**Bloco:** "E se meu DRE for muito simples / muito complexo?"

> A Sofia funciona para DREs de 1 página ou de 40 páginas.
> Para empresas com faturamento de R$30k a R$3M por mês.
> Para comércio, serviços, indústria e prestadores.
> Se tiver receita, custo e despesa — a Sofia analisa.

---

## ESPECIFICAÇÕES TÉCNICAS (PARA DEV)

```jsx
// Componente: <ProductTour />
// Local sugerido: entre seção "Como funciona" e "Planos"
// Animação: scroll-trigger com fade-in sequencial (CSS ou Framer Motion)

// Props:
// steps: Array<{ number, title, body, time }>
// testimonial: { text, author, role, plan, time }
// cta: { label, href, subtext }
// trust_badge: string

// Design tokens:
// bg: #0F0F1A (dark navy)
// card_bg: #1A1A2E
// accent: #7C3AED (roxo Máxima)
// step_connector: dashed line com animação de progressão
// time_badge: pill verde-escuro (#14532D / #22C55E)
```

---

## MÉTRICAS DE SUCESSO DESTA SEÇÃO

| KPI | Meta |
|-----|------|
| Scroll depth até o CTA | > 65% dos visitantes |
| CTR CTA "Testar grátis" dentro da seção | > 8% |
| Redução de bounce pós-seção | > 15% vs. controle sem seção |

---

## VARIANTE A/B

**Variante A (atual acima):** Tour em 3 passos com microcopy detalhado

**Variante B — Vídeo-first:**
> Substituir passos por thumbnail clicável do Welcome Video (roteiro em `outputs/2026-06-18/pagina-vendas-secao.md`)
> Headline: *"2 minutos. É o tempo que a Sofia precisa para te dizer onde está o dinheiro."*

---

*Próximo passo para o dev: implementar `<ProductTour />` após a seção "Como funciona" — complementa sem repetir.*
