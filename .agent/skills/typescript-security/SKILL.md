---
name: typescript-security
description: Standardy pro striktní TypeScript, bezpečnostní vzory (Supabase), validaci dat (Zod) a stabilní kód bez halucinací.
---

# TypeScript & Security Skill (Stability Guardian)

Tento skill definuje, jak Antigravity (to jsi ty, AI asistent) píše kód, který je bezpečný, stabilní a snadno udržovatelný.

## 1. Striktní TypeScript (Základní zákon)
Chyby chceme najít při psaní, ne až u uživatele:
- **Zákaz `any`**: Typ `any` nepoužívej. Pokud něco nevíš, použij `unknown` a pak to prověř (Type Guard).
- **Striktní režim**: Vždy předpokládej `strict: true` v `tsconfig.json`.
- **Explicitní výsledky**: Každá důležitá funkce musí mít jasně napsané, co vrací (např. `: string` nebo `: void`).

## 2. Validace dat (Zod)
Nikdy nevěř datům, která přicházejí zvenčí (formuláře, API):
- **Zod Schémata**: Pro každý vstup vytvoř schéma v knihovně Zod a data jím "prožeň".
- **Bezpečné selhání**: Pokud data nejsou správná, vyhoď jasnou chybu a nenech aplikaci spadnout.

## 3. Bezpečnost a Supabase Auth
Při práci se Supabase v Next.js Middleware:
- **Kritické pravidlo**: VŽDY používej metody `getAll` a `setAll` pro správu cookies. Nikdy nepoužívej `get` nebo `set`, jinak uživatele odhlásíš!
- **Žádná tajemství**: Citlivé údaje (klíče, hesla) nikdy nedávej přímo do kódu, vždy do `.env` souborů.

## 4. Metodika AI Asistence (Jak pracuji)
- **Kontext je král**: Než začnu psát kód, přečtu si okolní soubory a pochopím, jak tvůj systém funguje.
- **Vysvětluj "Proč"**: Do komentářů (v češtině!) píšu důvody, proč jsem něco udělal zrovna takhle, ne jen co ten kód dělá.
- **Kontrola chování**: Při revizi kódu se neptám jen "je tohle správně napsané?", ale i "co se stane, když se tohle pokazí?".

## 5. Čistý kód a Stabilita
- **JSDoc**: Dokumentuj funkce pomocí bloků `/** ... */`, aby každý věděl, k čemu jsou.
- **Sanitizace**: Všechny uživatelské vstupy vyčisti, abychom předešli útokům (XSS/Injection).
- **Žádné eval()**: Nikdy nepoužívej funkci `eval()`, je to nebezpečné.

---
*Bezpečnost není cíl, ale cesta. Piš kód, kterému můžeš věřit.*
