# Página de Vendas — Sequência de Pré-Lançamento / Waitlist
*Turno da noite — 21/05/2026*

---

## CONTEXTO

Com o app ~70% pronto e o lançamento se aproximando, o próximo passo é construir uma lista de espera aquecida **antes** de abrir o produto. Isso garante as primeiras vendas nos primeiros 48h após o lançamento.

Esta seção entrega:
1. **Página de Espera (Waitlist)** — copy completo para a landing page
2. **Sequência de 3 E-mails de Aquecimento** — D-14, D-7 e D-1 (dia do lançamento)
3. **Tokens dev** para implementar com React + Supabase

---

## PARTE 1 — PÁGINA DE ESPERA (WAITLIST)

### URL sugerida: `maximafinance.com.br/lista-vip`

---

### [HERO DA WAITLIST]

**Headline:**
```
Você vai ser o primeiro a saber quando abrir.
```

**Subheadline:**
```
O Máxima Finance IA está quase pronto.
Empresários que entrarem na lista VIP ganham:
→ Acesso antecipado (antes de todo mundo)
→ 30 dias grátis no plano Pro (R$97/mês)
→ Sessão de diagnóstico financeiro gratuita
```

**CTA principal:**
```
[Quero entrar na lista VIP — é grátis]
```

**Microcopy abaixo do botão:**
```
Sem spam. Sem compromisso. Só avisamos quando abrir.
```

---

### [FORMULÁRIO DE CAPTURA]

**Campos:**
```
Nome: [________________]
E-mail: [________________]
WhatsApp (opcional): [________________]

[Quero meu acesso VIP →]
```

**Token dev:**
```tsx
// Supabase insert na tabela `waitlist`
const { error } = await supabase
  .from('waitlist')
  .insert({
    name: formData.name,
    email: formData.email,
    phone: formData.phone || null,
    source: 'waitlist_page',
    created_at: new Date().toISOString()
  })
```

---

### [BLOCO DE URGÊNCIA — CONTADOR DE VAGAS]

**Copy:**
```
⚠️ Vagas VIP limitadas: 200 empresários.
[███████████░░░░░] 147 de 200 preenchidas.

Por que limitamos? Porque cada empresa recebe
análise personalizada no primeiro acesso.
```

**Token dev:**
```tsx
// Query para contar registros na waitlist
const { count } = await supabase
  .from('waitlist')
  .select('*', { count: 'exact', head: true })
// Exibir: `${count} de 200 preenchidas`
```

---

### [BLOCO "O QUE É O MÁXIMA FINANCE IA"]

**Copy:**
```
📊 O que é o Máxima Finance IA?

É a única plataforma que transforma seu DRE num
diagnóstico financeiro em português direto ao ponto.

Você faz upload → a IA lê → você recebe:
✓ Os 3 pontos que estão consumindo sua margem
✓ O índice de saúde financeira da sua empresa (0–100)
✓ As 5 ações prioritárias para o próximo mês

Sem precisar entender planilha. Sem contador na ligação.
Resultado em menos de 3 minutos.
```

---

### [BLOCO DE PROVA — PROBLEMA QUE RESOLVE]

**Copy:**
```
Para quem é:

✅ Empresa com faturamento entre R$ 30 mil e R$ 500 mil/mês
✅ Dono que sabe que tem que olhar os números, mas não sabe por onde começar
✅ Empresário que já teve contador, planilha ou ERP — e ainda não entendeu o DRE

Para quem NÃO é:
❌ Grandes corporações com CFO
❌ Quem já tem gestor financeiro dedicado
```

---

### [RODAPÉ DA PÁGINA DE ESPERA]

**Copy:**
```
© 2026 Máxima Finance IA
Construído para o empresário brasileiro que fatura de verdade — e quer saber o que sobra.

Dúvidas? fale@maximafinance.com.br
```

---

## PARTE 2 — SEQUÊNCIA DE E-MAILS PRÉ-LANÇAMENTO

---

### E-MAIL 1 — D-14 (14 dias antes do lançamento)
**Assunto:** `Você está na lista. Aqui está o que vem por aí.`

