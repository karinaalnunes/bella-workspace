# Página de Vendas — Seção: Checkout / Página de Pagamento
*Máxima Finance IA | Noite 03/07/2026 — Bella*

---

## CONTEXTO DE USO

Esta seção contém a copy completa para a **página de checkout / pagamento**, que o usuário vê imediatamente antes de inserir o cartão. É a última barreira antes da conversão — cada palavra conta.

**Posição no funil:** Clique em "Assinar Agora" → Checkout → Confirmação (Thank You Page já pronta)

---

## ESTRUTURA DA PÁGINA DE CHECKOUT

### HEADER FIXO (sticky — visível durante o scroll)

```
✅  Máxima Finance IA — Análise de DRE com Inteligência Artificial
🔒  Pagamento 100% seguro  |  ✅  Cancele quando quiser  |  🛡️  7 dias de garantia
```

---

### COLUNA ESQUERDA — RESUMO DO PLANO ESCOLHIDO

#### Versão PRO (R$97/mês)

```
Você escolheu o Plano Pro

📊  Máxima Finance IA — Plano Pro
Análise ilimitada de DRE
Chat Sofia (IA) sem limites de perguntas
Diagnóstico automático com pontos de atenção
Dashboard com indicadores principais
Relatório PDF exportável
Suporte via e-mail prioritário

R$ 97,00 / mês
(equivale a R$ 3,23 por dia — menos que um café)

Cobrado mensalmente. Sem contrato. Cancele quando quiser.
```

---

#### Versão BUSINESS (R$297/mês)

```
Você escolheu o Plano Business

📊  Máxima Finance IA — Plano Business
Tudo do Pro, mais:
Múltiplos CNPJs (até 5)
Análise comparativa mês a mês
Alertas automáticos de desvio de margem
Integração com contador (exportação personalizada)
Acesso antecipado a novos recursos
Suporte via WhatsApp

R$ 297,00 / mês
(R$ 9,90 por dia — menos que perder uma venda por desconhecimento)

Cobrado mensalmente. Sem contrato. Cancele quando quiser.
```

---

### COLUNA DIREITA — FORMULÁRIO + REFORÇO DE CONFIANÇA

#### Título da coluna:
```
Complete seu cadastro e acesse agora
```

#### Subtítulo:
```
Seu DRE vai ser interpretado em menos de 2 minutos.
```

#### Campos do formulário (tokens para dev):
- `[CAMPO: Nome completo]`
- `[CAMPO: E-mail]`
- `[CAMPO: Dados do cartão — Stripe Elements]`

#### Botão CTA principal:
```
🔐  ATIVAR MINHA CONTA POR R$ [VALOR]/MÊS
```

*Nota dev: texto do botão deve refletir o plano selecionado dinamicamente.*

---

### MICRO-COPY ABAIXO DO BOTÃO

```
🔒  Pagamento processado com criptografia SSL
💳  Aceitamos todos os cartões de crédito e débito
📧  Você receberá a confirmação no e-mail em até 2 minutos
```

---

### BLOCO DE GARANTIA (abaixo do formulário)

```
🛡️  Garantia Incondicional de 7 Dias

Se em até 7 dias após a assinatura você não sentir que a Máxima Finance IA
está te ajudando a entender melhor as finanças do seu negócio,
basta enviar um e-mail e devolvemos 100% do valor.

Sem perguntas. Sem burocracia.
```

---

### PROVA SOCIAL COMPACTA (abaixo da garantia)

```
"Assinou e já na primeira semana entendeu onde estava perdendo margem."
— Empresária, setor de serviços, SP

"Primeiro DRE que eu realmente entendi sem precisar ligar pro contador."
— Dono de distribuidora, MG

"Valia mais do que o preço de um almoço de negócios."
— Empreendedora, varejo online, RJ
```

---

### SEÇÃO DE OBJEÇÕES FINAIS (antes do rodapé)

```
Ainda com dúvida? Isso é normal.

❓ "E se eu não gostar?"
→ 7 dias de garantia. Sem risco nenhum para você.

❓ "Preciso saber de finanças para usar?"
→ Não. A Sofia explica tudo em português simples.

❓ "Meu contador já faz isso."
→ A Máxima não substitui contador — te ajuda a entender o que ele produz.

❓ "Posso cancelar a qualquer momento?"
→ Sim. Um clique, sem fidelidade, sem multa.
```

---

### RODAPÉ DO CHECKOUT

```
Máxima Finance IA  |  CNPJ: [XX.XXX.XXX/XXXX-XX]  |  contato@maximafinance.com.br
Termos de Uso  |  Política de Privacidade  |  Política de Cancelamento
```

---

## TOKENS PARA DEV — STRIPE INTEGRATION

```javascript
// Parâmetros para criação do checkout session (Stripe)
const checkoutConfig = {
  // Plano Pro
  pro: {
    priceId: '[STRIPE_PRICE_ID_PRO]',           // R$97/mês
    successUrl: '/obrigado?plano=pro',
    cancelUrl: '/planos',
  },
  // Plano Business
  business: {
    priceId: '[STRIPE_PRICE_ID_BUSINESS]',      // R$297/mês
    successUrl: '/obrigado?plano=business',
    cancelUrl: '/planos',
  }
}

// Dados para Supabase — pós pagamento confirmado
const userActivation = {
  plano: 'pro' | 'business',
  stripeCustomerId: '[stripe_customer_id]',
  stripeSubscriptionId: '[stripe_subscription_id]',
  ativadoEm: new Date().toISOString(),
  status: 'ativo'
}
```

---

## VARIAÇÕES A/B PARA TESTES FUTUROS

| Elemento | Versão A (padrão) | Versão B (alternativa) |
|---|---|---|
| Título coluna direita | "Complete seu cadastro e acesse agora" | "Comece sua análise em 2 minutos" |
| Botão CTA | "ATIVAR MINHA CONTA POR R$ X/MÊS" | "QUERO ENTENDER MINHA EMPRESA" |
| Garantia | "7 dias" | "Primeira semana gratuita, depois decide" |
| Depoimento em destaque | Empresária SP | Dono distribuidora MG |

---

*Checkpoint: esta seção fecha o funil de conversão. Com checkout pronto + Thank You Page (outputs/2026-05-12) + Stripe tokens (outputs/2026-06-30), o fluxo de pagamento está 100% documentado para implementação.*
