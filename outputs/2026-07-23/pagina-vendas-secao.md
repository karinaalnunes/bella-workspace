# Máxima Finance IA — Landing Page de Captação de Leads (Pré-Lançamento)
*Tipo de ativo: página de pré-cadastro / lista de espera*
*Gerado por Bella — Turno da noite 23/07/2026*

---

## OBJETIVO DESTA PÁGINA

Capturar e-mails de empresários interessados **antes** do lançamento oficial.
Criar senso de exclusividade, urgência e antecipar demanda real.
Meta: 200 leads qualificados na lista de espera antes de abrir o checkout.

---

## ESTRUTURA DA PÁGINA (HTML/React — mobile-first)

---

### BLOCO 1 — HEADLINE PRINCIPAL

```
AVISO ANTECIPADO: Máxima Finance IA

Seu DRE passa a falar por si mesmo —
e a Sofia explica tudo para você.

Entre na lista VIP e seja um dos primeiros a acessar.
```

**Subtítulo:**
```
Chega de DRE incompreensível.
A Máxima Finance IA lê o seu relatório, identifica onde você está perdendo dinheiro
e te diz o que fazer — em português simples, sem precisar de contador.
```

**CTA principal:**
```
[Quero meu acesso antecipado →]
```
*(campo de e-mail + botão verde)*

**Prova social abaixo do CTA:**
```
✅ Mais de [XXX] empresários já na lista de espera
```

---

### BLOCO 2 — QUALIFICADOR (Para quem é isso?)

**Título:**
```
Essa ferramenta foi criada para você se...
```

**Lista com ícone de check:**
```
✅ Você fatura entre R$30 mil e R$500 mil por mês
✅ Recebe o DRE do contador e não sabe o que fazer com ele
✅ Já terminou o mês no positivo no papel — mas sem dinheiro no caixa
✅ Toma decisões de preço e contratação "no feeling"
✅ Sente que deveria entender mais de finanças, mas não tem tempo para aprender
```

---

### BLOCO 3 — O QUE VOCÊ VAI RECEBER

**Título:**
```
Com acesso antecipado, você garante:
```

**Cards (3 colunas no desktop, empilhados no mobile):**

**Card 1 — Gratuito por 30 dias**
```
🎁 Acesso gratuito estendido
Enquanto a lista VIP é aberta, você usa tudo
pelo dobro do período de teste — sem cartão.
```

**Card 2 — Onboarding 1:1**
```
📞 Sessão de configuração com a equipe
Para os primeiros 50 cadastros:
sessão ao vivo para configurar sua análise de DRE.
```

**Card 3 — Preço de fundador**
```
🔒 Preço travado de fundador
Os primeiros usuários pagam R$67/mês no plano Pro —
e esse valor nunca sobe enquanto a conta estiver ativa.
```

---

### BLOCO 4 — COMO FUNCIONA (versão resumida, 3 passos)

**Título:**
```
Em 3 passos, seu DRE deixa de ser enigma
```

**Passo 1:**
```
📤 Você faz o upload do DRE
PDF, Excel, foto do relatório — a Máxima lê qualquer formato.
```

**Passo 2:**
```
🤖 A IA analisa e diagnostica
Em segundos, você recebe um relatório em português:
o que está bom, o que está mal e por quê.
```

**Passo 3:**
```
💬 A Sofia responde suas dúvidas
"Minha margem está boa?"
"Posso contratar mais um funcionário?"
"Por que sobrou tão pouco esse mês?"
Pergunte em texto normal — ela responde com base no seu próprio DRE.
```

---

### BLOCO 5 — DEPOIMENTO PLACEHOLDER (para substituir quando tiver cliente real)

```
"Eu tinha medo de olhar pro DRE porque nunca entendia nada.
Com a Máxima, pela primeira vez eu vi onde minha empresa estava
sangrando dinheiro. E resolvi."

— Empresário do setor de [segmento], faturamento R$[X]/mês
(Beta tester — depoimento real em breve)
```

*Nota de implementação: substituir por depoimento real assim que os primeiros beta users ativarem.*

---

### BLOCO 6 — FORMULÁRIO PRINCIPAL (repetição para mobile)

**Título:**
```
Garanta seu acesso antecipado agora
(Gratuito — sem compromisso)
```

**Campos:**
```
Nome da empresa: [campo]
Seu nome: [campo]
E-mail profissional: [campo]
Faturamento mensal aproximado: [dropdown]
  - Até R$30 mil
  - R$30 mil a R$100 mil
  - R$100 mil a R$300 mil
  - R$300 mil a R$500 mil
  - Acima de R$500 mil

[Entrar na lista VIP agora →]
```

**Microcopy abaixo do botão:**
```
🔒 Sem spam. Sem cartão. Você recebe um e-mail quando abrirmos as vagas.
```

---

### BLOCO 7 — FAQ DA LANDING PAGE (4 perguntas curtas)

**P: Preciso pagar alguma coisa para entrar na lista?**
R: Não. A lista de espera é completamente gratuita. Você só decide se quer ser cliente quando recebermos o convite.

**P: Quando abre o acesso?**
R: Estamos em fase final de desenvolvimento. A previsão é em breve — quem está na lista recebe com antecedência.

**P: Meu contador pode usar junto comigo?**
R: Sim. O plano Business inclui acesso para mais de um usuário. Mas muitos clientes usam sozinhos, sem precisar do contador.

**P: E se eu não gostar?**
R: Você tem 7 dias de garantia após o primeiro pagamento. Pede o reembolso, devolvo sem perguntas.

---

### BLOCO 8 — RODAPÉ DA LANDING PAGE

```
Máxima Finance IA © 2026
Todos os direitos reservados.

[Política de Privacidade] | [Termos de Uso]

Desenvolvido com ❤️ para empresários brasileiros que merecem entender as próprias finanças.
```

---

## INSTRUÇÕES DE IMPLEMENTAÇÃO

**Stack:** React (já existente no projeto)
**Formulário:** integrar com Supabase (tabela `leads_waitlist`) + trigger de e-mail via Resend
**Campos obrigatórios:** nome, e-mail, faturamento mensal
**Campos opcionais:** nome da empresa
**Após submit:** redirecionar para `/obrigado` (thank you page — já produzida em 12/07)
**Pixel:** preparar para receber pixel Meta Ads (para lookalike no futuro)

**Prioridade:** 🔥 Alta — essa página pode ser publicada ANTES do app estar 100% pronto.
Capturar leads agora = lançamento com demanda já aquecida.

---

*Próximo ativo sugerido: sequência de e-mails de boas-vindas para a lista de espera (3 e-mails de nutrição pré-lançamento)*
