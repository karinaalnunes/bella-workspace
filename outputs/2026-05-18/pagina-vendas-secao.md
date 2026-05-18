# Máxima Finance IA — Copy para Upsell in-App / Modal de Upgrade
## Seção: Upgrade Gratuito → Pro (Modais + Banners in-app)
*Turno da noite — 18/05/2026 | Bella*

---

## CONTEXTO DE USO

Acionado quando o usuário do plano Gratuito:
- Tenta fazer upload do 2º DRE (limite do Free)
- Tenta acessar o Chat Sofia
- Fica 30 segundos na AnalisePage sem converter
- Tenta exportar o relatório em PDF

**Objetivo:** converter Free → Pro (R$97/mês) no momento de maior intenção.

---

## MODAL 1 — Limite de DRE atingido (trigger: 2º upload)

### Headline
**Você está crescendo — o plano Gratuito não acompanha.**

### Subheadline
Você já analisou seu primeiro DRE. Agora é hora de acompanhar a evolução mês a mês.

### Corpo
Com o **Máxima Pro** você:
- ✅ Faz upload ilimitado de DREs
- ✅ Compara mês a mês e vê tendências em segundos
- ✅ Conversa com a Sofia sobre qualquer número
- ✅ Exporta diagnóstico completo em PDF para banco ou sócios

> *"O primeiro DRE te mostrou onde você estava. O segundo vai mostrar se você melhorou."*

### CTA Principal
**Quero o Pro — R$97/mês**
`→ ir para checkout`

### CTA Secundário
Continuar no Gratuito por enquanto
`→ fechar modal`

### Microcopy abaixo do CTA
Cancela quando quiser. Sem multa. Sem burocracia.

---

## MODAL 2 — Chat Sofia bloqueado (trigger: clique no chat)

### Headline
**A Sofia sabe a resposta. Mas ela só conversa com assinantes Pro.**

### Subheadline
Desbloqueie o chat financeiro da IA e tire dúvidas em linguagem simples — sem precisar de contador.

### Corpo
Pergunte à Sofia:
- *"Minha margem bruta está boa para o meu setor?"*
- *"Onde estou perdendo margem comparado ao mês passado?"*
- *"O que preciso cortar para chegar em 15% de lucro líquido?"*

Ela responde em português, com os **números do seu DRE** — não com teoria.

### CTA Principal
**Desbloquear Sofia — R$97/mês**
`→ ir para checkout`

### CTA Secundário
Ver o que consigo no Gratuito
`→ fechar modal`

### Microcopy
Teste 7 dias grátis. Sem cobrança agora.

---

## MODAL 3 — Export PDF bloqueado (trigger: clique em "Exportar Relatório")

### Headline
**Seu diagnóstico está pronto. Falta só 1 passo para baixar.**

### Subheadline
O relatório em PDF é exclusivo do Pro — pronto para apresentar ao banco, ao contador ou ao seu sócio.

### Corpo
**O que está no PDF:**
- Resumo executivo do DRE (linguagem simples)
- Semáforo de saúde financeira (verde / amarelo / vermelho)
- 3 alertas prioritários com recomendação de ação
- Evolução mensal (quando tiver 2+ meses)
- Assinatura digital da Máxima Finance IA

**Por que isso importa:**
Bancos aprovam crédito com mais facilidade para empresas que apresentam diagnóstico financeiro organizado. Seu contador vai agradecer.

### CTA Principal
**Gerar PDF agora — R$97/mês**
`→ ir para checkout`

### CTA Secundário
Agora não
`→ fechar modal`

### Microcopy
Teste 7 dias grátis. Cancela com 1 clique.

---

## BANNER PERSISTENTE — Topo do Dashboard (plano Gratuito)

```
[📊 Você está no plano Gratuito]  Upgrade para Pro — desbloqueie Sofia, PDF e DREs ilimitados.  [→ Assinar por R$97/mês]
```

*Aparece sempre. Some quando assinar.*

---

## BANNER IN-FEED — AnalisePage (após ver diagnóstico do 1º DRE)

### Headline
**Agora que você sabe onde está — descubra para onde ir.**

### Corpo
O diagnóstico mostrou os problemas. O **Máxima Pro** te ajuda a resolvê-los, mês a mês, com acompanhamento da Sofia.

**→ Assinar Pro por R$97/mês** | Cancela quando quiser

---

## MODAL DE SAÍDA — Usuário inativo por 7+ dias (email/push)

### Assunto do e-mail
*Seu DRE ainda está esperando por você*

### Pré-header
Uma análise feita. Quanto mudou desde então?

### Corpo
Oi [Nome],

Faz [X dias] que você analisou seu DRE no Máxima Finance.

Enquanto isso, sua empresa gerou receita, pagou contas, contratou ou perdeu clientes.

**O DRE desse período conta uma história. Você ainda não leu.**

Com o Máxima Pro você faz upload do novo mês em 2 minutos e a Sofia te mostra o que mudou — e o que precisa de atenção agora.

**[→ Voltar e atualizar meu DRE]**

Com o plano Gratuito, seu 1º DRE já está aqui esperando.
Com o Pro, você tem o histórico completo — e o diagnóstico evolui junto com você.

*Bella — Máxima Finance IA*

---

## TOKENS PARA DEV (React + Supabase)

```typescript
// Trigger de upsell
type UpsellTrigger =
  | 'second_dre_upload'   // 2º upload → Modal 1
  | 'sofia_click'          // click chat → Modal 2
  | 'pdf_export_click'     // click export → Modal 3
  | 'dashboard_idle_30s'   // idle 30s na análise → Modal 3 leve
  | 'inactive_7d'          // e-mail re-engajamento

// Supabase: verificar plano
const { data: { subscription } } = await supabase
  .from('subscriptions')
  .select('plan, status')
  .eq('user_id', user.id)
  .single()

const isPro = subscription?.plan === 'pro' && subscription?.status === 'active'

// Condicional no componente
if (!isPro && trigger === 'second_dre_upload') {
  setUpsellModal('dre_limit') // abre Modal 1
}
```

---

## MÉTRICAS DE SUCESSO

| Métrica | Meta |
|---|---|
| Taxa de abertura do modal | > 70% |
| CTR modal → checkout | > 15% |
| Conversão checkout → assinatura | > 25% |
| Cancelamento 7 dias (churn trial) | < 20% |

---

*Próximo passo dev: implementar `<UpsellModal>` com os 3 variantes + banner persistente no `<DashboardLayout>` quando `plan === 'free'`.*
