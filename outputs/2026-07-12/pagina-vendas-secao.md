# Página de Vendas — Seção: Página de Obrigado (Thank You Page)
*Turno da noite — 12/07/2026*

---

## CONTEXTO DE USO

Esta é a página que o usuário vê imediatamente após se cadastrar no plano Gratuito.
É o momento de maior engajamento emocional — o usuário acabou de tomar uma decisão.
Objetivo duplo: (1) confirmar que fez certo, (2) guiar o próximo passo.

---

## HEADLINE PRINCIPAL

**"Sua conta está pronta. Agora você vai enxergar sua empresa de um jeito diferente."**

---

## SUBTÍTULO

Você levou menos de 2 minutos para dar o primeiro passo que a maioria dos empresários nunca dá: parar de adivinhar e começar a ler os números de verdade.

---

## BLOCO: CONFIRMAÇÃO + REFORÇO DE DECISÃO

> ✅ **Conta criada com sucesso**
> 
> Bem-vindo à Máxima Finance IA.
> Você está no plano **Gratuito** — e já pode começar agora.

---

## SEÇÃO: O QUE FAZER AGORA (3 passos, sem enrolação)

### Passo 1 — Faça o upload do seu DRE
> Aceita Excel, PDF ou preenchimento manual.
> Se não tiver o DRE, não tem problema: a Sofia te ajuda a montar um do zero.

**[→ Fazer upload agora]** *(botão CTA principal)*

---

### Passo 2 — Leia o diagnóstico em português
> Em menos de 60 segundos, a IA lê seu DRE e entrega um resumo claro:
> onde está sua margem, onde está o risco e o que fazer primeiro.

---

### Passo 3 — Converse com a Sofia
> Tem dúvida sobre um número? Pergunte.
> A Sofia responde em linguagem de gente, não de contador.

---

## BLOCO: EXPECTATIVA (o que acontece nos próximos dias)

**Nos próximos minutos:**
Você vai receber um e-mail de boas-vindas com um guia rápido sobre como tirar o máximo do plano Gratuito.

**Nos próximos 7 dias:**
A Bella (nossa assistente autônoma) vai acompanhar seu uso e te enviar dicas personalizadas com base no DRE que você enviou.

---

## BLOCO: UPGRADE (sem pressão — só plantando a semente)

### Quer ir mais fundo?

No **plano Pro (R$97/mês)** você desbloqueia:

- ✅ Análises mensais ilimitadas
- ✅ Comparativo mês a mês (tendência da sua empresa)
- ✅ Alertas automáticos quando um indicador sai do normal
- ✅ Relatórios para apresentar ao sócio ou investidor

**[→ Conhecer o Pro]** *(link secundário, sem peso)*

---

## BLOCO: PROVA SOCIAL (minimalista, pós-cadastro)

> *"Fiz o upload na segunda-feira. Na terça já tinha clareza sobre onde estava perdendo dinheiro. Isso vale mais que qualquer consultoria."*
> **— Rodrigo M., dono de distribuidora em Ribeirão Preto**

---

## RODAPÉ DA PÁGINA

Dúvidas? Fale com a Sofia pelo chat → ou escreva para suporte@maximafinance.com.br

*Feito para empresários que faturam entre R$30k e R$500k/mês e querem crescer com segurança.*

---

## NOTAS DE IMPLEMENTAÇÃO (para o dev)

- CTA principal: fundo roxo (#6B21A8), texto branco, sem sombra
- CTA secundário (Pro): link simples em roxo claro, sem botão
- Passo-a-passo: usar ícones numerados simples (1, 2, 3), fonte bold
- Quote de depoimento: fundo cinza muito claro (#F9FAFB), borda esquerda roxa
- Não exibir nav/menu completo — manter usuário focado nos próximos passos
- Tracking: evento `signup_thank_you_page_view` + `cta_upload_click` + `upgrade_link_click`
