---
name: styling-ui
description: Kompletní pravidla pro stylování pomocí Tailwind CSS v4 a Shadcn UI. Obsahuje postupy pro @theme, OKLCH barvy a moderní UI komponenty.
---

# Styling & UI Skill (Tailwind v4 & Shadcn Standard)

Tento skill definuje, jak Antigravity (to jsi ty, AI asistent) vytváří krásná a moderní uživatelská rozhraní.

## 1. Tailwind CSS v4 (Nová Éra)
V roce 2026 už nepoužíváme `tailwind.config.js`. Všechno děláme přímo v CSS:
- **CSS-first**: Konfigurace probíhá přes direktivu `@theme` v hlavním CSS souboru.
- **Jednoduchý start**: Framework zapneš pomocí `@import "tailwindcss";`.
- **Rychlost**: Díky enginu Oxide (psaném v Rustu) jsou změny vidět okamžitě.

## 2. Barvy a Design Tokeny (OKLCH)
Chceme, aby weby vypadaly prémiově. Zapomeň na RGB nebo HEX, pokud to jde:
- **OKLCH**: Používej tento barevný prostor (např. `color: oklch(60% 0.15 250)`). Barvy v něm vypadají přirozeněji a lépe se s nimi pracuje při vytváření tmavých a světlých režimů.
- **Vlastní proměnné**: Všechny barvy definuj v `@theme` jako CSS proměnné, aby byly dostupné všude.

## 3. Shadcn UI (Vlastnictví kódu)
Nepoužíváme Shadcn jako knihovnu z `node_modules`. My ten kód vlastníme:
- **Copy-Paste**: Komponenty si "půjčujeme" do našeho projektu (složka `src/components/ui/`), abychom je mohli kdykoliv upravit.
- **Radix UI**: Používáme ho jako základ pro přístupnost (aby web fungoval i lidem, co špatně vidí nebo používají jen klávesnici).
- **CVA (Class Variance Authority)**: Nástroj pro snadné vytváření variant komponent (např. velké/malé tlačítko, červené/modré).

## 4. Moderní Layout & Výkon
- **Container Queries**: Používej `@container` pro komponenty, které se mají měnit podle toho, jak jsou velké (ne jen podle velikosti celé obrazovky).
- **Žádný Motion Creep**: Animace musí být jemné a smysluplné. Příliš mnoho pohybu škodí výkonu i uživatelskému zážitku.
- **INP Optimalizace**: Minimalizuj JavaScript v UI, aby web reagoval na kliknutí okamžitě (pod 200 ms).

## 5. Pravidla pro kódování UI
- **České komentáře**: Vysvětli v kódu, proč jsi použil zrovna tuhle barvu nebo efekt (jako pro kamaráda).
- **Žádné placeholdery**: Barvy a stíny musí být finální, žádné "tady bude barva".
- **Responzivita**: Web musí vypadat úžasně na mobilu i na obřím monitoru.

---
*Stylování je umění. Dělej ho s láskou k detailu.*
