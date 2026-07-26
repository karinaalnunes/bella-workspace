# Página de Vendas — Seção: Sequência de Ativação Pós-Compra
*Turno da noite — 26/07/2026*
*Foco: cadência WhatsApp + e-mail nas primeiras 48h após cadastro (redução de churn na ativação)*

---

## CONTEXTO ESTRATÉGICO

Esta seção não é uma página de vendas clássica — é o **funil de ativação pós-cadastro**.
A maior causa de cancelamento em SaaS não é o cliente que testa e sai. É o cliente que cadastra, nunca usa, e cancela porque "não viu valor".

A sequência abaixo resolve isso: garante que o cliente faça o primeiro upload do DRE nas primeiras 24h e sinta o valor real da ferramenta antes de qualquer cobrança.

**Gatilho:** Cadastro realizado (plano Gratuito, Pro ou Business).
**Objetivo:** Cliente faz o primeiro upload + recebe análise → momento "Uau" → ativação confirmada.
**Prazo:** 48 horas.

---

## CADÊNCIA COMPLETA — PRIMEIRAS 48H

### ⏰ H+0 — WhatsApp automático (imediato após cadastro)

> Olá, [nome]! Aqui é a Sofia, sua assistente financeira da Máxima Finance IA. 👋
>
> Seu acesso está ativo agora.
>
> Para você ver o poder da ferramenta de verdade, preciso de só uma coisa: o DRE da sua empresa — pode ser do mês passado, qualquer período.
>
> Ele pode estar no Excel, PDF ou até uma foto. Manda aqui ou direto na plataforma: [link]
>
> Leva menos de 2 minutos. A análise sai na hora. 🚀

---

### ⏰ H+0 — E-mail de boas-vindas (imediato)

**Assunto:** Sua conta está pronta — 1 passo para ver seu DRE de outro jeito

---

[Nome],

Você acabou de criar sua conta na Máxima Finance IA.

Agora tem acesso à ferramenta que transforma o DRE da sua empresa em diagnóstico real — sem precisar ser contador, sem planilha complicada.

**O que fazer agora (leva 2 minutos):**

1. Acesse sua conta → [botão: Entrar na plataforma]
2. Clique em "Nova Análise"
3. Faça upload do DRE (Excel, PDF ou imagem)
4. Receba o diagnóstico em segundos

Qualquer dúvida, a Sofia está disponível direto no chat da plataforma.

Até já,
**Equipe Máxima Finance IA**

---

### ⏰ H+4 — WhatsApp (se não fez upload)

> [Nome], ainda não vi seu DRE por aqui. 😊
>
> Sei que o dia fica corrido — mas 2 minutos agora podem te mostrar exatamente onde está indo o dinheiro da sua empresa.
>
> Se tiver dificuldade pra encontrar o arquivo, me fala. Consigo te ajudar a montar um DRE simples pelo próprio chat.
>
> [link da plataforma]

---

### ⏰ H+24 — E-mail (se não ativou)

**Assunto:** Uma pergunta rápida, [nome]

---

[Nome],

Ontem você criou sua conta na Máxima Finance IA — mas ainda não vi sua primeira análise.

Antes de eu presumir que você não quer continuar: tem algo que travou?

→ Não encontrou o DRE?
→ Ficou com dúvida de qual arquivo usar?
→ Não teve tempo?

Me responde com um desses números (1, 2 ou 3) e eu te ajudo agora.

**Máxima Finance IA**

*P.S. Se quiser, posso te mandar um modelo de DRE simplificado para você preencher e já testar a ferramenta.*

---

### ⏰ H+24 — WhatsApp (se não ativou)

> [Nome], deixa eu te contar o que acontece quando o empresário faz o primeiro upload na Máxima:
>
> A Sofia analisa o DRE e entrega em segundos:
> ✅ Qual é a sua margem real (não o que você acha que é)
> ✅ Quais despesas estão comendo mais o seu resultado
> ✅ Se seu negócio está em equilíbrio, lucro ou risco
>
> Isso costuma abrir os olhos de quem usa.
>
> Quando você quiser testar: [link]
>
> Estou aqui se precisar de ajuda. 💜

---

### ⏰ H+48 — E-mail (último da sequência de ativação)

**Assunto:** Última vez que vou falar sobre isso por enquanto

---

[Nome],

Nos últimos 2 dias mandei algumas mensagens porque queria garantir que você tivesse a chance de ver o que a Máxima Finance IA pode fazer pelo seu negócio.

Vou ser direta:

A maioria dos empresários que fazem o primeiro upload fica surpresa com o que encontra. Não porque está tudo ruim — mas porque **nunca tinham visto o DRE explicado de forma simples assim**.

Se você ainda não testou, a conta continua ativa. Quando quiser:
→ [Botão: Fazer minha primeira análise]

Se precisar de ajuda com qualquer parte do processo, é só responder este e-mail.

**Equipe Máxima Finance IA**

---

## NOTAS DE IMPLEMENTAÇÃO (para dev)

- **Trigger H+0:** webhook no evento `user.created` no Supabase → dispara WhatsApp (Evolution API) + e-mail (Resend/SendGrid)
- **Trigger H+4 / H+24 / H+48:** cron job que verifica se `user.first_analysis_at IS NULL` e dispara mensagem correspondente
- **Encerramento da cadência:** assim que `first_analysis_at` for preenchido, cancelar todas as mensagens pendentes desta sequência
- **Personalização:** `[nome]` e `[link]` devem ser variáveis dinâmicas injetadas no template

---

## POR QUE ESSA SEQUÊNCIA FUNCIONA

| Princípio | Aplicação |
|---|---|
| Velocidade | H+0 garante que o cliente está quente no momento do cadastro |
| Baixa fricção | O próximo passo sempre é só 1 ação (upload) |
| Empatia | Pergunta o motivo do travamento em vez de só insistir |
| Prova de valor | H+24 WhatsApp mostra o resultado antes de pedir o upload |
| Encerramento limpo | H+48 dá dignidade ao cliente que não ativou, sem spam |
