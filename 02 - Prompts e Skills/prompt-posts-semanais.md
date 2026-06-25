---
tags: [prompts, posts, semanal, conteudo]
---

# Prompt — Geração de Posts Semanais

> Espelho de `app/src/lib/postGenerator.ts` → função `generateWeekPosts`.
> Usado no job `weekly-full` ou quando você clica em "Gerar Posts" na interface.

---

## O que o Claude recebe

1. **Identidade do cliente** — nome, tom de voz, objetivo, nicho
2. **ICP** — `Estratégia/ICP.md`
3. **Estratégia de conteúdo** — `Estratégia/estrategia-conteudo.md`
4. **Funil orgânico** — `Estratégia/funil-organico.md`
5. **Voz e personalidade** — `Estratégia/voz.md`
6. **Posts virais dos concorrentes** — cache em `data/competitors/<clientId>.json`
7. **Dias disponíveis** — Segunda a Sexta da semana alvo
8. **Skills de copy por formato** — regras de Reel, Carrossel, Stories, Foto

---

## O que o Claude produz

5 posts detalhados para a semana, em JSON, com:

| Campo | Descrição |
|---|---|
| `weekday` | Dia da semana (Segunda a Sexta) |
| `theme` | Tema do post |
| `format` | Reel / Carrossel / Foto / Stories |
| `hook` | Gancho de abertura (segue skill do formato) |
| `caption` | Legenda completa (200-400 chars, segue skill do formato) |
| `hashtags` | 3-5 hashtags do nicho |
| `objective` | TOFU / MOFU / BOFU |
| `cta` | Call to action específico |
| `pillar` | Pilar de conteúdo |

---

## Diferença em relação ao Calendário Mensal

| Calendário Mensal | Posts Semanais |
|---|---|
| Visão macro — 20 posts/mês | Visão micro — 5 posts/semana |
| Temas e formatos | Legendas completas e CTAs |
| Gerado uma vez por mês | Gerado toda semana |
| Modelo: Claude Sonnet | Modelo: Claude Haiku (mais rápido) |

---

## Como a legenda varia por formato

- **Reel:** hook de 1 linha + 2-3 linhas de contexto + CTA de comentário
- **Carrossel:** descreve slide a slide (Slide 1: gancho, Slides 2-4: desenvolvimento, Último: CTA)
- **Foto:** história curta com virada
- **Stories:** frase única + CTA imediato

---

## Como personalizar por cliente

O `Estratégia/voz.md` do cliente é o principal diferencial. Quanto mais rico, mais o Claude vai escrever com a cara daquele cliente específico.
