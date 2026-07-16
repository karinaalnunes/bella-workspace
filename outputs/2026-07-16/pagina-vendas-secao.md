# Página de Vendas — Pop-up de Intenção de Saída (Exit Intent)
*Gerado por Bella — Turno da noite — 16/07/2026*

---

## CONTEXTO E OBJETIVO

Quando o visitante tenta fechar a aba ou rolar para sair da página de vendas sem converter, este pop-up ativa. Objetivo: recuperar entre 5% e 15% dos visitantes que iriam embora.

---

## POP-UP PRINCIPAL — "Espera! Um presente antes de você ir"

### Gatilho
- Desktop: movimento do mouse em direção ao botão de fechar / barra de endereço
- Mobile: scroll rápido para cima (intenção de fechar)

---

### TÍTULO DO POP-UP

**"Espera — antes de você ir, deixa eu te mostrar uma coisa."**

---

### CORPO DO TEXTO

> Você acabou de visitar a Máxima Finance IA.
>
> Sei que é difícil tomar uma decisão agora.
>
> Por isso, quero te dar **acesso gratuito por 14 dias** — sem cartão, sem risco.
>
> Em 3 minutos você vai descobrir:
> - ✅ Qual produto da sua empresa realmente dá lucro
> - ✅ Onde o dinheiro está vazando no seu DRE
> - ✅ O que fazer agora para proteger sua margem
>
> **Só precisa do seu e-mail.**

---

### CTA (botão)

**[Quero meus 14 dias grátis →]**

Cor: verde escuro `#1A7F5A` | Texto branco | Bordas arredondadas 8px

*Ou então: "Não, prefiro continuar no escuro sobre meu DRE."*
*(link de recusa — tom de ironia leve, não agressivo)*

---

### ABAIXO DO CTA

> 🔒 Sem cartão de crédito. Sem cobrança automática. Cancele quando quiser.
> 🤝 Mais de 200 empresas já analisaram o DRE com a Máxima.

---

## VARIANTE A — Tom Urgência (para testar via A/B)

### Título
**"Essa oferta expira em 15 minutos."**

### Corpo
> Você quase foi embora.
>
> Antes que feche isso, vou ser direto:
>
> Todo mês que você passa sem entender seu DRE, **você perde dinheiro sem saber de onde.**
>
> Hoje você pode começar de graça.
> **Acesso por 14 dias — sem cartão de crédito.**

### CTA
**[Começar agora — 14 dias grátis]**

*Cronômetro regressivo: 14:59 → 00:00*

---

## VARIANTE B — Tom Curiosidade (recomendado para fundo de funil frio)

### Título
**"Uma pergunta rápida antes de você ir:"**

### Corpo
> *"Você sabe qual produto da sua empresa tem maior margem agora?"*
>
> Se a resposta foi "não tenho certeza" — você precisa da Máxima.
>
> Em menos de 3 minutos, nossa IA analisa seu DRE e responde exatamente isso.
>
> **Teste grátis por 14 dias. Sem cartão.**

### CTA
**[Descobrir agora gratuitamente →]**

---

## ESPECIFICAÇÕES TÉCNICAS

| Item | Especificação |
|---|---|
| Delay após trigger | 300ms |
| Overlay | Fundo escuro semi-transparente (rgba 0,0,0,0.6) |
| Animação | Slide-in de cima, 0.4s |
| Largura máxima | 540px |
| Botão fechar (X) | Canto superior direito, claro e acessível |
| Cookie de controle | 30 dias (não reexibir para quem fechou) |
| Cookie de conversão | Zerar ao converter |
| Evento para GA4 | `exit_intent_trigger`, `exit_intent_conversion` |

---

## QUANDO NÃO MOSTRAR

- Para usuários já logados
- Em páginas internas do app
- Para quem já converteu no mesmo dispositivo nos últimos 30 dias
- Menos de 10 segundos na página (ainda não leu nada)

---

## MÉTRICAS PARA ACOMPANHAR (semana 1)

| Métrica | Meta inicial |
|---|---|
| Taxa de exibição | > 40% dos visitantes que saem |
| Taxa de abertura do e-mail (versão A) | > 25% |
| Taxa de conversão do pop-up | > 5% |
| Taxa de ativação do trial | > 60% dos que deixaram e-mail |

---

## PRÓXIMOS PASSOS SUGERIDOS

1. Implementar no React com `mouseleave` no `document`
2. Integrar formulário ao Supabase (tabela `leads_exit_intent`)
3. Acionar sequência de e-mail de onboarding (já pronta: 09/07)
4. Rodar A/B por 14 dias → declarar vencedor por taxa de ativação de trial

---

*Observação para Karina:* Esta é uma das peças de recuperação mais eficientes de funil. Com 500 visitantes/mês e 5% de conversão no pop-up, são 25 novos trials por mês que seriam perdidos. Se 30% virarem pagantes → 7-8 clientes a mais por mês sem nenhum custo extra de tráfego.
