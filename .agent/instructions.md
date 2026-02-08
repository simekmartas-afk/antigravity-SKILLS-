# Project Instructions

This file (`.agent/instructions.md`) serves as the **primary source of truth and context** for the AI agent working on this specific project. It helps the agent understand the project's goals, structure, and rules immediately.

## What should be included here?

1.  **Project Overview**:
    *   Tady napíšeš co stavíš za projekt a co je cílem .. 

2.  **Tech Stack**:
    *   na čem to stavíš 
    *   Frameworks (e.g., React, Astro, Supabase)
    *   Key libraries and tools. (třeba ten GSAP na animace)

3.  **Architecture & Structure**:
    *   Key directories and their purposes.
    *   Design patterns used (e.g., MVC, Atomic Design).
    *   Data flow explanations.

4.  **Coding Standards**:
    *   Naming conventions (camelCase, snake_case).
    *   Formatting rules (if not handled by linters).
    *   Preferred approaches (e.g., "Prefer functional components", "Use Result types for errors").

5.  **Project-Specific Rules & SKILLS**:
    *   **VŽDY POUŽÍVEJ**:
        *   `planning`: Pro každý netriviální úkol.
        *   `typescript-security`: Pro psaní bezpečného a stabilního kódu.
        *   `styling-ui`: Pro veškeré úpravy rozhraní (Tailwind + Shadcn).
    *   **POUŽÍVEJ PODLE POTŘEBY**:
        *   `gsap`: Když děláme animace.
        *   `astro-react`: Standardy pro komponenty v tomto projektu.
        *   `error-handling-patterns`: Pokud implementujeme komplexnější logiku.
    *   **SKILL CREATION**:
        *   Pokud narazíš na opakující se task (např. deployment, specifický sync), použij `gemini-skill-creator` a vytvoř pro něj nový skill.

6.  **Development Workflow (Deployment)**:
    *   **Staging**: Pro nahrávání na testovací server používej skill pro deployment (pokud existuje).
    *   **Produkce**: Na produkci se dává kód až po schválení na stagingu.

> **Poznámka pro uživatele**: Do tohoto souboru piš vše, co se agentovi nechceš opakovat. Čím lepší kontext v `instructions.md`, tím lepší "Vibe" při kódování.

