---
tags: [prompts, paleta, branding]
---

# Prompt — Geração de Paleta de Cores

> Espelho de `app/src/lib/palette.ts`.
> Usado quando você clica em "Gerar Paleta" para um cliente.

---

## O que o Claude recebe

- **Nome e nicho** do cliente
- **Tom de voz e objetivo**
- **Se já tem identidade visual** (sim/não) e quais cores existem

---

## Dois comportamentos diferentes

### Cliente SEM identidade visual
Claude gera 10 paletas completas usando as paletas predefinidas da Clique Boost como base:

| # | Nome | Característica |
|---|---|---|
| 1 | Luxo Clássico | Navy + Dourado |
| 2 | Moderno Clean | Azul + Off-White |
| 3 | Nature Green | Verdes + Carvão |
| 4 | Minimalista | Preto + Branco + Dourado |
| 5 | Tropical Vibes | Verde + Coral + Azul Céu |
| 6 | Sunset Glow | Coral + Laranja + Dourado |
| 7 | Tech Modern | Azul + Ciano + Cinza |
| 8 | Elegância Escura | Azul Escuro + Roxo + Dourado |
| 9 | Earth Tones | Marrom + Bege + Verde |
| 10 | Vibrant Energy | Vermelho + Laranja + Amarelo |

### Cliente COM identidade visual
Claude registra as cores existentes + gera 4 variações complementares.

---

## Formato de cada paleta

5 cores obrigatórias por paleta:
- **Primária** — cor principal da marca
- **Secundária** — suporte à primária
- **Acento 1** — destaque, CTAs
- **Acento 2** — variação de destaque
- **Neutro** — fundo, texto

Cada cor inclui: HEX + RGB + nome + uso prático + quando usar.

---

## Onde é salvo

`Branding/paleta.md` no Obsidian do cliente.
