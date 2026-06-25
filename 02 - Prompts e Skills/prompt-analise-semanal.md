---
tags: [prompts, analise, semanal, metricas]
---

# Prompt — Análise Semanal de Performance

> Espelho de `app/src/lib/weeklyAnalysis.ts`.
> Usado no job `weekly-analysis` ou `weekly-full`.
> **Requer Meta API funcionando** — sem token válido, não roda.

---

## O que o Claude recebe

1. **Posts da semana passada** — dados da Meta Graph API (alcance, impressões, engajamento)
2. **Top performers** — posts que mais engajaram
3. **Bottom performers** — posts que menos engajaram
4. **Comparativo** — semana atual vs. semana anterior
5. **Nicho e objetivo do cliente** — para contextualizar as recomendações

---

## O que o Claude produz

Um relatório salvo em `Análises/YYYY-WXX.md` com:

- **Resumo executivo** — o que funcionou e o que não funcionou
- **Top posts da semana** — formato, tema, métricas
- **Bottom posts** — o que não engajou e por quê
- **Insights estratégicos** — padrões identificados
- **5 recomendações** — o que fazer diferente na próxima semana

---

## Como as recomendações são usadas

O job `weekly-refresh` lê as recomendações do arquivo `Análises/` mais recente e as usa para ajustar os posts da próxima semana no Trello.

Fluxo completo:
```
Análise → recomendações → Refresh → posts ajustados no Trello
```

---

## Limitação atual

- Depende de token Meta válido (problema de expiração em <7 dias — ver pendências)
- Sem métricas reais, a análise não roda
- Workaround: rodar análise manual e adicionar direto no arquivo `Análises/`
