# Página de Vendas — Seção FAQ
*Produzido por Bella — Turno da Noite — 08/07/2026*
*Rotação: Hero → Dor → Solução → Como Funciona → Planos → **FAQ** → CTA*

---

## SEÇÃO 6 DE 7 — PERGUNTAS FREQUENTES

*Instrução de design:* accordion expansível, fundo levemente destacado do restante da página, título com H2, cada pergunta com H3. Mobile-first. CTA secundária ("Experimente grátis") no final da seção.

---

### FAQ — Perguntas Frequentes

**O subtítulo da seção:**
> *Respostas diretas para as dúvidas mais comuns antes de assinar*

---

#### 1. Eu preciso saber de contabilidade para usar o Máxima Finance?

**Não.** Esse é exatamente o ponto.

Você envia a foto ou o PDF do seu DRE — o mesmo documento que o contador já entrega todo mês — e a IA da Sofia faz a leitura e a interpretação por você. Ela diz o que está bom, o que está preocupante e o que fazer a seguir, em português claro, sem termos técnicos.

Se você entende de vender e de operar o seu negócio, você já tem o que precisa para usar o Máxima.

---

#### 2. O que é o DRE? Eu preciso ter um para usar a plataforma?

DRE é a Demonstração do Resultado do Exercício — um resumo de quanto o seu negócio faturou, quanto gastou e quanto lucrou em um período. É o documento mais importante da saúde financeira de uma empresa, e a maioria das PMEs já o recebe do contador mensalmente.

Se você ainda não tem, a Sofia também pode te ajudar a entender o que pedir ao seu contador. Empresas que faturam acima de R$30 mil/mês normalmente já possuem um — às vezes só não sabem que se chama assim.

---

#### 3. Qual a diferença entre o Máxima Finance e o meu ERP (Omie, Conta Azul, Nibo...)?

**São ferramentas complementares, não concorrentes.**

O ERP organiza, lança e categoriza as suas operações. O Máxima Finance *interpreta* — pega o resultado financeiro e diz o que ele significa para o futuro do seu negócio.

É a diferença entre ter um placar do jogo e ter um técnico analisando o que está funcionando e o que precisa mudar no segundo tempo.

Muitos clientes usam Máxima Finance junto com o Omie ou Conta Azul. Um não substitui o outro.

---

#### 4. Meus dados financeiros ficam seguros?

Sim. Seguimos as diretrizes da LGPD e os seus dados não são compartilhados com terceiros nem usados para treinar modelos de IA.

Os arquivos que você envia ficam vinculados exclusivamente à sua conta. Você pode solicitar a exclusão a qualquer momento pelas configurações do perfil.

Para o plano Business, oferecemos processamento com isolamento de dados adicional — cada empresa tem seu ambiente separado.

---

#### 5. Como funciona o limite de análises? Posso analisar DREs antigos?

No plano **Gratuito**, você tem **3 análises por mês** — ideal para testar e sentir o resultado antes de assinar.

No plano **Pro (R$97/mês)**, as análises são **ilimitadas**. Você pode subir o DRE do mês atual, dos últimos 12 meses, ou vários de uma vez para comparar períodos.

No plano **Business (R$297/mês)**, além do ilimitado, você tem análises simultâneas de múltiplas empresas ou filiais no mesmo painel.

Não existe carência: você já começa a usar na hora em que assina.

---

#### 6. A Sofia é uma IA genérica ou entende de negócios brasileiros?

Sofia foi treinada especificamente para o contexto de PMEs brasileiras: sazonalidade do mercado nacional, estrutura tributária do Simples e Lucro Presumido, comportamento de margem em setores como varejo, serviços e indústria leve.

Ela não é um chatbot genérico. Cada resposta leva em conta o porte da empresa, o setor e o histórico que você compartilhou.

---

#### 7. Posso cancelar quando quiser?

Sim, sem burocracia e sem multa. O cancelamento é feito direto no painel, em menos de dois cliques. Você mantém acesso até o fim do período pago e não é cobrado no mês seguinte.

Não existe fidelidade mínima, não existe contrato anual obrigatório — embora ofereçamos desconto de 20% para quem opta pelo plano anual.

---

#### 8. Vocês oferecem suporte? E se eu tiver dúvida na hora de interpretar um resultado?

No plano Pro, o suporte é via chat com resposta em até 24 horas em dias úteis.

No plano Business, o suporte é prioritário com resposta em até 4 horas — também por WhatsApp.

Além disso, todos os planos pagos têm acesso à nossa base de conteúdo: artigos, vídeos curtos e guias práticos para que você entenda o que o DRE está mostrando mesmo sem depender de suporte.

---

#### 9. Tem período de teste gratuito?

Sim. O plano Gratuito não tem prazo de validade — é gratuito para sempre, com 3 análises por mês. Você não precisa cadastrar cartão de crédito para começar.

Quando você sentir que quer mais análises ou funcionalidades avançadas, a migração para o Pro é feita dentro da plataforma em menos de dois minutos.

---

#### 10. Para que tipo de empresa o Máxima Finance é ideal?

O produto foi desenhado para **empresas que faturam entre R$30 mil e R$500 mil por mês** — o que a gente chama de PME ativa no Brasil.

Funciona melhor para quem:
- Já tem DRE (mesmo que não entenda direito o que ele diz)
- Quer tomar decisões mais rápidas sem depender do contador para tudo
- Sente que o negócio cresce mas o caixa não acompanha
- Precisa de clareza financeira antes de contratar, investir ou cortar

Se você se reconheceu em algum desses pontos, o Máxima Finance foi feito para você.

---

### CTA interna da seção FAQ

```
[ Começar grátis — sem cartão ]

Ou fale com a Sofia agora: → [botão: "Testar 3 análises gratuitas"]
```

*Micro-copy abaixo do botão:*
> Sem fidelidade. Cancele quando quiser. 3 análises grátis por mês, para sempre.

---

## NOTAS DE IMPLEMENTAÇÃO (para o dev/Karina)

**Componente sugerido:** `<Accordion>` do shadcn/ui ou Radix UI — já compatível com o stack React do projeto.

**Ordem recomendada das perguntas na página:**
1. Preciso saber contabilidade? ← mais importante, derruba a maior barreira
2. O que é o DRE?
3. Diferença do ERP?
4. Dados seguros?
5. Como funciona o limite?
6. Sofia é genérica ou especializada?
7. Posso cancelar?
8. Suporte?
9. Teste gratuito?
10. Para qual empresa?

**SEO/Schema:** Marcar esta seção com `FAQPage` schema (JSON-LD) — aumenta chances de aparecer nos "People Also Ask" do Google para buscas como "software financeiro para pequenas empresas" e "como analisar DRE da minha empresa".

**Analytics:** Registrar qual pergunta é mais expandida — dados importantes para entender as principais objeções dos visitantes e priorizar conteúdo futuro.

---

*Bella — Assistente Autônoma Máxima Finance IA | 08/07/2026*
