# Página de Confirmação do Webinar + Sequência de Lembretes
*Turno da Noite — 23/05/2026 | Bella*

---

## CONTEXTO

**Para usar em:** Página de confirmação imediata após inscrição no webinar de lançamento (03 ou 04/jun) + 3 lembretes automatizados (D-2 / D-1 / Dia D).

**Evento:** "Como ler o DRE da sua empresa em 15 minutos e finalmente entender para onde vai o seu dinheiro" — Webinar ao vivo com Karina Alnunes.

**Público:** Empresário/a PME inscrito na lista VIP ou em campanha de captação.

**Integração:** Resend (e-mails) + Calendly ou Zoom (link do evento) + tokens para Supabase.

---

## 1. PÁGINA DE CONFIRMAÇÃO (Thank You Page — Webinar)

**URL:** `/webinar/confirmado`

**Token dev:**
```
status_webinar: "confirmed"
webinar_date: "2026-06-03"
webinar_time: "20h00 BRT"
webinar_link: {{ webinar_url }}
user_name: {{ first_name }}
```

---

### Headline principal

**Você está dentro! 🎉**

Sua vaga no webinar gratuito está confirmada.

---

### Subheadline

**"Como ler o DRE da sua empresa em 15 minutos e finalmente entender para onde vai o seu dinheiro"**

📅 **Terça-feira, 03 de junho de 2026**
🕗 **20h00 (horário de Brasília)**
💻 **Ao vivo pelo Zoom — link no e-mail de confirmação**

---

### Corpo da página

**O que vai acontecer no webinar:**

✅ Você vai aprender a ler o DRE sem precisar de contador
✅ Vai descobrir os 3 números que mais afetam o lucro da sua empresa
✅ Vai entender por que o caixa some mesmo quando o faturamento é alto
✅ Vai ver a Máxima Finance IA ao vivo — e como ela analisa um DRE em segundos

**E no final:** quem assistir ao vivo vai ter acesso antecipado ao plano Pro por um preço que não vai aparecer mais.

---

### CTA — Adicionar ao calendário

```
[+ Adicionar ao Google Agenda]    [+ Adicionar ao Outlook]
```

*Também enviamos o link por e-mail. Verifique a caixa de entrada (e o spam, só por garantia).*

---

### Bloco de reforço de valor

**Por que vale reservar a terça-feira às 20h:**

> "Empresários que acompanham o DRE todo mês tomam decisões melhores. Não porque são mais inteligentes — mas porque têm os dados certos na frente."
>
> — Karina Alnunes, fundadora da Máxima Finance IA

---

### Urgência viral (compartilhamento)

**Conhece outro empresário que também vive com essa dúvida?**

Manda o link pra ele. O webinar é gratuito e as vagas são limitadas.

```
[Compartilhar no WhatsApp]    [Compartilhar no Instagram]
```

*Link direto: maximafinance.com.br/webinar*

---

## 2. E-MAIL D-2 (enviado na noite de domingo, 01/jun)

**Assunto:** Lembrete: seu webinar é em 2 dias, {{ first_name }}

**Preview:** Você está inscrito. Só não esqueça de aparecer 👇

---

**Corpo:**

Oi, {{ first_name }}!

Só passando para lembrar: o webinar **"Como ler o DRE em 15 minutos"** acontece **terça-feira (03/jun) às 20h**.

Eu sei que a rotina de dono de empresa é cheia. Por isso estou te mandando esse lembrete agora — para você bloquear a agenda antes que apareça outra coisa.

**📅 Terça-feira, 03 de junho — 20h00 BRT**
**🔗 Link: {{ webinar_url }}**

---

**O que vamos ver ao vivo:**

→ Por que a maioria dos empresários olha para o número errado no DRE
→ Os 3 indicadores que separam uma empresa lucrativa de uma que está quebrando devagar
→ Uma demonstração ao vivo da Máxima Finance IA analisando um DRE real

E no final: quem assistir ao vivo recebe uma oferta que não vai aparecer em outro lugar.

---

Adicione o evento na agenda agora para não esquecer:

```
[+ Google Agenda]    [+ Outlook]
```

Te vejo terça!

**Karina Alnunes**
Fundadora, Máxima Finance IA

---

**Token dev:**
```
trigger: D-2 antes de webinar_date
segmento: webinar_inscrito
```

---

## 3. E-MAIL D-1 (enviado na segunda-feira, 02/jun — manhã)

**Assunto:** Amanhã às 20h — você vai estar lá?

**Preview:** Uma coisa que você vai descobrir amanhã que vai mudar como você vê o DRE

---

**Corpo:**

{{ first_name }}, amanhã é o dia.

