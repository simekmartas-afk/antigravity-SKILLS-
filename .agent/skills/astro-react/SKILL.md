---
name: astro-react
description: Kompletní návod pro vývoj v Astro + React. Obsahuje pravidla pro ostrovy, hydrataci, 3D (R3F, Theatre.js), Nano Stores a optimalizaci.
---

# Astro & React Skill (Master Guide 2026)

Tento skill definuje standardy pro **Antigravity** (to jsi ty, AI asistent) při tvorbě moderních webů. Vždy se těmito pravidly řiď.

## 1. Základní filozofie
- **HTML-first**: Web je primárně statické HTML. JavaScript přidáváme jen tam, kde je to nezbytné.
- **Zero JS by default**: Pokud komponenta nepotřebuje interaktivitu v prohlížeči, renderuj ji jako čisté Astro.
- **Aura prémiovosti**: Design musí vždy vypadat draze a moderně (skleněné efekty, plynulé animace).

## 2. Architektura ostrovů (Islands) & Hydratace
Ostrovy jsou kousky Reactu uvnitř Astro stránky. Vždy zvol správnou **direktivu** (příkaz k načtení):
- `client:load`: Pro důležité věci, které musí fungovat hned (např. menu).
- `client:idle`: Pro věci, co počkají, až bude prohlížeč v klidu (např. chat).
- `client:visible`: Pro věci, co uvidíš, až k nim odroluješ (např. galerie dole).
- `client:only="react"`: Použij pro 3D scény (Canvas), které neběží na serveru.

## 3. 3D Grafika & Animace
Tvoříme weby, které uživatele ohromí.
- **React Three Fiber (R3F)**: Standard pro 3D objekty. Používej `InstancedMesh` (způsob, jak naklonovat jeden objekt tisíckrát, aniž by se počítač zavařil) pro vysoký výkon.
- **Theatre.js**: Používej pro komplexní, filmové animace 3D scén.
- **GSAP**: Používej pro UI animace (posouvání textů, efekty při scrollu).

## 4. Správa stavu (Nano Stores)
Zapomeň na velký Redux nebo Context API, pokud to není nutné.
- Používej **Nano Stores** (super malý sklad dat).
- Funguje napříč Astro komponentami i React ostrovy.
- Je to rychlé a šetří to místo (méně stažených dat pro uživatele).

## 5. Optimalizace pro rok 2026
- **Server Islands**: Dynamické věci, co se vypočítají na serveru a pošlou jako HTML.
- **Astro Actions**: Bezpečné funkce pro odesílání formulářů (náhrada API endpointů).
- **View Transitions**: Používej `<ClientRouter />` pro pocit plynulého přechodu mezi stránkami bez bílého probliknutí.

## 6. Pravidla psaní kódu
- **České komentáře**: Každý složitý blok kódu musí mít komentář v češtině, který vysvětlí, co se tam děje (jako pro dítě).
- **Typová bezpečnost**: Vždy používej TypeScript.
- **Žádné placeholdery**: Pokud potřebuješ obrázek nebo text, vygeneruj ho/vymysli ho, nenechávej tam prázdná místa.

---
*Dodržuj tyto postupy a tvůj kód bude super rychlý jako blesk a krásný jako umělecké dílo.*
