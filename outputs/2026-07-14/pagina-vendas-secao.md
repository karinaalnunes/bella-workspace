# Página de Vendas — Seção: Order Bump / Oferta no Checkout
*Produzido por Bella — Turno da noite — 14/07/2026*

---

## CONTEXTO DE USO

Esta seção é exibida **dentro do checkout**, logo antes do botão de confirmação do pagamento.
Funciona como um "sim adicional" de baixa fricção — o usuário já está com o cartão na mão.

**Posição:** Bloco visual entre o resumo do plano e o botão "Finalizar assinatura"
**Gatilho:** Aparece apenas para quem escolhe o plano **Pro (R$97/mês)**
**Objetivo:** Upgrade para Business ou venda de sessão de onboarding avulsa

---

## OPÇÃO A — Order Bump: Sessão de Onboarding 1:1 (R$97 avulso)

```
┌─────────────────────────────────────────────────────┐
│  ☑ SIM! Quero começar com o pé direito             │
│                                                     │
│  Adicionar: Sessão de Onboarding 1:1 com Especialista │
│  ── 45 minutos ao vivo ──                           │
│                                                     │
│  ✅ Faço o upload do seu DRE com você               │
│  ✅ Explico o primeiro diagnóstico em tempo real    │
│  ✅ Defino com você os 3 indicadores para monitorar │
│                                                     │
│  De R$197  por apenas R$97 (uma vez só)             │
│                                                     │
│  Disponível apenas AGORA — não aparece depois       │
└─────────────────────────────────────────────────────┘
```

**Copy completo do bloco:**

> **Antes de finalizar — uma oportunidade única:**
>
> Adicione uma **Sessão de Onboarding 1:1** ao seu plano Pro.
>
> Em 45 minutos ao vivo, nossa especialista financeira:
> - Faz o upload do seu primeiro DRE com você
> - Lê o diagnóstico gerado pela IA e explica em detalhes
> - Define os 3 indicadores mais críticos para sua empresa agora
>
> Sem enrolação. Sem apresentação genérica. Diretamente no que importa para o **seu** negócio.
>
> **Investimento:** ~~R$197~~ **R$97** — cobrado uma única vez, agora.
>
> Essa oferta só aparece aqui, neste momento.
> Depois de confirmar o pagamento, ela não estará mais disponível.
>
> ☐ Sim, quero a sessão de onboarding por +R$97 agora

---

## OPÇÃO B — Order Bump: Upgrade para Business

```
┌─────────────────────────────────────────────────────┐
│  ☑ UPGRADE: Ir direto para o Business               │
│                                                     │
│  Você está ativando o Pro (R$97/mês)               │
│  Por mais R$200/mês, tenha o Business:             │
│                                                     │
│  🔓 CNPJs ilimitados                               │
│  🔓 Relatórios customizados                        │
│  🔓 Suporte prioritário + acesso antecipado        │
│                                                     │
│  R$297/mês — cancele quando quiser                 │
│                                                     │
│  ☐ Prefiro continuar no Pro por R$97/mês          │
└─────────────────────────────────────────────────────┘
```

**Copy completo do bloco:**

> **Você está ativando o Pro. Faz sentido ir direto para o Business?**
>
> Se você tem mais de um CNPJ, sócios que precisam de visibilidade separada, ou quer relatórios com a cara da sua empresa — o **Business (R$297/mês)** foi feito para você.
>
> O que você ganha ao fazer o upgrade agora:
> - **CNPJs ilimitados** — analise todas as empresas do grupo
> - **Relatórios personalizados** — export com logo e identidade visual
> - **Suporte prioritário** — atendimento em até 4h em dias úteis
> - **Acesso antecipado** a novas funcionalidades de IA
>
> A diferença é R$200/mês. Isso é menos de R$7 por dia para ter controle financeiro completo de todo o seu grupo.
>
> ☑ Sim, prefiro ativar o Business por R$297/mês (R$200 a mais agora)
> ☐ Continuar com o Pro por R$97/mês

---

## RECOMENDAÇÃO DE IMPLEMENTAÇÃO

**Para o dev:**

```
Lógica:
- Plano selecionado = Pro → exibir Order Bump A (Sessão 1:1) como padrão
- Se marcado ☑ → adicionar SKU "onboarding-1x1" à order
- Exibir Order Bump B como alternativa (tab ou accordion abaixo)
- Nenhum order bump no fluxo Gratuito → Business (usuário já quer Business)

Colocação na tela:
- Abaixo do resumo do plano, acima do botão "Finalizar"
- Borda com destaque visual (cor diferente, ex: amarelo âmbar suave)
- Checkbox marcado por padrão (opt-OUT) aumenta conversão
```

**Raciocínio estratégico:**
- Order bump de onboarding 1:1 resolve a principal objeção oculta: "e se eu não souber usar?"
- Preço de R$97 no checkout é percebido como pequeno quando o usuário já comprometeu R$97/mês
- Urgência real: sessão é limitada por agenda — copy não mente, a oferta sai do checkout após confirmação

---

## VARIAÇÕES DE A/B PARA TESTAR

| Variante | Hipótese |
|---|---|
| Checkbox marcado por padrão (opt-out) | Aumenta take rate — usuário precisa desmarcar ativamente |
| Checkbox desmarcado (opt-in) | Menor volume, mas leads mais qualificados |
| Texto "Só aparece aqui" em vermelho | Urgência visual aumenta cliques |
| Texto "Esgotando — 3 vagas esta semana" | Escassez aumenta conversão mas precisa ser verdadeiro |

---

*Bella — Máxima Finance IA*