```
Olá, [NOME]!

Você entrou na lista VIP do Máxima Finance IA.

Enquanto os outros vão ficar de fora, você vai ser
um dos primeiros a testar quando a gente abrir.

Mas antes de contar tudo, deixa eu te perguntar uma coisa:

Você sabe qual é a sua margem líquida este mês?

Não o faturamento. A margem. O que sobrou de verdade
depois de pagar tudo — folha, fornecedor, imposto, aluguel.

A maioria dos empresários que vai entrar no Máxima
me disse que não sabe com precisão. Ou que precisa
perguntar pro contador. Ou que precisa abrir uma
planilha que ninguém mais atualiza.

Esse é exatamente o problema que a gente resolve.

No próximo e-mail, vou te mostrar como funciona
o diagnóstico de IA na prática — com um DRE real.

Até lá,
Karina Alnunes
Fundadora — Máxima Finance IA

P.S. Se quiser, já me responde aqui: qual é o maior
desafio que você tem hoje com o financeiro da sua empresa?
Lerei todas as respostas.
```

---

### E-MAIL 2 — D-7 (7 dias antes do lançamento)
**Assunto:** `[Bastidores] Como o Máxima leu um DRE em 2m47s`

```
Olá, [NOME]!

Faltam 7 dias.

Semana passada perguntei qual era seu maior desafio financeiro.
Recebi dezenas de respostas. As três mais comuns:

1. "Não sei se estou no lucro ou no prejuízo de verdade"
2. "Sei o faturamento, mas não sei o que sobra"
3. "Tenho contador, mas ele só me manda o DRE. Não explica nada."

É exatamente por isso que o Máxima existe.

👉 Aqui está o que acontece quando você faz upload do seu DRE:

1. O sistema lê a estrutura do documento (PDF, Excel ou foto)
2. A IA identifica receita bruta, CMV, despesas fixas, variáveis e resultado líquido
3. Em menos de 3 minutos você recebe:
   → Índice de saúde financeira (0 a 100)
   → Os 3 principais pontos de atenção
   → 5 ações prioritárias em linguagem simples

Não é magia. É tecnologia aplicada ao problema certo.

Na próxima semana você vai poder testar isso com o DRE da sua empresa.

Os primeiros 200 VIPs ganham 30 dias grátis no plano Pro.

Até amanhã,
Karina

P.S. Compartilhe este link com um sócio ou colega empresário:
[link da waitlist]
```

---

### E-MAIL 3 — D-1 (véspera do lançamento)
**Assunto:** `🔓 Amanhã abre. Você está na lista.`

```
Olá, [NOME]!

Amanhã, às 10h, o Máxima Finance IA abre para o público.

Mas você não é público. Você é VIP.

Isso significa que às 9h você vai receber um e-mail
com o link de acesso antecipado — 1 hora antes de todo mundo.

Sua vaga VIP inclui:
✅ 30 dias grátis no plano Pro (R$ 97/mês)
✅ Acesso prioritário (sem fila)
✅ Sessão de diagnóstico financeiro gratuita na primeira semana

Para garantir sua vaga, só uma coisa:
→ Abra o e-mail amanhã às 9h e clique no link.
→ Os primeiros 200 que acessarem garantem o benefício.

Se você não conseguir amanhã, me avisa — vou
segurar sua vaga por mais 24h.

Até amanhã,
Karina

P.S. Amanhã você vai finalmente saber, com precisão,
o que está sobrando da sua empresa. Nos vemos às 9h.
```

---

## PARTE 3 — TOKENS DEV

### Tabela Supabase — `waitlist`
```sql
create table waitlist (
  id uuid default gen_random_uuid() primary key,
  name text not null,
  email text not null unique,
  phone text,
  source text default 'waitlist_page',
  is_vip boolean default true,
  notified_d14 boolean default false,
  notified_d7 boolean default false,
  notified_d1 boolean default false,
  converted boolean default false,
  created_at timestamptz default now()
);
```

### Edge Function — Envio e-mail via Resend
```typescript
// supabase/functions/waitlist-welcome/index.ts
import { Resend } from 'resend'

const resend = new Resend(Deno.env.get('RESEND_API_KEY'))

Deno.serve(async (req) => {
  const { email, name } = await req.json()

  await resend.emails.send({
    from: 'Karina <karina@maximafinance.com.br>',
    to: email,
    subject: 'Você está na lista. Aqui está o que vem por aí.',
    html: `<p>Olá, ${name}!</p>...` // usar template do E-mail 1
  })

  return new Response(JSON.stringify({ success: true }))
})
```

---

## MÉTRICAS DE SUCESSO

| Métrica | Meta mínima | Meta ideal |
|---|---|---|
| Conversão visitante → waitlist | 25% | 40% |
| Abertura E-mail D-14 | 45% | 60% |
| Abertura E-mail D-7 | 40% | 55% |
| Abertura E-mail D-1 | 55% | 70% |
| Conversão waitlist → cliente pago | 15% | 25% |

**Meta: 200 VIPs na lista → 30–50 clientes pagos no dia do lançamento**

---

*Bella — Turno da noite 21/05/2026*
