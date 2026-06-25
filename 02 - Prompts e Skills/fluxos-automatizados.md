---
tags: [prompts, fluxos, automacao]
---

# Fluxos Automatizados — Clique Boost

> Documentação dos processos automáticos do sistema.

---

## Pipeline de Onboarding (novo cliente)

```
Google Forms (briefing)
  → googleSheets.ts (detecta novo briefing)
  → onboarding.ts (cria cliente + salva Briefing/briefing.md no Obsidian)
  → icp.ts (Claude gera Estratégia/ICP.md)
  → palette.ts (Claude gera Branding/paleta.md)
  → contentCalendar.ts (Claude + Apify → Calendários/YYYY-MM.md)
  → trello.ts (cria board + cards por semana)
```

## Ciclo Semanal Completo

```
weekly-full (toda segunda-feira)
  → weeklyAnalysis.ts (Meta API → Análises/YYYY-WXX.md)
  → weeklyRefresh.ts (ajusta próxima semana no Trello)
  → postGenerator.ts (gera posts detalhados da próxima semana)
```

## Geração de Conteúdo

O Claude lê do Obsidian:
- `Estratégia/ICP.md` — quem é o cliente ideal
- `Estratégia/estrategia-conteudo.md` — pilares e objetivos
- `Estratégia/funil-organico.md` — jornada de compra

Combina com posts virais dos concorrentes (Apify) e gera calendário mensal.
