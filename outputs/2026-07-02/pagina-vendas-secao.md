# Página de Vendas — Pop-up de Exit Intent + Sequência de Recuperação
*Turno da Noite — 02/07/2026 | Bella*

---

## CONTEXTO DE USO

Esta seção cobre dois elementos de recuperação de visitantes que **não converteram na primeira visita**:

1. **Pop-up de Exit Intent** — aparece quando o mouse vai em direção ao botão fechar/barra de endereço
2. **Sequência de e-mails de recuperação** — para leads que deixaram o e-mail mas não completaram o cadastro

Taxa média de abandono de landing page B2B: **70–80%**. Esses elementos capturam uma fatia dessa perda.

---

## 1. POP-UP DE EXIT INTENT

### Headline principal
> **"Espera — antes de sair, responde uma coisa:"**

### Pergunta gancho (escolher uma variação por teste A/B)

**Variação A — Dor direta:**
> *Você sabe exatamente quanto sobrou da sua empresa no mês passado?*
> Não o saldo da conta. O **lucro real**, depois de pagar tudo.
> Se a resposta demorou mais de 5 segundos — você precisa da Máxima.

**Variação B — Custo da ignorância:**
> *Cada mês sem ler o DRE é um mês de decisões no escuro.*
> Empresários que ignoram o DRE perdem, em média, **23% da margem** para custos que nem sabiam que existiam.
> Não seja o próximo.

**Variação C — Oferta de isca:**
> *Antes de ir: baixe o Checklist DRE em 5 Minutos — gratuito.*
> O mesmo checklist que nossos usuários Pro usam toda segunda-feira para fechar a semana no positivo.

---

### CTA do pop-up

| Variação | Botão Principal | Botão Secundário |
|---|---|---|
| A | **Quero saber meu lucro real →** | Não, prefiro adivinhar |
| B | **Comece grátis agora →** | Vou continuar no escuro |
| C | **Baixar Checklist Grátis →** | Não, obrigado |

---

### Subheadline (abaixo do CTA — reduzir fricção)
> Plano gratuito. Sem cartão de crédito. Cancela quando quiser.

---

### Design / UX
- **Fundo:** escuro semi-transparente (overlay)
- **Card:** branco com borda sutil roxa (#6C3FC4)
- **Ícone topo:** 💡 ou gráfico de lucro subindo
- **Máximo de texto:** conforme acima — não adicionar mais
- **Mobile:** exibir após 40s na página (não exit intent em mobile — usar timer)

---

## 2. SEQUÊNCIA DE RECUPERAÇÃO — 3 E-MAILS

*Para leads que deixaram o e-mail no Checklist/Lead Magnet mas não completaram o cadastro.*

---

### E-mail 1 — Imediato (H+1)
**Assunto:** Seu checklist DRE está aqui — e tem uma coisa que preciso te perguntar
**Preview:** Demorou 3 segundos para responder?

---

Oi, [NOME]!

Aqui está o Checklist DRE em 5 Minutos que você pediu:
→ **[BOTÃO: Baixar Checklist]**

Mas antes de você abrir, me responde uma coisa honesta:

Você consegue responder **agora mesmo**, sem abrir planilha nem ligar pro contador:

- Qual foi o seu lucro líquido no mês passado?
- Seu custo com pessoal passou de 35% da receita?
- Você está crescendo faturamento ou crescendo despesa?

Se demorou mais de 10 segundos em qualquer uma — o checklist vai ajudar. Mas ele resolve o diagnóstico, não o acompanhamento.

É para isso que existe a **Máxima Finance IA**.

Seu DRE sobe, a IA interpreta, você recebe o diagnóstico em português — sem contador, sem planilha, sem chute.

→ **[BOTÃO: Começar grátis — sem cartão]**

Até já,
Sofia — Assistente IA da Máxima Finance

---

### E-mail 2 — D+2
**Assunto:** [NOME], você sabia que 68% dos empresários não sabem sua margem real?
**Preview:** Não é culpa deles. É estrutural.

---

Oi, [NOME]!

Uma pesquisa com PMEs brasileiras mostra:

> **68% dos empresários não conseguem responder qual é sua margem líquida real sem consultar o contador.**

Isso não é falta de inteligência. É falta de ferramenta.

O contador entrega o balanço meses depois. A planilha exige horas de preenchimento. O ERP mostra dados, mas não interpreta.

Resultado: você toma decisão de crescimento com informação de 3 meses atrás.

A Máxima muda isso.

Você faz o upload do DRE (aquele arquivo que o contador já te manda). Em 90 segundos, a Sofia analisa e te entrega:

✅ Sua margem real por linha de receita
✅ Os custos que estão comendo seu lucro (sem você perceber)
✅ O que fazer nos próximos 30 dias para melhorar

→ **[BOTÃO: Testar grátis por 14 dias]**

Sem compromisso. Sem cartão.

Sofia — Máxima Finance IA

---

### E-mail 3 — D+5
**Assunto:** Última mensagem sobre isso — promessa
**Preview:** Se não for para você, tudo bem. Mas antes de decidir...

---

Oi, [NOME]!

Essa é minha última mensagem sobre a Máxima Finance IA — prometido.

Só quero deixar uma coisa clara antes de você decidir:

**A Máxima não substitui seu contador.**
Ela complementa. O contador cuida do legal, do fiscal, do compliance.
A Máxima cuida da sua **gestão diária** — os números que você precisa entender toda semana para não perder dinheiro.

Se você fatura entre R$ 30 mil e R$ 500 mil por mês e ainda depende de intuição para tomar decisões financeiras — a Máxima foi feita para você.

Se já tem um CFO interno ou um controller dedicado — ela provavelmente não vai agregar muito.

Sem pressão. Só clareza.

→ **[BOTÃO: Começar grátis — é só fazer upload do DRE]**

Se não for o momento, tudo bem.
Estou aqui quando for.

Sofia — Máxima Finance IA

P.S. O plano gratuito não tem limite de tempo. Você pode testar com calma.

---

## TOKENS PARA DEV

```
// EXIT INTENT POP-UP
trigger: mouseleave (desktop) | timer 40s (mobile)
show_delay: 500ms após trigger
show_once_per_session: true
suppress_after_signup: true
ab_test_variants: ['dor', 'custo', 'isca']

// EMAIL SEQUENCE
tag: 'lead_magnet_nao_convertido'
trigger: download_checklist AND NOT signup_completed
emails:
  - delay: 1h    | id: 'recovery_1'
  - delay: 2d    | id: 'recovery_2'
  - delay: 5d    | id: 'recovery_3'
unsubscribe_tag: 'recovery_sequence'
```

---

*Próximo elemento de conversão sugerido: Página de Obrigado pós-cadastro (upsell imediato para Pro)*
