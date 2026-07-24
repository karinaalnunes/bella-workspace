# Máxima Finance IA — Sequência de E-mails de Nutrição Pré-Lançamento
*Tipo de ativo: 3 e-mails para quem entrou na lista de espera (pré-lançamento)*
*Gerado por Bella — Turno da noite 24/07/2026*

---

## OBJETIVO DESTA SEQUÊNCIA

Nutrir os leads captados pela landing page de pré-cadastro.
Objetivo: manter o interesse aquecido, construir autoridade e preparar para conversão no dia do lançamento.

**Frequência sugerida:** E-mail 1 logo após o cadastro → E-mail 2 no dia 3 → E-mail 3 no dia 7

---

## E-MAIL 1 — BOAS-VINDAS (envio imediato após cadastro)

**Assunto:** Você está na lista VIP — aqui está o que acontece agora
**Preview (pré-header):** Enquanto o acesso não abre, você já pode começar a se preparar.

---

**Corpo:**

Oi, [Nome]!

Que bom ter você na lista VIP da Máxima Finance IA.

Você foi um dos primeiros empresários a levantar a mão e dizer: **"quero entender minhas finanças de verdade."** Isso não é pouca coisa.

Enquanto finalizamos os últimos detalhes antes de abrir o acesso para você, quero te contar o que vai acontecer nas próximas semanas:

**→ Nos próximos dias:** você vai receber 2 e-mails com conteúdo gratuito que preparamos especialmente para quem está na lista — sobre DRE, análise de margem e as perguntas que todo empresário deveria saber responder antes de tomar qualquer decisão financeira.

**→ Quando abrirmos o acesso:** você vai ser o primeiro a saber. E vai ter um benefício exclusivo de quem estava na lista — te conto mais no último e-mail da sequência.

Uma coisa que eu quero que você faça agora:

Pega o DRE do último mês (pode ser o PDF do contador, uma planilha, qualquer formato) e salva num lugar de fácil acesso.

Quando a Máxima abrir, você vai querer subir esse documento em menos de 2 minutos — e eu quero que você tenha o "uau" ainda no primeiro acesso.

Até em breve,
**Karina — Máxima Finance IA**

*P.S.: Esse e-mail vai para a lista VIP exclusiva. Se quiser sair a qualquer momento, é só clicar em cancelar inscrição abaixo — sem ressentimentos.*

---

## E-MAIL 2 — CONTEÚDO / EDUCAÇÃO (envio no dia 3)

**Assunto:** A pergunta que nenhum empresário consegue responder (e deveria)
**Preview:** Não é sobre faturamento. Nem sobre lucro. É sobre algo mais simples — e mais importante.

---

**Corpo:**

[Nome], preciso te fazer uma pergunta.

**Se alguém te ligar agora e perguntar: "qual é a margem de contribuição da sua empresa?" — você saberia responder?**

Sem consultar planilha. Sem ligar pro contador. De cabeça.

A maioria dos empresários não sabe. Não porque não são competentes — mas porque nunca ninguém explicou de forma simples o que é esse número e por que ele importa.

Aqui vai a explicação de 2 minutos:

---

**Margem de contribuição é quanto cada real de venda "sobra" depois de pagar os custos variáveis.**

Fórmula:
> **Margem = (Receita — Custos Variáveis) ÷ Receita × 100**

Exemplo real:
- Você fatura R$80.000/mês
- Custos variáveis (mercadoria, comissão, frete): R$32.000
- Margem de contribuição: **60%**

O que isso significa? Que de cada R$100 que entra, R$60 ficam disponíveis para pagar seus custos fixos (aluguel, funcionários, energia) e gerar lucro.

**Por que isso importa tanto?**

Porque é a margem de contribuição que determina:
- Quantas vendas você precisa fazer para não ter prejuízo (ponto de equilíbrio)
- Se contratar mais funcionários vai aumentar ou engolir seu lucro
- Se aquele produto que "vende muito" está realmente te fazendo ganhar dinheiro

A Máxima Finance IA calcula isso automaticamente quando você sobe o seu DRE — e a Sofia explica o que o número significa para o **seu** negócio específico, não um exemplo genérico.

No próximo e-mail (daqui a 4 dias), vou te contar o que os primeiros usuários da Máxima descobriram quando analisaram o DRE pela primeira vez — e o que vamos oferecer exclusivamente para quem está nessa lista.

Até lá,
**Karina**

---

## E-MAIL 3 — OFERTA / ANTECIPAÇÃO DO LANÇAMENTO (envio no dia 7)

**Assunto:** Acesso antecipado + preço de fundador — abrindo em breve
**Preview:** Isso não vai para o público geral. Só para quem está nessa lista.

---

**Corpo:**

[Nome], chegou o momento que eu queria te contar desde o início.

Você entrou na lista VIP porque quer resolver um problema real: entender o que está acontecendo com as finanças da sua empresa, sem depender de planilha ou de esperar 60 dias pelo relatório do contador.

**Estamos abrindo o acesso da Máxima Finance IA nos próximos dias.**

E as pessoas dessa lista têm uma vantagem que o público geral não vai ter:

---

**O que você garante como membro da lista VIP:**

🔒 **Preço de fundador travado: R$67/mês** (o plano Pro regular é R$97/mês)
*Esse valor nunca sobe enquanto sua conta estiver ativa.*

🎁 **30 dias de acesso gratuito** (dobro do período padrão de teste)
*Você explora tudo, sem colocar cartão.*

📞 **Sessão de configuração 1:1** *(disponível para os primeiros 50 usuários)*
*Um membro da equipe te ajuda a configurar a primeira análise de DRE ao vivo.*

---

**Como vai funcionar:**

Quando abrirmos, você vai receber um e-mail com o link de acesso exclusivo da lista VIP. O link vai estar ativo por 48 horas — depois disso, o cadastro vai para a fila pública, sem os benefícios acima.

**Não precisa fazer nada agora.**

Fique de olho na caixa de entrada (e no spam, só por precaução).

Se tiver alguma dúvida antes do lançamento, responde esse e-mail — eu mesma leio.

Até breve,
**Karina — Máxima Finance IA**

*P.S.: Já separou seu DRE? Quando o acesso abrir, você vai querer subir na hora. 😉*

---

## INSTRUÇÕES DE IMPLEMENTAÇÃO

**Plataforma de e-mail sugerida:** Resend (já está no stack) + Supabase para controle de lista
**Trigger:** cadastro na tabela `leads_waitlist` → dispara Sequência Pré-lançamento
**Variável de personalização:** `{{nome}}` (campo "Seu nome" do formulário de lista)
**Rastreamento:** UTM nos links para medir qual e-mail converte mais no dia do lançamento

| E-mail | Dia | Objetivo |
|---|---|---|
| E-mail 1 | D+0 (imediato) | Boas-vindas + instrução de preparação |
| E-mail 2 | D+3 | Educação (margem de contribuição) + autoridade |
| E-mail 3 | D+7 | Antecipação do lançamento + oferta VIP |

**Nota:** E-mail 3 deve ser atualizado com a data real de abertura quando definida.

---

*Próximo ativo sugerido: script de DM para WhatsApp / Instagram para leads que não abriram os e-mails (re-engajamento manual nos primeiros 50 da lista)*
