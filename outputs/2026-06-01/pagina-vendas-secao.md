# Página de Vendas — Sequência de Retargeting Pós-Webinar
## Meta Ads — D+1 a D+7 após o webinar (03/jun)
*Máxima Finance IA | Turno da noite 01/06/2026 — Bella*

---

## CONTEXTO DE USO

**Quando ativar:** Logo após o encerramento do webinar (03/jun, ~22h)
**Duração:** 7 dias — do D+1 (04/jun) ao D+7 (10/jun)
**Objetivo:** Converter os "quase-sim" — assistiram, se interessaram, mas não compraram na hora
**Segmentos-alvo:**
- Assistiram ao webinar e visitaram a página de vendas mas não compraram
- Visitaram a página de vendas nos últimos 30 dias (tráfego orgânico + pago anterior)
- Engajaram nos posts do Instagram sobre DRE nos últimos 60 dias

---

## ANÚNCIO 1 — OBJEÇÃO: "Preciso pensar melhor"
**Formato:** Vídeo 15s (corte do webinar) + legenda
**Objetivo:** Quebrar a indecisão com prova social imediata

**Headline:**
> "Você saiu do webinar pensando — mas não decidiu ainda."

**Texto do anúncio:**
> Eu entendo. É uma decisão. Mas enquanto você "pensa melhor", seu DRE deste mês continua sem diagnóstico.
>
> Quem usou a Máxima pela primeira vez descobriu em 8 minutos que estava operando com margem 3% abaixo do ponto de equilíbrio.
>
> Você prefere descobrir agora — ou em 60 dias, quando o caixa aperta?
>
> ✅ Teste grátis. Sem cartão. Sem compromisso.

**CTA:** Começar Agora Grátis
**Token dev:** `retargeting_webinar_attendee_objecao`

---

## ANÚNCIO 2 — URGÊNCIA: Oferta de abertura expira
**Formato:** Imagem estática com countdown
**Objetivo:** Criar urgência real sem parecer pressão falsa

**Headline:**
> ⏳ Oferta do webinar encerra em [X] horas

**Texto do anúncio:**
> Na live de [data], você viu como o DRE pode ser lido em português simples — sem precisar de contador.
>
> A oferta especial que apresentei ao vivo ainda está disponível — mas só até [data de encerramento, 48h após o webinar].
>
> Depois disso, volta ao preço cheio.
>
> O DRE de junho já começou. Você quer entrar no mês sabendo os números?

**CTA:** Garantir Meu Acesso
**Token dev:** `retargeting_webinar_urgencia_oferta`

---

## ANÚNCIO 3 — CURIOSIDADE: O número que ficou faltando
**Formato:** Carrossel 3 slides
**Objetivo:** Resgatar quem saiu antes do final com um gancho de conteúdo

**Slide 1:**
> "No webinar de ontem, mostrei o número que 73% das PMEs brasileiras não calculam."

**Slide 2:**
> Não é o faturamento.
> Não é o lucro líquido.
> É a **margem de contribuição por produto** — o número que revela qual produto está bancando a empresa e qual está drenando.
> O DRE mostra. Ninguém explica.

**Slide 3:**
> Essa é a análise que a Sofia faz para você em 8 minutos.
> → Upload do DRE → Diagnóstico em português → Decisão sem depender de ninguém
>
> **[Quero ver o diagnóstico da minha empresa →]**

**CTA:** Ver Como Funciona
**Token dev:** `retargeting_webinar_curiosidade_carrossel`

---

## ANÚNCIO 4 — PROVA SOCIAL: Depoimento pós-webinar
**Formato:** Print de depoimento (template) + fundo sólido
**Objetivo:** Mostrar resultado real de alguém parecido com o lead

**Template de depoimento (preencher com depoimento real coletado após o webinar):**
> *"Entrei no webinar sem entender nada de DRE. Saí sabendo que minha empresa estava operando no negativo por causa de [problema específico]. Assino o Pro há [X] dias e já tomei [Y] decisão com base no diagnóstico."*
> — [Nome], [segmento], [cidade]