**Webinar ao vivo: terça-feira, 03/jun — 20h00 BRT**
🔗 {{ webinar_url }}

---

Deixa eu te contar uma coisa.

Quando eu pergunto para um empresário: *"Você sabe qual é a sua margem líquida?"*, a resposta mais comum é um silêncio constrangedor.

Não é falta de inteligência. É falta de ferramenta certa.

O DRE existe para responder essa pergunta. Mas ele foi criado para contadores — não para donos de empresa.

**Amanhã, vou te mostrar como ler esse relatório em 15 minutos, do jeito que o empresário entende.**

---

**Agenda do webinar:**

🕗 20h00 — Abertura + apresentação
🕗 20h10 — Por que o seu DRE está te enganando (sem querer)
🕗 20h25 — Os 3 números que mais importam
🕗 20h40 — Demo ao vivo: Máxima Finance IA analisando um DRE
🕗 20h55 — Perguntas ao vivo
🕗 21h05 — Oferta exclusiva para quem assistiu até o final

---

Nos vemos amanhã!

**Karina Alnunes**
Fundadora, Máxima Finance IA

---

**P.S.:** O link funciona no celular também. Se você vai estar em deslocamento às 20h, dá para assistir do carro ou do metrô (com fone 🎧).

---

**Token dev:**
```
trigger: D-1 antes de webinar_date (manhã — 09h00 BRT)
segmento: webinar_inscrito
```

---

## 4. E-MAIL DIA D — "Hoje às 20h" (enviado na terça, 03/jun — 17h BRT)

**Assunto:** Hoje às 20h — o link está aqui

**Preview:** Você tem 3 horas. O link do Zoom está abaixo 👇

---

**Corpo:**

{{ first_name }},

**Hoje às 20h.** Esse é o momento.

🔗 **Link do Zoom:** {{ webinar_url }}

---

Salva esse e-mail. O link é esse. Clica 5 minutos antes para entrar sem pressa.

---

**O que acontece hoje:**

Você vai ver, ao vivo, como a Máxima Finance IA analisa um DRE de uma PME real — e o que ela entrega em segundos que levaria horas para um contador produzir.

E vou te mostrar os 3 números que toda empresa com mais de R$ 30 mil de faturamento precisa acompanhar todo mês.

---

**Quem ficar até o final vai receber:**

Uma oferta exclusiva — válida apenas durante o webinar — para acessar o plano Pro da Máxima Finance IA com condições que não estarão disponíveis depois.

---

**A partir das 19h55, o link já estará aberto.** Te vejo lá!

**Karina Alnunes**
Fundadora, Máxima Finance IA

---

**Token dev:**
```
trigger: webinar_date às 17h00 BRT
segmento: webinar_inscrito
subject_line_ab_test: true
variant_a: "Hoje às 20h — o link está aqui"
variant_b: "{{ first_name }}, em 3 horas começa 👇"
```

---

## 5. MENSAGEM DE LEMBRETE — WHATSAPP (Dia D — 19h30 BRT)

**Para:** Lista VIP / inscritos que optaram por WhatsApp

```
Oi, {{ first_name }}! 👋

Daqui a 30 minutos começa o webinar.

🔗 Link: {{ webinar_url }}

Hoje às 20h — ao vivo.

"Como ler o DRE em 15 minutos e entender para onde vai o dinheiro da sua empresa."

Quem ficar até o final recebe uma condição especial no plano Pro. 🎁

Te vejo já!
— Karina, Máxima Finance IA
```

**Token dev:**
```
trigger: webinar_date às 19h30 BRT
canal: whatsapp
opt_in_required: true
campo: user_phone
```

---

## MÉTRICAS PARA ACOMPANHAR

| Métrica | Benchmark |
|---|---|
| Taxa de abertura D-2 | > 45% |
| Taxa de abertura D-1 | > 50% |
| Taxa de abertura Dia D | > 60% |
| Show rate (inscritos → assistentes) | > 35% |
| Taxa de conversão (assistentes → Pro) | > 10% |

---

## PRÓXIMOS PASSOS PARA DEV

1. Configurar página `/webinar/confirmado` com os tokens acima (Supabase: `webinar_registrations`)
2. Criar automação no Resend: trigger `webinar_confirmed` → sequência D-2 / D-1 / Dia D 17h
3. Adicionar campo `phone` no formulário de inscrição (opcional) + opt-in WhatsApp
4. Configurar A/B test no e-mail Dia D (assunto)
5. Integrar botões "Adicionar ao Google Agenda" com link `.ics` gerado dinamicamente

---

*Produzido por Bella — Turno da Noite 23/05/2026*
