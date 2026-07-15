# Página de Vendas — Seção: Downsell — Oferta de Recuperação (Última Chance)
*Produzido por Bella — Turno da noite — 15/07/2026*

---

## CONTEXTO DE USO

Esta página aparece **imediatamente após o usuário recusar o upsell Pro** ou fechar o checkout sem comprar.
É a última tentativa de conversão antes de o lead sair da jornada de compra.
Tom: acolhedor, sem pressão — oferta de entrada de baixíssimo atrito.

---

## GATILHO DE EXIBIÇÃO

Quando o usuário clica em "Não, quero continuar no plano gratuito" ou abandona o checkout,
redirecionar para esta página (ou exibir como modal de saída).

---

## COPY COMPLETO

---

### Headline

**Espera — antes de ir embora.**

*(fonte grande, centralizada, sem urgência agressiva)*

---

### Subheadline

*Você não precisa de tudo agora. Mas precisa de um primeiro passo.*

---

### Corpo principal

Karina entende que talvez você ainda não esteja pronto para o plano Pro.

Mas existe uma coisa que a maioria dos empresários deixa pra depois — e que custa muito caro quando o assunto é DRE:

**Não saber o que os números estão dizendo.**

---

Por isso, criamos uma oferta especial só para quem está saindo agora.

---

### Caixa de Oferta (destaque visual)

---

🎁 **ACESSO ESTENDIDO — GRATUITO POR 30 DIAS**

Ative hoje e ganhe:

✅ **3 análises completas de DRE** (no plano gratuito são apenas 1)
✅ **Acesso ao Chat Sofia** por 30 dias sem limitação
✅ **Relatório de diagnóstico inicial** entregue em até 24h por e-mail
✅ **Onboarding guiado** — você envia seu primeiro DRE e a Sofia interpreta ao vivo

**Sem cartão de crédito. Sem cobrança. Sem pegadinha.**

Depois dos 30 dias, se quiser continuar com mais análises, você ativa o Pro por R$97/mês.
Se não quiser — sem compromisso, sem multa, sem chateação.

---

### CTA Principal

**[Quero meus 30 dias grátis → Ativar agora]**

*(botão verde, grande, centralizado)*

---

### Prova Social Rápida (abaixo do botão)

> *"Comecei no gratuito, fiz 2 análises e entendi mais do meu DRE em 1 hora do que em 5 anos com meu contador."*
> — **Renato S., dono de distribuidora, SP**

---

### Parágrafo de reforço (menor, cinza)

Mais de **1.200 empresários** já usaram o Máxima Finance para entender seus números.
Não deixe o seu DRE parado numa gaveta — ele tem respostas que você precisa.

---

### Link de saída (texto, discreto)

*Não, obrigado. Prefiro continuar sem analisar meu DRE. →*

*(esse link fecha o modal ou redireciona para o dashboard gratuito padrão)*

---

## INSTRUÇÕES TÉCNICAS DE IMPLEMENTAÇÃO

| Campo | Valor |
|---|---|
| Trigger | Clique em "Não quero o Pro" OU abandono do checkout (exit intent) |
| Exibição | Modal fullscreen ou redirect para `/downsell` |
| CTA URL | `/ativar-trial-30-dias` com parâmetro `?source=downsell` |
| Rastreamento | Evento GA4: `downsell_accept` / `downsell_reject` |
| Limite de exibição | Mostrar apenas 1x por sessão, máximo 2x por usuário no mês |

---

## VARIANTE A/B SUGERIDA

**Variante A (padrão acima):** foco no benefício de tempo (30 dias grátis)
**Variante B:** foco no risco de não agir — headline: *"Você sabe qual é a sua margem real agora?"*

Testar com 50/50 por 14 dias e manter a que tiver maior taxa de ativação.

---

## POSIÇÃO NO FUNIL

```
Cadastro gratuito
    ↓
Thank You Page (boas-vindas)
    ↓
Upsell → Pro R$97/mês
    ↓
Order Bump → Business R$297 + sessão 1:1
    ↓
[recusa] → DOWNSELL (esta página) → Trial 30 dias estendido
    ↓
Sequência de e-mails de ativação (7 dias)
```

---

*Produzido por Bella | bella@maximafinance.ia*