**Texto do anúncio:**
> Isso foi o que aconteceu com [Nome] depois do webinar de [data].
>
> Você também pode ter esse diagnóstico ainda esta semana.
>
> 👇 Comece grátis. Veja o que o DRE da sua empresa está escondendo.

**CTA:** Quero Meu Diagnóstico
**Token dev:** `retargeting_webinar_prova_social`

---

## ANÚNCIO 5 — REENGAJAMENTO D+5: Para quem visitou mas não converteu
**Formato:** Vídeo curto (30s) — Karina falando direto para a câmera
**Objetivo:** Toque pessoal para quem está quase decidindo

**Roteiro do vídeo (30s):**
> [0–5s] "Você esteve no webinar há 5 dias. Ou viu a página, mas ainda não entrou."
>
> [5–15s] "Eu entendo que tem dúvida. Mas te pergunto uma coisa: hoje você sabe, com precisão, qual é a margem do seu negócio este mês?"
>
> [15–25s] "Se a resposta for 'mais ou menos' — é exatamente pra isso que a Máxima existe. Upload do DRE. 8 minutos. Diagnóstico em português."
>
> [25–30s] "Começa grátis. Sem cartão. Clica abaixo."

**CTA:** Começar Agora — É Grátis
**Token dev:** `retargeting_d5_reengajamento_video`

---

## SEGMENTAÇÃO RECOMENDADA (Meta Ads)

### Público 1 — Quentes (D+1 a D+3)
- Custom Audience: Visitaram `/vendas` ou `/checkout` nos últimos 7 dias
- Custom Audience: Engajaram no webinar (lista de inscritos) → importar via CSV para Custom Audience
- Budget sugerido: R$ 80/dia

### Público 2 — Mornos (D+3 a D+7)
- Custom Audience: Visitaram qualquer página do site nos últimos 30 dias
- Custom Audience: Assistiram 50%+ do vídeo do VSL nos últimos 14 dias
- Budget sugerido: R$ 50/dia

### Exclusão obrigatória
- Custom Audience: Já converteram (compraram Pro ou Business) → excluir de todos os conjuntos

---

## CRONOGRAMA DE ATIVAÇÃO

| Dia | Anúncios ativos | Budget |
|-----|----------------|--------|
| D+1 (04/jun) | Anúncio 1 + 2 (urgência) | R$ 80/dia |
| D+2 (05/jun) | Anúncio 2 + 3 (urgência + curiosidade) | R$ 80/dia |
| D+3 (06/jun) | Anúncio 3 + 4 (curiosidade + prova social) | R$ 60/dia |
| D+4 (07/jun) | Anúncio 4 (prova social) | R$ 50/dia |
| D+5 (08/jun) | Anúncio 5 (reengajamento vídeo) | R$ 50/dia |
| D+6 (09/jun) | Anúncio 5 (reengajamento vídeo) | R$ 50/dia |
| D+7 (10/jun) | Anúncio 1 + 5 (objeção + reengajamento) | R$ 50/dia |

**Budget total estimado: R$ 420 para 7 dias**

---

## NOTA DE IMPLEMENTAÇÃO

1. Configurar pixel Meta no `/vendas`, `/checkout`, `/obrigado` para alimentar os Custom Audiences
2. Exportar lista de inscritos do webinar (Zoom/Hopin) para CSV → importar no Meta como Custom Audience
3. Ativar os anúncios logo após o encerramento da oferta de 48h (D+2 à noite) para capturar os "indecisos tardios"
4. Acompanhar CTR e CPL diariamente — se CTR < 1,5%, testar novo criativo no D+3

---

*Arquivo: `outputs/2026-06-01/pagina-vendas-secao.md`*
*Próximo: Implementar pixel Meta + criar Custom Audiences antes do webinar (03/jun)*
