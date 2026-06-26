# Kit Coupon REVISAO_SEMESTRAL_JUNHO — Assets Prontos para os Próximos 4 Dias
*Produzido por Bella — Turno da Noite — 26/06/2026*

---

> **Contexto:** Coupon `REVISAO_SEMESTRAL_JUNHO` expira 30/jun — 4 dias restantes.
> Estes assets são para uso imediato: stories, post, e-mail de urgência e mensagens WhatsApp.
> **Use hoje e amanhã (26–27/jun) para máximo impacto.**

---

## 1. STORIES INSTAGRAM — 3 SEQUÊNCIA (para postar hoje ou amanhã)

### Story 1 — Gancho (15 seg)
**Visual:** Fundo escuro, texto branco centralizado + emojis

```
Você ainda não leu
o DRE de junho? 📊

👇 Desliza para ver
o que está te custando.
```
**CTA:** Arraste para cima

---

### Story 2 — Dor (15 seg)
**Visual:** Fundo roxo escuro, texto claro

```
Metade das empresas entra
em julho sem saber:

❌ Qual produto deu prejuízo
❌ Se a margem subiu ou caiu
❌ Quanto de caixa sobra

O DRE já tem a resposta.
Você só precisa ler.
```

---

### Story 3 — Oferta + Urgência (15 seg)
**Visual:** Fundo com gradiente roxo, botão CTA destacado

```
Hoje a Máxima Finance IA
interpreta seu DRE em minutos.

Use o cupom:

REVISAO_SEMESTRAL_JUNHO

↓ Desconto ativo por 4 dias ↓
[ACESSAR AGORA]
```
**Sticker:** Contagem regressiva até 30/jun

---

## 2. POST INSTAGRAM — Carrossel 5 Slides (urgência de semestre)

### Slide 1 — Capa
**Título:** `4 dias para fechar o semestre.`
**Subtítulo:** `Você sabe onde foi parar o lucro de junho?`

---

### Slide 2 — O problema
**Título:** `Empresário que não lê o DRE de junho entra em julho às cegas`

**Texto:**
Sem o DRE lido:
- Você define meta de julho sem base
- Repete os erros do 1º semestre
- Perde a janela de ajuste de preços

Isso tem nome: decisão no escuro.

---

### Slide 3 — A solução existe
**Título:** `Não precisa ser contador para entender o DRE`

**Texto:**
A Máxima Finance IA lê o seu DRE
e entrega o diagnóstico em português.

Sem planilha. Sem jargão.
Só os números que importam para você.

---

### Slide 4 — Prova / Como funciona
**Título:** `Em menos de 5 minutos você sabe:`

```
✅ Se a margem melhorou ou piorou
✅ Qual despesa está fora do controle
✅ Se você pode contratar em julho
✅ Onde cortar sem demitir
```

---

### Slide 5 — CTA + Coupon
**Título:** `Revisão semestral com IA. Hoje.`

**Texto:**
Use o cupom `REVISAO_SEMESTRAL_JUNHO`
e comece com desconto.

Válido até 30/06 — **4 dias apenas.**

👉 Link na bio

---

## 3. E-MAIL DE URGÊNCIA (para base de leads)

**Assunto:** Você fechou o 1º semestre. Mas sabe o que os números dizem?

**Preview:** 4 dias para usar o coupon de revisão semestral.

---

Oi [nome],

Junho está acabando.

E a maioria dos empresários vai entrar em julho fazendo a mesma coisa que fez em janeiro: apostando sem dados.

Porque o DRE de junho já tem as respostas:

- Qual foi a margem real do semestre?
- Qual produto deu mais lucro — e qual deu prejuízo disfarçado?
- Quanto de caixa você tem para investir em julho?

Essas perguntas parecem simples. Mas sem o DRE lido e interpretado, são só palpites.

**A Máxima Finance IA interpreta o seu DRE em minutos.**

Você faz o upload, a Sofia analisa, e você recebe o diagnóstico em português — sem precisar de contador, sem planilha, sem jargão.

