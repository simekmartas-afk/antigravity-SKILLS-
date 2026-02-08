# Antigravity SKILLS Repository

Tento repositář obsahuje specializované "dovednosti" (skills) pro AI agenta **Antigravity**. Tyto dovednosti rozšiřují schopnosti agenta o specifické workflow, standardy a nástroje.

## Hlavní princip: Context & Instructions

Nejdůležitějším dokumentem v každém projektu je **`.agent/instructions.md`**.
- Definuje cíle projektu, tech stack a specifická pravidla.
- **Určuje, které SKILLS se mají v daném projektu používat.**
- Tento soubor si agent bere do kontextu při každé interakci (nebo by měl).

**Složku `.agent` si zkopíruj do každého projektu a Antigravity s tím bude spolupracovat.**

## Přehled dostupných SKILLS


| Skill | Popis |
| :--- | :--- |
| **[Astro-React](.agent/skills/astro-react/SKILL.md)** | Kompletní návod pro vývoj v Astro + React. Pravidla pro ostrovy, hydrataci, 3D (R3F) a Nano Stores. |
| **[Brainstorming](.agent/skills/brainstorming/SKILL.md)** | Prozkoumání záměru uživatele, požadavků a designu před samotnou implementací. |
| **[Gemini Skill Creator](.agent/skills/gemini-skill-creator/SKILL.md)** | **Klíčový nástroj.** Slouží k vytváření nových dovedností pro opakující se činnosti (např. deployment). |
| **[Error Handling Patterns](.agent/skills/error-handling-patterns/SKILL.md)** | Vzory pro ošetření chyb, Result typy a propagaci chyb pro robustní aplikace. |
| **[GSAP](.agent/skills/gsap/SKILL.md)** | Vysoce výkonné webové animace, timeline a interaktivní prvky. |
| **[Planning](.agent/skills/planning/SKILL.md)** | Detailní implementační plány pro komplexní úkoly. |
| **[Styling UI](.agent/skills/styling-ui/SKILL.md)** | Pravidla pro Tailwind CSS v4 a Shadcn UI, moderní design systémy. |
| **[TypeScript Security](.agent/skills/typescript-security/SKILL.md)** | Striktní TypeScript, bezpečnostní vzory (Supabase) a validace dat (Zod). |

## Jak vytvářet nové SKILLS

Když narazíš na činnost, kterou děláš opakovaně (například specifický deployment na VPS, nahrávání souborů atd.), použij **Gemini Skill Creator**:
1. Dej agentovi do kontextu skill `gemini-skill-creator`.
2. Popiš mu činnost, kterou chceš zautomatizovat/standardizovat.
3. Nech ho vytvořit nový skill adresář v `.agent/skills/`.
4. Nový skill pak ulož sem do tohoto repositáře, abychom měli centrální zásobu dovedností.

---
*Tento dokument byl vygenerován na základě instrukcí uživatele pro efektivní "Vibe Coding" s Antigravity.*
