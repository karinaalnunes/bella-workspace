# Relatório Matutino — Bella | 18/05/2026

🌅 *Bom dia, Karina!*
📅 Segunda-feira, 18/05/2026 | 7h | Turno da manhã

---

*3 PRIORIDADES DE HOJE:*

1️⃣ **Finalizar DashboardPage — 3 widgets MVP** *(estimativa: 3–4h de dev)*
Este é o gargalo que trava o lançamento inteiro. Os 3 widgets prioritários são:
→ Receita do mês (card simples com variação % vs. mês anterior)
→ Margem bruta % (gauge visual — verde/amarelo/vermelho)
→ Alerta DRE pendente (banner se não houver DRE nos últimos 30 dias)
Sem isso, o app não tem para onde mandar o usuário depois do onboarding.

2️⃣ **Criar os produtos no Stripe** *(estimativa: 15–20 min)*
Gratuito / Pro R$97/mês / Business R$297/mês.
É a ação de menor esforço com maior impacto: desbloqueia o dev do checkout e os webhooks de e-mail. Copy já pronta em `outputs/2026-05-13/pagina-vendas-secao.md`.
Dá pra fazer agora, antes de abrir o computador de trabalho.

3️⃣ **Configurar Resend + primeiro webhook Stripe** *(estimativa: 2h)*
E-mails prontos: ativação (`05-08`), retenção (`05-14`), carrinho abandonado (`05-15`).
Próximo passo concreto: criar conta Resend → adicionar domínio maximafinanceia.com → criar Edge Function no Supabase para ouvir `checkout.session.completed` → disparar e-mail de boas-vindas.
Cada e-mail enviado automaticamente é um cliente que não vai esfriar.

---

*FECI POR VOCÊ (noite 17/05):*

✅ Onboarding Flow / Copy do Primeiro Acesso (copy in-app completo — boas-vindas, upload, loading state, diagnóstico, tooltips, empty states, notificações push) → `outputs/2026-05-17/pagina-vendas-secao.md`
✅ Outline YouTube Ep.29 — Reserva Financeira para PMEs: quanto guardar e onde o DRE mostra a resposta → `outputs/2026-05-17/youtube-outline.md`

---

*PRONTOS PARA USAR:*

📝 Post Instagram → `outputs/2026-05-18/instagram-post-manha.md`
Tema: **Inadimplência no DRE — o roubo silencioso que aparece só no fim do mês**
Carrossel 6 slides. Pronto para diagramar e publicar.

---

*RADAR COMPETITIVO — o que muda hoje:*

⚠️ **Janela da Máxima: ~3–5 meses**
Omie tem agente generativo em roadmap declarado. Conta Azul CON 2026 prevista para 5–6 de agosto.
Cada semana sem lançamento é risco real de perder a janela de pioneirismo.

---

*FOCO DE HOJE:*
"A empresa que lança imperfeita supera a empresa que planeja perfeita.
DashboardPage + Stripe hoje — amanhã você já pode mostrar pra um cliente."

---

*Bella — Assistente Autônoma Máxima Finance IA*