E até 30 de junho, você começa com desconto:

```
REVISAO_SEMESTRAL_JUNHO
```

**[ACESSAR COM DESCONTO →]**

O coupon expira em 4 dias.

Depois disso, só na próxima revisão semestral — em dezembro.

Até lá,
Karina
Máxima Finance IA

---

*P.S. Se quiser ver o app ao vivo antes de assinar, [clique aqui] para entrar na lista da live de demonstração.*

---

## 4. MENSAGENS WHATSAPP — 3 mensagens (para lista de contatos / grupo de empresários)

### Mensagem 1 — Para contatos frios (nunca usaram o app)

```
Oi [nome], tudo bem?

Você já tem o DRE de junho em mãos?

Criei uma IA que interpreta o DRE da sua empresa em português — sem precisar de contador.

Você faz o upload, e em minutos recebe o diagnóstico: margem, custos fora do controle, o que ajustar em julho.

Até 30/jun tem desconto com o cupom REVISAO_SEMESTRAL_JUNHO.

Quer dar uma olhada? [link]
```

---

### Mensagem 2 — Para leads quentes (demonstraram interesse antes)

```
[nome], lembra que você perguntou sobre a Máxima Finance?

Aproveitei o fechamento de semestre para liberar um cupom de desconto.

REVISAO_SEMESTRAL_JUNHO — válido até domingo 30/jun.

Se quiser entrar e fazer a revisão do DRE de junho agora, é o momento certo.

[link para assinar]

Qualquer dúvida me fala aqui.
```

---

### Mensagem 3 — Para usuários gratuitos (para upgrade Pro)

```
Oi [nome]!

Você está no plano gratuito da Máxima Finance.

Só até 30/jun tem um coupon especial para quem quer subir para o Pro e fazer a revisão completa do 1º semestre:

REVISAO_SEMESTRAL_JUNHO

Com o Pro você desbloqueia:
✅ Análises ilimitadas
✅ Chat Sofia sem limite
✅ Histórico semestral comparado

[FAZER UPGRADE →]

Válido por 4 dias. Depois o preço volta ao normal.
```

---

## 5. TOKENS PARA DEV (implementação do coupon no Stripe + banner)

```javascript
// Banner de urgência — exibir em todas as páginas logadas até 30/jun
const COUPON_BANNER = {
  code: 'REVISAO_SEMESTRAL_JUNHO',
  expires: '2026-06-30T23:59:59-03:00',
  message: '⚡ Revisão semestral com desconto — válido até 30/jun. Use o cupom ',
  cta: 'Ativar agora',
  ctaLink: '/upgrade?coupon=REVISAO_SEMESTRAL_JUNHO',
  variant: 'warning', // fundo amarelo/laranja
  dismissible: false, // manter visível
}

// Stripe coupon — criar no painel (Settings > Coupons)
const STRIPE_COUPON = {
  id: 'REVISAO_SEMESTRAL_JUNHO',
  percent_off: 30, // sugestão: 30% de desconto
  duration: 'once',
  redeem_by: 1751328000, // Unix: 30/jun/2026 23:59 BRT
  max_redemptions: 100,
}

// Lógica de exibição do banner
function shouldShowCouponBanner() {
  const now = new Date()
  const expiry = new Date('2026-06-30T23:59:59-03:00')
  return now < expiry
}
```

---

## CHECKLIST DE USO IMEDIATO

- [ ] Criar coupon `REVISAO_SEMESTRAL_JUNHO` no Stripe (15 min)
- [ ] Postar stories (sequência 3 slides) — hoje 26/jun ou amanhã 27/jun
- [ ] Disparar e-mail para base de leads — hoje à noite ou manhã 27/jun
- [ ] Enviar mensagem WhatsApp para leads quentes — amanhã cedo
- [ ] Ativar banner de urgência no app (tokens acima)
- [ ] Agendar live de demonstração — roteiro pronto em `outputs/2026-06-24/pagina-vendas-secao.md`
