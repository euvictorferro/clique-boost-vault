---
tags: [prompts, icp]
---

# Prompt — Geração de ICP

> Espelho de `app/src/prompts/icp.ts`. Para alterar, avise no VS Code.
> Este prompt é usado quando você clica em "Gerar ICP" para um cliente.

---

## O que o Claude recebe

- **Negócio:** nicho + descrição do que o cliente faz
- **Briefing:** respostas do formulário de onboarding

---

## O que o Claude produz

Um perfil completo do cliente ideal (ICP) com as seguintes seções:

**A) Dados Demográficos**
Nome fictício, idade, breve descrição do perfil

**B) Problema Principal**
- Problema central que o ICP enfrenta
- 5 emoções principais em torno desse problema
- 5 maiores medos
- Como esses medos afetam relacionamentos
- Frases que pessoas próximas dizem (conversacional)

**C) Outras Soluções que já tentou**
- O que tentou no passado (5-6 soluções)
- O que não quer fazer para resolver

**D) Transformação Primária**
- Como seria a vida ideal se o problema fosse resolvido
- Impacto nos relacionamentos mais próximos

**E) Especificidades do Mercado**
- Em que o ICP baseia seu sucesso
- Do que abre mão por conta do problema
- Quem culpa pelo problema
- 5 maiores objeções ao produto/serviço

**F) EJACA**
- Encorajar sonhos
- Justificar erros
- Aliviar medos
- Confirmar suspeitas
- Apontar inimigos

**G) Submercados**
5 submercados dentro do nicho

---

## Como melhorar este prompt

Se o ICP estiver saindo muito genérico, adicione ao briefing do cliente:
- Casos reais de clientes que já atendeu
- Frases que seus clientes usam com frequência
- O que diferencia quem compra de quem não compra
