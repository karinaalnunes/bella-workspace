# Página de Vendas — Seção: Canal de Contadores / Parceiros B2B
*Máxima Finance IA — Noite 28/05/2026*

---

## CONTEXTO ESTRATÉGICO

Contadores são o maior canal de distribuição não explorado do Máxima Finance IA.
Cada contador atende em média 30–80 PMEs. Uma parceria bem posicionada multiplica o alcance sem custo de aquisição.

Posicionamento crítico: **a Máxima não substitui o contador — ela entrega ao cliente o que o contador não tem tempo de entregar: diagnóstico em linguagem simples, todo mês, em minutos.**

---

## SEÇÃO: PARA CONTADORES E ESCRITÓRIOS CONTÁBEIS

### Headline principal
**Seus clientes tomam decisões financeiras sem entender os números que você entrega.**

### Subheadline
A Máxima Finance IA transforma o DRE que você já faz em linguagem que o empresário entende — sem substituir você.

---

### BLOCO 1 — A DOR DO CONTADOR

> Você fecha o DRE do seu cliente, envia por e-mail, e ele te responde: *"Tá, mas como fico? Tô bem ou mal?"*

Você explica. Ele finge entender. No mês seguinte, repete-se.

O problema não é o seu trabalho. É que o DRE foi feito para contadores, não para empresários.

**O que muda com a Máxima:**
- Você continua fazendo o DRE do jeito que faz
- A Máxima interpreta, em português simples, para o cliente
- O cliente para de ligar para você com perguntas básicas
- Você pode focar no que agrega mais valor: planejamento, compliance, estratégia

---

### BLOCO 2 — COMO FUNCIONA A PARCERIA

**3 passos simples:**

**① Você indica ou integra**
Indique o Máxima Finance IA para seu cliente, ou integre via API (plano Business) para enviar o DRE diretamente pela sua plataforma.

**② O cliente recebe o diagnóstico**
Assim que o DRE é processado, o cliente recebe:
- Resumo em linguagem simples (sem jargão)
- 3 alertas prioritários do mês
- Comparativo com o mês anterior
- Chat Sofia: tira dúvidas em tempo real, 24h

**③ Você recebe a comissão**
Programa de indicação com comissão recorrente enquanto o cliente for assinante.

---

### BLOCO 3 — O QUE VOCÊ GANHA

| Benefício | Detalhe |
|---|---|
| **Comissão recorrente** | 20% do plano indicado, todo mês |
| **Cliente mais engajado** | Empresário que entende os números pergunta melhor e valoriza mais o contador |
| **Menos ligações básicas** | A Sofia resolve as dúvidas de "o que significa isso?" |
| **Diferencial competitivo** | Você oferece algo que 99% dos escritórios contábeis não oferecem |
| **Dashboard do parceiro** | Veja todos os seus clientes indicados em um painel único |

---

### BLOCO 4 — PARA QUEM É

**Ideal para:**
- Contadores e escritórios contábeis que atendem PMEs (faturamento R$ 30k–500k/mês)
- BPOs financeiros que buscam valor agregado
- Consultores financeiros que querem escalar atendimento

**Não é para:**
- Escritórios 100% voltados para grandes empresas com CFO interno
- Contadores que atendem apenas MEIs (abaixo do escopo do DRE completo)

---

### BLOCO 5 — DEPOIMENTO PLACEHOLDER (inserir real pré-lançamento)

> *"Meus clientes pararam de me ligar perguntando 'tô lucrando ou não'. Agora eles chegam com perguntas melhores — e eu consigo cobrar mais pela consultoria estratégica."*
> — **[Nome], Contador, [Cidade]**

---

### BLOCO 6 — CTA PARCEIROS

**Headline:** Quer oferecer diagnóstico financeiro com IA para seus clientes?

**Subheadline:** Seja um parceiro Máxima Finance. É gratuito para se cadastrar.

**CTA primário:** → Quero ser parceiro
**CTA secundário:** → Falar com a equipe

**Microcopy:** Sem mensalidade para o parceiro. Comissão de 20% recorrente. Cancele quando quiser.

---

### TOKENS PARA DEV

```
// Rotas sugeridas
/parceiros          → Página de captação de parceiros (esta seção)
/parceiros/painel   → Dashboard do parceiro (clientes indicados + comissões)

// Supabase
tabela: partners
campos: id, name, email, crm_number, referral_code (unique), commission_rate (default 0.20), created_at
tabela: partner_referrals
campos: id, partner_id (FK), customer_id (FK), plan, mrr, commission_amount, status (active/cancelled), created_at

// Stripe
- metadata do customer: { referredBy: partner_id }
- webhook: customer.subscription.created → calcular e registrar comissão
- webhook: customer.subscription.deleted → atualizar status no Supabase

// Resend — e-mail de boas-vindas ao parceiro
trigger: INSERT em partners
template_id: "welcome-partner"
variáveis: { name, referral_code, referral_link }

// Link de indicação
https://maximafinance.com.br/cadastro?ref={referral_code}
```

---

### MÉTRICAS PARA ACOMPANHAR

| Métrica | Meta inicial |
|---|---|
| Parceiros cadastrados | 20 nos primeiros 60 dias |
| Taxa de conversão parceiro→cliente | 30% (por indicação) |
| Ticket médio do cliente indicado | Pro (R$97) |
| LTV estimado por parceiro ativo | R$ 582/ano (30% × 10 clientes × R$97 × 20% × 12m) |

---

*Produzido por Bella — Turno da noite 28/05/2026*
