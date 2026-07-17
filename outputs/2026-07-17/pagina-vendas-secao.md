# Página de Vendas — Sequência de Abandono de Checkout
*Turno da Noite — 17/07/2026 | Bella*

---

## CONTEXTO

Seção complementar à integração Stripe (próxima sprint).
Empresários que chegam ao checkout e não finalizam a compra — recuperação via e-mail em 3 etapas.
Taxa média de recuperação de checkout abandonado: 10–15% do volume não convertido.

---

## SEQUÊNCIA: ABANDONO DE CHECKOUT (3 E-MAILS)

---

### E-MAIL 1 — Enviado: 1h após abandono
**Assunto:** Você esqueceu alguma coisa, [nome]

---

Oi, [nome]!

Você estava quase lá.

Vimos que você começou a assinar o Máxima Finance IA — e parou na metade.

Pode ter sido uma distração, uma dúvida de última hora, ou simplesmente a vida que puxou você para outro lado.

Está tudo bem.

Mas antes de você ir embora de vez, deixa eu te fazer uma pergunta rápida:

**Quanto você perdeu nos últimos 3 meses por não ter clareza sobre o que está acontecendo com o seu dinheiro?**

Não precisa me responder. Só pensa um instante.

Quando você está pronto, sua conta continua aqui esperando por você:

**→ [BOTÃO: Finalizar minha assinatura]**

Se tiver qualquer dúvida antes de assinar, é só responder esse e-mail.

Atenciosamente,
**Karina Alnunes**
Máxima Finance IA

---

*P.S.: O plano Pro inclui análise ilimitada de DRE + Chat Sofia, tudo por R$97/mês. Cancele quando quiser, sem multa.*

---

### E-MAIL 2 — Enviado: 24h após abandono
**Assunto:** Esse erro custa caro (e é silencioso)

---

Oi, [nome].

Deixa eu te contar sobre a Débora.

Ela tinha uma empresa de serviços que faturava R$180 mil por mês.

Todo mês ela olhava para a conta bancária e pensava: *"Por que nunca sobra?"*

Ela tentou planilha. Contratou contador. Fez curso de finanças.

Nada resolvia porque ninguém conseguia traduzir os números para ela de um jeito que fizesse sentido.

Até que ela subiu o DRE de um mês no Máxima Finance IA.

Em 8 minutos, a IA identificou que ela tinha **3 categorias de despesas crescendo acima da receita** — e que uma delas sozinha consumia 22% da margem.

Ela nunca tinha notado porque os valores pareciam pequenos separados.

Juntos, estavam destruindo a lucratividade dela.

---

Você pode estar passando pelo mesmo problema agora.

**→ [BOTÃO: Quero entender meu DRE — finalizar assinatura]**

Qualquer dúvida, responda aqui.

Karina

---

*P.S.: O plano começa em R$97/mês. Primeiro mês com garantia de 7 dias — se não ajudar, devolvemos o dinheiro, sem burocracia.*

---

### E-MAIL 3 — Enviado: 72h após abandono
**Assunto:** Última vez que entro em contato sobre isso

---

Oi, [nome].

Não quero ser insistente — esse é o último e-mail sobre sua assinatura.

Mas quero deixar algo claro antes de você decidir.

A maioria dos empresários que não contrata uma ferramenta de gestão financeira não é porque não quer — é porque acha que **vai resolver isso depois**, quando tiver mais tempo, mais dinheiro, menos problema para resolver.

O problema é que esse "depois" nunca chega.

E os meses passam, as margens encolhem, e a dúvida fica:
*"Para onde está indo o meu dinheiro?"*

O Máxima Finance IA não vai resolver seus problemas sozinho.

Mas vai te dar algo que você não tem hoje: **clareza**.

E com clareza, você toma decisões melhores.

---

Se quiser dar uma última chance antes de fechar:

**→ [BOTÃO: Experimentar por 7 dias sem risco]**

Se não fizer sentido para você, sem problema. Boa sorte com o negócio.

Karina Alnunes
Máxima Finance IA

---

*Você está recebendo esse e-mail porque iniciou um cadastro em maximafinance.com.br. Para cancelar esses lembretes: [Descadastrar]*

---

## CONFIGURAÇÃO TÉCNICA (para integração Stripe/Supabase)

```
Trigger: user inicia checkout → não finaliza em 60 minutos
Condição: payment_status = "pending" AND no "completed" event in 1h
Sequência:
  - E-mail 1: delay 1h
  - E-mail 2: delay 24h (só se não converteu)
  - E-mail 3: delay 72h (só se não converteu)
Parar sequência: payment_status = "completed"
```

**Métricas para acompanhar:**
- Open rate (referência: 40–50% em abandono de checkout)
- Click rate (referência: 8–12%)
- Recovery rate (referência: 10–15% dos que abriram)

---

*Produzido por Bella | Turno da Noite 17/07/2026*
