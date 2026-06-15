# Máxima Finance IA — Programa de Indicação / Referral
*Turno da Noite — 15/06/2026 | Bella*

---

## CONTEXTO ESTRATÉGICO

Com o lançamento se aproximando (janela: antes do Conta Azul CON — 5/ago), crescimento viral via indicação pode acelerar a base de clientes sem custo marginal de aquisição. Esta seção contém **copy completa do Programa "Indica e Ganha"**, pronta para implementar na plataforma e em e-mails.

---

## NOME DO PROGRAMA

**"Indica e Ganha" — Máxima Finance IA**

*Tagline:* Você conhece um empresário que merece entender as finanças do negócio dele. Apresente a Máxima — e os dois ganham.

---

## PÁGINA DO PROGRAMA (copy completa)

### Headline
> **Indique um empresário. Ganhe 1 mês grátis. Ele começa com 30 dias free.**

### Subheadline
> Simples assim. Sem truques, sem teto, sem prazo de validade. Cada indicação válida = 1 mês gratuito na sua conta.

---

### Bloco 1 — Como funciona (3 passos)

**Passo 1 — Copie seu link único**
> Cada conta tem um link de indicação exclusivo. Copie e envie para quem você acha que vai amar a Máxima.

**Passo 2 — Seu indicado experimenta de graça**
> Quem usar seu link ganha 30 dias no plano Pro sem pagar nada. Sem necessidade de cartão de crédito.

**Passo 3 — Você ganha 1 mês grátis**
> Assim que o indicado completar 7 dias ativos na plataforma, seu próximo mês é automaticamente zerado.

---

### Bloco 2 — Contador / Acumulador

> **Você já ganhou:** [X] meses grátis  
> **Total economizado:** R$ [X × valor do plano]  
> **Indicações ativas:** [X] empresários usando a Máxima

*(Tokens dev: `user.referral_months_earned`, `user.referral_savings`, `user.referral_active_count`)*

---

### Bloco 3 — Para quem indicar?

> Indique se seu colega empresário:
> - Fatura entre R$ 30 mil e R$ 500 mil por mês
> - Reclama que "não sobra dinheiro mesmo vendendo bem"
> - Usa planilha ou não acompanha o DRE
> - Quer crescer mas tem medo de arriscar sem dados

> **Resumo:** qualquer dono de negócio que merece uma visão clara das finanças.

---

### Bloco 4 — Compartilhe agora

**Botão primário:** `Copiar meu link de indicação`

**Mensagem pré-pronta para WhatsApp:**

> *Oi [nome], uso a Máxima Finance IA para entender o DRE do meu negócio em segundos — a IA explica tudo em português simples, sem precisar de contador. Você pode testar 30 dias grátis usando meu link: [LINK]. Vale muito a pena.*

*(Botão: "Enviar via WhatsApp" — abre wa.me com texto pré-preenchido)*

**Mensagem pré-pronta para e-mail:**

> *Assunto: Te apresento uma ferramenta que mudou como cuido das finanças da minha empresa*
>
> Oi [nome],
>
> Comecei a usar a Máxima Finance IA para analisar o DRE do meu negócio. A ferramenta usa inteligência artificial para interpretar os números em português simples — sem precisar de contador para cada dúvida.
>
> Você pode testar por 30 dias sem pagar nada: [LINK]
>
> Abraço,
> [Nome do indicante]

---

### Bloco 5 — FAQ do Programa

**Quantas indicações posso fazer?**
> Sem limite. Cada indicação válida = 1 mês grátis. Não tem teto, não tem prazo de expiração dos créditos.

**O que é uma "indicação válida"?**
> O indicado precisa criar conta usando seu link E completar 7 dias com pelo menos 1 análise de DRE feita.

**Quando aparece o desconto na minha conta?**
> No momento em que o indicado completa 7 dias ativos. Você recebe um e-mail de confirmação.

**E se o indicado já tiver conta?**
> Nesse caso a indicação não é contabilizada. O link só funciona para novos usuários.

**Posso usar os meses grátis para pagar plano Business?**
> Sim. Os créditos valem para qualquer plano que você tiver ativo.

**Tem prazo de validade?**
> Não. Os meses acumulam indefinidamente até você usá-los.

---

### CTA Final

> **Comece agora — seu link já está esperando.**

`[Copiar link de indicação]`

*Já compartilhou com alguém? Nos conte no suporte — gostamos de ouvir histórias de empresários se ajudando.*

---

## E-MAIL DE CONFIRMAÇÃO DE INDICAÇÃO

**Assunto:** Sua indicação foi confirmada — 1 mês grátis adicionado 🎉

> Oi [nome],
>
> Ótima notícia: [nome do indicado] completou 7 dias ativos na Máxima Finance IA usando seu link.
>
> **1 mês grátis foi adicionado à sua conta.**
>
> Você agora tem [X] meses de crédito acumulado — equivalente a R$ [X × valor].
>
> Quer continuar economizando? Compartilhe seu link com mais um empresário:
>
> [LINK PESSOAL]
>
> Obrigada por fazer a Máxima crescer com indicações de qualidade.
>
> Equipe Máxima Finance IA

---

## E-MAIL PARA INDICADO (boas-vindas via referral)

**Assunto:** [Nome do indicante] te deu 30 dias grátis na Máxima Finance IA

> Oi [nome do indicado],
>
> [Nome do indicante] acha que a Máxima Finance IA pode transformar a forma como você cuida das finanças da sua empresa — e por isso te deu 30 dias grátis no plano Pro.
>
> **O que você vai conseguir fazer:**
> - Fazer upload do DRE e receber um diagnóstico em português simples em menos de 2 minutos
> - Perguntar para a Sofia (nossa IA financeira) o que cada número significa
> - Identificar onde sua margem está vazando — sem precisar de contador
>
> Comece agora (sem cartão de crédito):
>
> [BOTÃO: Criar minha conta grátis]
>
> Se tiver qualquer dúvida, a Sofia responde no chat — é literalmente para isso que ela existe.
>
> Equipe Máxima Finance IA

---

## TOKENS PARA DEV

```js
// Página do programa
const referralLink = `https://maximafinance.com.br/ref/${user.referral_code}`;

// Indicações e créditos
user.referral_months_earned     // número de meses ganhos (total histórico)
user.referral_months_available  // saldo atual disponível
user.referral_savings_brl       // economia em R$ acumulada
user.referral_active_count      // indicações ativas (já cadastradas, >7 dias)
user.referral_pending_count     // indicações cadastradas mas < 7 dias ativos

// Webhooks Stripe / Supabase
// Trigger: user_created via referral_code → inicia contagem 7 dias
// Trigger: day_7_active → credita 1 mês em referrer + envia e-mail confirmação
// Edge function: apply_referral_credit(userId, months=1)
```

---

## NOTA ESTRATÉGICA

O programa de indicação deve ser comunicado **no momento de maior satisfação do usuário** — logo após a primeira análise de DRE (estado "Aha moment"). Sugestão: popup ou banner após análise concluída com copy:

> *"Gostou do diagnóstico? Indique um colega empresário e ganhe 1 mês grátis."*
> [Botão: Ver o programa de indicação]

---

*Produzido por Bella — Turno da Noite 15/06/2026*
