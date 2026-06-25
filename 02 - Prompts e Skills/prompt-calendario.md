---
tags: [prompts, calendario, conteudo]
---

# Prompt — Geração de Calendário Mensal

> Espelho de `app/src/lib/contentCalendar.ts` → função `buildCalendarPrompt`.
> Usado quando você clica em "Gerar Calendário" ou roda o job `calendar` no pipeline.

---

## O que o Claude recebe

1. **Identidade do cliente** — nome, tom de voz, objetivo, nicho, plataformas
2. **ICP** — `Estratégia/ICP.md` do cliente (até 2000 chars)
3. **Estratégia de conteúdo** — `Estratégia/estrategia-conteudo.md` (até 2000 chars)
4. **Voz e personalidade** — `Estratégia/voz.md` (até 1500 chars)
5. **Referências virais** — posts dos concorrentes scrapeados pelo Apify (últimos 30 dias)
6. **Skills de copy por formato** — regras de Reel, Carrossel, Stories, Foto

---

## O que o Claude produz

20 posts de feed para o mês (5 por semana), em JSON, com:

| Campo | Descrição |
|---|---|
| `week` | Semana do mês (1-4) |
| `day` | Dia do mês |
| `theme` | Tema do post |
| `format` | Reel / Carrossel / Foto / Stories |
| `platforms` | Instagram / TikTok |
| `hook` | Gancho de abertura |
| `objective` | TOFU / MOFU / BOFU |
| `rationale` | Por que este post neste momento do mês |
| `storiesIdea` | Stories complementar (para Reels) |

---

## Regras estratégicas aplicadas

- Semanas 1-2 → awareness/educação
- Semanas 3-4 → conversão/prova social
- Mix por semana: 2-3 Reels + 2 Carrosseis
- Reels vão automaticamente para TikTok (se cliente tiver)
- Ganchos seguem as regras de copy por formato

---

## Como personalizar por cliente

Edite o `Estratégia/voz.md` do cliente com:
- Tom específico dele/dela
- Ganchos que já funcionaram
- Frases que ele/ela usaria ou nunca usaria
- Posts aprovados anteriormente

O sistema lê automaticamente o `voz.md` antes de gerar.
