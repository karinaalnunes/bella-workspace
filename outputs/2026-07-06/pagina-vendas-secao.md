# Página de Vendas — Seção: Sequência de E-mails de Reativação (Usuários Inativos)
*Produzido por Bella — Turno da Noite — 06/07/2026*

---

## CONTEXTO DE USO

**Gatilho:** Usuário cadastrado há 30+ dias sem fazer login (plano Gratuito ou Pro).
**Objetivo:** Reativar o usuário, mostrar valor tangível, converter Gratuito→Pro ou reverter churn iminente de Pro.
**Sequência:** 3 e-mails em 7 dias.

---

## E-MAIL 1 — DIA 0 (disparo automático após 30 dias de inatividade)

**Assunto A/B:**
- A: "Karina, sua empresa mudou em 30 dias — o DRE sabe disso?"
- B: "Uma coisa que você não viu no mês passado (mas o DRE registrou tudo)"

**Preview:** O número que mais importa está esperando por você.

---

**CORPO:**

Oi, [primeiro_nome]!

Faz um tempo que você não abre o Máxima Finance.

Sem julgamento — a rotina de quem gere uma empresa é implacável.

Mas o DRE do seu negócio continuou rodando enquanto você estava ocupado.

Receitas entraram. Custos saíram. A margem do mês ficou registrada.

E o maior erro que os empresários cometem nessa hora é não olhar para esse número quando ele ainda pode ser corrigido.

**O que você vai encontrar quando entrar agora:**

- ✅ O diagnóstico do último período que você carregou
- ✅ Resposta para: "meu negócio está saudável ou está se deteriorando?"
- ✅ 1 ação prática que a Sofia (nossa IA) sugere para este momento

👉 **[Abrir meu painel agora →]**

*(Leva menos de 3 minutos. Prometemos.)*

Até mais,
**Sofia — IA do Máxima Finance**

P.S. Se tiver dúvida sobre qualquer número do seu DRE, é só me perguntar no chat. Estou aqui.

---

## E-MAIL 2 — DIA 3

**Assunto A/B:**
- A: "O empresário que ignorou o DRE em julho pagou caro em outubro"
- B: "Tem uma pergunta que 83% dos empresários nunca conseguem responder"

**Preview:** A resposta está no seu painel — a gente já calculou.

---

**CORPO:**

Oi, [primeiro_nome]!

Tem uma pergunta que fazemos para todos os empresários que chegam ao Máxima Finance:

> *"Você sabe qual é a sua margem líquida real hoje?"*

83% respondem com silêncio.

Não porque sejam desatentos. Porque ninguém nunca mostrou de forma simples.

Planilha? Você abre, fecha, esquece.
Contador? Manda o relatório cheio de siglas no fim do mês.
ERP? 14 relatórios, 3 horas, e ainda não sabe a resposta.

**O Máxima Finance foi feito para essa pergunta específica.**

Você carrega o DRE → a Sofia interpreta → você recebe a resposta em português direto:

*"Sua margem líquida em [mês] foi de X%. Para o seu setor, o saudável é entre Y% e Z%. Você está [abaixo/dentro/acima]. Aqui está o que está puxando para baixo:"*

Simples assim.

👉 **[Quero ver minha margem agora →]**

Se você estiver no plano Gratuito e quiser desbloquear análise comparativa mês a mês, o Pro custa R$97/mês — menos do que uma hora de consultoria financeira.

**[Quero upgrade para o Pro →]**

Qualquer dúvida, pode responder esse e-mail ou me chamar no chat.

Sofia 💜

---

## E-MAIL 3 — DIA 7 (último da sequência)

**Assunto A/B:**
- A: "Vou ser direta: você quer mesmo entender as finanças da sua empresa?"
- B: "Último aviso sobre sua conta Máxima Finance (e uma oferta honesta)"

**Preview:** Se a resposta for sim, a gente está aqui. Se não, tudo bem também.

---

**CORPO:**

Oi, [primeiro_nome],

Esse é o último e-mail desta sequência — prometo.

Se você não abriu os dois anteriores, ou abriu e não voltou para o painel, é provável que um desses cenários seja verdadeiro:

1. A rotina não deu espaço (totalmente compreensível)
2. Você não viu valor suficiente ainda (isso eu posso resolver)
3. Você está bem sem isso (honestidade total: tudo bem)

Se for o cenário 2, deixa eu ser direta:

**O Máxima Finance não é mais um relatório financeiro.**

É uma conversa com uma IA que entende o DRE da sua empresa e responde perguntas como:

— "O que está comendo minha margem?"
— "Posso contratar mais uma pessoa esse mês?"
— "Por que faturei mais mas sobrou menos?"
— "Meu negócio está indo bem ou estou me enganando?"

Essas perguntas têm resposta. E a resposta está no seu DRE.

**Se você quiser dar uma última chance:**

👉 [Abrir o painel — último acesso gratuito estendido por 7 dias →]

*(Para usuários Gratuito: acesso a 1 análise Pro desbloqueada por 7 dias, sem precisar de cartão.)*

Se você não voltar, nenhum problema. Fico aqui quando precisar.

Sofia 💜

P.S. Se o plano Gratuito não está atendendo o que você precisa, o Pro por R$97/mês inclui histórico comparativo, alertas automáticos e chat ilimitado com a Sofia. [Ver planos →]

---

## TOKENS TÉCNICOS (Supabase / Automação)

```javascript
// Trigger: usuário sem login há 30 dias
const INACTIVITY_THRESHOLD_DAYS = 30;

// Segmentação por plano
const segments = {
  gratuito: {
    email1_subject_a: "{{first_name}}, sua empresa mudou em 30 dias — o DRE sabe disso?",
    cta_upgrade: true,
    trial_extension: "7 dias desbloqueados no E-mail 3"
  },
  pro: {
    email1_subject_a: "{{first_name}}, sua análise de {{last_month}} está esperando",
    cta_upgrade: false,
    churn_risk_tag: "reativacao_30d"
  }
};

// Sequência: 0 / +3 dias / +7 dias
const sequence = [
  { delay_days: 0, template: "reactivation_email_1" },
  { delay_days: 3, template: "reactivation_email_2" },
  { delay_days: 7, template: "reactivation_email_3" }
];

// Parar sequência se usuário fizer login
// Event: user.login → cancel_sequence("reactivation_30d")
```

---

## MÉTRICAS A MONITORAR

| Métrica | Meta |
|---|---|
| Taxa de abertura E-mail 1 | > 35% |
| Taxa de clique E-mail 1 | > 8% |
| Taxa de reativação (login em 7 dias) | > 15% |
| Conversão Gratuito→Pro nessa sequência | > 3% |
| Cancelamentos evitados (Pro) | > 20% dos inativos |

---

*Próxima seção sugerida: E-mails de Downsell (Pro→Gratuito — usuário que cancela Pro) / Sequência de Retenção pré-churn (usuário que visualizou página de cancelamento)*
