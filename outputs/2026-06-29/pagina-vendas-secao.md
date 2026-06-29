# Seção Página de Vendas — Upsell / Upgrade In-App (Plano Pro → Business)
*Turno da noite — 29/06/2026 | Bella*

---

## CONTEXTO

Seção e copy completa para converter usuários do plano Pro (R$97) para o Business (R$297) dentro do próprio app.
Inclui: banner in-app, modal de upgrade, página de upgrade, e-mail de upgrade e tokens de desenvolvimento.

---

## SEÇÃO 1 — Banner In-App (sempre visível no Pro)

**Localização:** topo do Dashboard e da AnalisePage (faixa laranja discreta)

```
Você está no plano Pro.
Quer comparar sua margem com empresas do mesmo setor?
→ [Fazer upgrade para Business] — R$297/mês
```

**Variante B (mais assertiva):**
```
Sua margem bruta está em [X]%.
Sabe se isso é bom ou ruim para o seu setor?
O Business responde isso automaticamente.
→ [Ver plano Business]
```

---

## SEÇÃO 2 — Modal de Upgrade (gatilho: usuário tenta acessar recurso Business)

**Título:**
> Esse recurso é exclusivo do plano Business

**Subtítulo:**
> Você chegou até aqui porque está levando a gestão a sério.
> No Business, a Sofia vai além: ela compara seus números com benchmarks do setor e aponta exatamente onde você pode melhorar.

**Lista de benefícios do Business (vs Pro):**

| Pro (você tem) | Business (você ganha) |
|---|---|
| Análise de 1 DRE por vez | Histórico de até 24 meses de DRE |
| Chat Sofia para dúvidas | Sofia com benchmarks do setor |
| Relatório padrão | Relatório executivo com gráficos e PDF |
| — | Alerta automático de desvio de margem |
| — | Suporte prioritário (WhatsApp) |
| — | Multi-CNPJ (até 3 empresas) |

**CTA principal:**
> [Fazer upgrade agora — R$297/mês]

**Linha de suporte:**
> Sem contrato. Cancele quando quiser.

---

## SEÇÃO 3 — Página Dedicada de Upgrade `/upgrade`

### Headline:
**Você já sabe o que o DRE diz sobre sua empresa.**
**Agora descubra o que ele diz sobre você no mercado.**

### Subheadline:
O plano Business coloca seus números lado a lado com empresas do mesmo segmento. A Sofia entrega um diagnóstico completo — não só o que está acontecendo, mas por quê está acontecendo e o que você pode fazer.

---

### Bloco "O que muda de verdade":

**Sem Business:**
> "Sua margem bruta caiu de 38% para 31% em março."

**Com Business:**
> "Sua margem bruta caiu de 38% para 31% em março. Empresas do varejo com faturamento entre R$200k–R$500k/mês têm margem média de 35%. A Sofia identificou que seu CMV subiu 9% — possível aumento de fornecedor não repassado ao preço. Recomendação: reajuste de preço de 4–6% nos produtos de maior giro."

*A diferença entre um dado e uma decisão.*

---

### Depoimento âncora:

> *"No Pro eu sabia que tinha problema. No Business eu soube exatamente o que era e o que fazer."*
>
> — Marcos R., dono de distribuidora, Campinas

---

### Bloco de preço:

**Plano Business**
**R$ 297/mês**
ou R$ 2.970/ano (economize 2 meses)

✅ Tudo do Pro
✅ Histórico de DRE (24 meses)
✅ Benchmarks por segmento
✅ Relatório executivo em PDF
✅ Alertas automáticos de margem
✅ Multi-CNPJ (até 3 empresas)
✅ Suporte prioritário WhatsApp

> [Fazer upgrade agora]

Cartão de crédito. Sem contrato. Cancele quando quiser.

---

### Garantia:
> 30 dias de garantia. Se o Business não entregar mais clareza do que o Pro, devolvemos a diferença. Sem perguntas.

---

## SEÇÃO 4 — E-mail de Upgrade (enviado D+14 após cadastro no Pro)

**Assunto:** Karina, seu DRE revela mais do que você está vendo

**Pré-header:** A Sofia do plano Business enxerga o que o Pro não mostra.

---

Olá, [NOME],

Você está usando o Máxima Finance há [X] dias e já subiu de nível: você olha para o DRE, entende o que está acontecendo e toma decisões com dados.

Mas tem uma pergunta que o plano Pro não consegue responder:

**Sua margem é boa *para o seu setor*?**

Um faturamento de R$200k/mês com margem líquida de 6% pode ser excelente para varejo e péssimo para serviços.

No plano Business, a Sofia responde essa pergunta automaticamente — toda vez que você subir um DRE.

Ela cruza seus números com benchmarks do segmento, identifica desvios, aponta causas e sugere ações específicas para o seu negócio.

**O upgrade custa R$200/mês a mais.**
Se você tomar uma decisão melhor de precificação, contratação ou corte de custo baseada no que a Sofia encontrar — esse valor paga sozinho em dias.

→ [Ver o que muda no Business]

Sem pressa. Mas quanto antes você souber onde está em relação ao mercado, mais rápido você ajusta o rumo.

Sofia e eu estamos aqui.

*Karina Nunes*
Fundadora, Máxima Finance IA

---

## TOKENS DE DESENVOLVIMENTO

```tsx
// Banner in-app (componente)
// Arquivo: src/components/UpgradeBanner.tsx

interface UpgradeBannerProps {
  currentPlan: 'free' | 'pro'
  metricValue?: string // ex: "31%"
  metricLabel?: string // ex: "margem bruta"
}

// Modal de upgrade
// Arquivo: src/components/UpgradeModal.tsx
// Trigger: onClick em qualquer feature com flag requiresPlan: 'business'
// Props: featureName, featureDescription, onClose, onUpgrade

// Página /upgrade
// Arquivo: src/pages/UpgradePage.tsx
// Rota: /upgrade?from=[dashboard|analise|modal]
// Rastrear UTM para entender de onde vêm os upgrades

// Feature flag helper
// src/utils/planAccess.ts
export const requiresBusiness = (feature: BusinessFeature): boolean => {
  return userPlan !== 'business'
}
type BusinessFeature = 'benchmarks' | 'history_24m' | 'pdf_report' | 'alerts' | 'multi_cnpj'
```

---

## ORDEM DE IMPLEMENTAÇÃO SUGERIDA

1. Feature flags nas rotas Business (1h)
2. Banner in-app no Dashboard (30min)
3. Modal de upgrade ao tocar em feature bloqueada (1h)
4. Página `/upgrade` com preço e CTA (2h)
5. Webhook Stripe → atualizar `plan` no Supabase (1h)
6. E-mail automático D+14 via Resend/Brevo (30min)

**Total estimado: ~6h de dev**
