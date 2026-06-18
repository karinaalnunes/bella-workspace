# Máxima Finance IA — Script de Welcome Video (Onboarding em Vídeo)
*Turno da noite — 18/06/2026*

---

## CONTEXTO DE USO

**Tipo:** Vídeo de boas-vindas para novos usuários (gratuitos e pagos)
**Duração:** 2 min (roteiro completo) + versão 45 seg (modal de boas-vindas no app)
**Onde aparece:**
- Modal na primeira abertura do dashboard (`<WelcomeModal>`)
- E-mail de boas-vindas (Resend/Loops) — vídeo incorporado
- Página de Thank You após cadastro

**Tom:** Leve, humano, direto. A Sofia (IA) fala como parceira, não como robô.

---

## ROTEIRO COMPLETO — 2 MINUTOS

### ABERTURA (0:00 – 0:15)
*[Tela: Logo Máxima Finance + animação do DRE sendo processado]*

> "Seja bem-vindo à Máxima Finance IA. Sou a Sofia, sua analista financeira.
> Em 2 minutos, você vai entender como usar a plataforma para nunca mais olhar para o DRE e não saber o que fazer."

---

### PROBLEMA QUE A GENTE RESOLVE (0:15 – 0:35)
*[Tela: planilha confusa → transformação em diagnóstico limpo]*

> "A maioria dos empresários recebe o DRE do contador uma vez por mês e não sabe o que os números significam na prática.
> O que deve subir? O que está cortando seu lucro? Qual produto está te dando prejuízo?
> Essas respostas estão no DRE. Só que até agora, ninguém te ajudava a ler."

---

### COMO FUNCIONA — PASSO A PASSO (0:35 – 1:10)
*[Screencast rápido do app: upload → análise → chat → relatório]*

> "Com a Máxima, é simples:
>
> **Passo 1:** Você faz o upload do seu DRE — pode ser PDF, Excel ou foto.
>
> **Passo 2:** Em segundos, eu processo todos os números e identifico os pontos críticos do seu resultado.
>
> **Passo 3:** Você recebe um diagnóstico em linguagem normal — sem jargão contábil.
>
> **Passo 4:** Me pergunte qualquer coisa no chat. 'Sofia, por que meu lucro caiu?' 'Qual o meu ponto de equilíbrio?' 'Estou no caminho certo?'
>
> Eu respondo com base nos seus números reais."

---

### O QUE VOCÊ VAI DESCOBRIR (1:10 – 1:35)
*[Tela: 4 cards dos indicadores — Margem, CMV, Custos Fixos, Resultado]*

> "No seu dashboard, você vai acompanhar:
>
> → **Sua margem bruta real** — o quanto sobra depois de pagar o que você vende
> → **Seus custos fixos como % do faturamento** — o quanto vai embora antes de você ganhar qualquer coisa
> → **O resultado do mês** — lucro ou prejuízo, com explicação do que causou
> → **Alertas automáticos** — quando alguma linha do DRE sai do padrão saudável
>
> Tudo em um lugar só. Sem planilha. Sem precisar entender contabilidade."

---

### PRÓXIMO PASSO (1:35 – 2:00)
*[Tela: botão "Fazer upload do meu primeiro DRE"]*

> "Agora é com você.
>
> Faça o upload do DRE do mês mais recente — pode ser de hoje, do mês passado, não importa.
>
> Nos próximos 60 segundos, você vai ter o diagnóstico financeiro mais claro que já viu sobre a sua empresa.
>
> Vamos começar?"

---

## VERSÃO 45 SEGUNDOS — MODAL DE BOAS-VINDAS

*[Aparece na primeira abertura do dashboard — autoplay, com mute por padrão]*

> "Oi! Sou a Sofia, sua analista IA da Máxima Finance.
>
> Você está aqui porque quer entender de verdade o que o DRE da sua empresa está dizendo.
>
> O jeito mais rápido de começar: faça o upload do seu DRE agora. Em 60 segundos, você tem um diagnóstico completo em linguagem simples.
>
> Qualquer dúvida, é só me perguntar no chat. Estou aqui."

*[CTA: botão "Fazer upload agora" + link "Ver o tour completo"]*

---

## TOKENS DE IMPLEMENTAÇÃO (para o dev)

```jsx
// Componente: WelcomeModal.tsx
// Trigger: useEffect no DashboardPage — verificar flag user.hasSeenWelcome no Supabase

const WelcomeModal = ({ user, onClose }) => (
  <Modal isOpen={!user.hasSeenWelcome} onClose={handleClose}>
    <VideoPlayer
      src="/videos/sofia-welcome-45s.mp4"
      autoPlay
      muted
      poster="/images/sofia-welcome-thumb.jpg"
    />
    <h2>Bem-vindo, {user.firstName}!</h2>
    <p>Seu diagnóstico financeiro começa com o upload do DRE.</p>
    <Button variant="primary" onClick={() => router.push('/upload')}>
      Fazer upload agora
    </Button>
    <TextLink onClick={() => router.push('/tour')}>
      Ver tour completo (2 min)
    </TextLink>
  </Modal>
)

// Flag de controle no Supabase:
// UPDATE users SET has_seen_welcome = true WHERE id = auth.uid()
// Chamar após o usuário fechar o modal ou clicar em qualquer CTA
```

---

## E-MAIL DE BOAS-VINDAS — VERSÃO COM VÍDEO INCORPORADO

**Assunto:** Sua analista financeira está esperando você 👇
**Preview text:** Primeiro passo: faça o upload do DRE. Em 60 segundos, você tem o diagnóstico.

---

Oi, {primeiro_nome}!

Sou a **Sofia**, analista de IA da Máxima Finance. Você acabou de criar sua conta — e estou aqui para te ajudar a entender o que os números da sua empresa estão dizendo.

**Seu primeiro passo:**

[🎬 ASSISTIR: Como usar a Máxima em 2 minutos → thumbnail do vídeo]

Mas se preferir ir direto ao ponto:

→ **[Fazer upload do meu primeiro DRE →]**

Em 60 segundos, você tem:
- Diagnóstico da margem bruta
- Identificação dos custos que estão pesando mais
- Resultado do mês com explicação em linguagem simples
- Alertas de pontos de atenção

Qualquer dúvida — financeira ou sobre a plataforma — é só responder esse e-mail ou me perguntar no chat do app.

Estou aqui para você,

**Sofia**
Analista IA · Máxima Finance

---

*P.S.: Já tem o DRE de junho em mãos? Perfeito timing — o fechamento de semestre é o melhor momento para fazer o diagnóstico e planejar o 2º semestre.*

---

## NOTAS DE PRODUÇÃO

- **Voz da Sofia:** feminina, ritmo moderado, paulistana neutra. Evitar sotaque regional ou tom muito "corporativo".
- **Background do vídeo:** tela do app em movimento (screencast) com overlay sutil. Evitar fundo branco estático.
- **Legenda:** obrigatória (usuário assiste sem som no modal). Usar closed caption automático + revisão manual.
- **Versão mobile:** gravar 9:16 da versão 45s para Stories/Reels de onboarding.
- **Ferramenta sugerida:** Loom (protótipo) → Descript (edição + legendas) → exportar MP4 720p
