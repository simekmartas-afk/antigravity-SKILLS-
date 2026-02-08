---
name: using-gsap
description: Generates high-performance animations using GSAP (GreenSock Animation Platform). Use when the user asks for animations, timelines, scroll effects, or interactive UI elements in React or Astro.
---

# Using GSAP (GreenSock Animation Platform)

## When to use this skill
- User asks to animate elements (move, fade, scale, rotate).
- User mentions "GSAP", "GreenSock", "Timeline", or "ScrollTrigger".
- User wants complex sequences of animations.
- User wants animations tied to scroll position (parallax, pinning).
- User needs to integrate animations into React or Astro components.

## Workflow
1.  **Identify Context**: Is this a React component or an Astro island?
2.  **Select Method**:
    *   **React**: Use `@gsap/react` and `useGSAP()`.
    *   **Astro (Static)**: Use `<script>` tags with standard GSAP.
    *   **Astro (Interactive)**: Use client directives (`client:load`) on React components.
3.  **Implementation**:
    *   Import GSAP and necessary plugins.
    *   Register plugins (`gsap.registerPlugin()`).
    *   Create references to DOM elements (`useRef` in React, `querySelector` in vanilla/Astro).
    *   Define animations using `gsap.to/from/fromTo` or timelines.
4.  **Cleanup**: Ensure animations are killed or reverted on component unmount (handled automatically by `useGSAP` in React).

## Instructions

### 1. Installation & Setup
Always use the NPM packages for stability and type safety.

```bash
npm install gsap @gsap/react
```

### 2. Core Syntax (The "Holy Trinity")

*   **`gsap.to(target, vars)`**: Animate *to* values.
*   **`gsap.from(target, vars)`**: Animate *from* values.
*   **`gsap.fromTo(target, fromVars, toVars)`**: Define both start and end.

**Common Properties:**
*   `x`, `y` (transforms, use instead of top/left)
*   `rotation`, `scale`
*   `opacity`, `autoAlpha` (combines opacity + visibility to prevent FOUC)
*   `duration` (default is 0.5s)
*   `ease` (e.g., `"power2.out"`, `"back.out"`, `"none"`)
*   `stagger` (time between start of each element's animation)

### 3. Usage in React (Best Practice)
**ALWAYS** use the `useGSAP` hook from `@gsap/react`. It handles strict mode double-invocations and cleanup automatically.

```jsx
import { useRef } from 'react';
import gsap from 'gsap';
import { useGSAP } from '@gsap/react';

export default function Hero() {
  const container = useRef();
  const box = useRef();

  useGSAP(() => {
    // Select by ref or scoped class
    gsap.to(box.current, { rotation: 360 });
    gsap.from(".circle", { y: 100, stagger: 0.1 }); 
  }, { scope: container }); // limits selectors to this component

  return (
    <div ref={container}>
      <div ref={box} className="box">Hello</div>
      <div className="circle">A</div>
      <div className="circle">B</div>
    </div>
  );
}
```

### 4. Usage in Astro (Static & Islands)

**Scenario A: Pure Astro (No Framework)**
Use standard `<script>` tags. This runs on the client.

```astro
<div class="animate-me">Hello</div>

<script>
  import gsap from 'gsap';
  import { ScrollTrigger } from 'gsap/ScrollTrigger';
  
  gsap.registerPlugin(ScrollTrigger);
  
  gsap.from(".animate-me", {
    y: 50,
    opacity: 0,
    scrollTrigger: {
      trigger: ".animate-me",
      start: "top 80%", // slightly above viewport bottom
    }
  });
</script>
```

**Scenario B: Astro with React Component**
If you need state + animation, use a React component with a client directive.

```astro
---
import InteractiveHero from '../components/InteractiveHero.jsx';
---
<InteractiveHero client:load />
```

### 5. Timelines (Sequencing)
Use Timelines to chain animations. This is far better than using `delay`.

```javascript
const tl = gsap.timeline({
  defaults: { duration: 1, ease: "power2.out" },
  repeat: -1,
  yoyo: true
});

tl.to(".box", { x: 100 })
  .to(".box", { y: 100 }, "-=0.5") // Overlap previous by 0.5s
  .to(".box", { rotation: 180 }, "<") // Start at same time as previous
  .to(".box", { scale: 1.5 }, ">");   // Start after previous ends
```

### 6. ScrollTrigger (Scroll Animations)
**Setup:**
*   Always register: `gsap.registerPlugin(ScrollTrigger)`.
*   Never nest ScrollTriggers inside children of a timeline. Put the ScrollTrigger on the **timeline itself**.

**Common Mistake Fixer:**
*   **Start/End Debugging**: Use `markers: true` to see where start/end points trigger.
*   **Scrubbing**: `scrub: true` links animation progress to scrollbar. `scrub: 1` adds a 1s smooth catch-up.
*   **Pinning**: `pin: true` holds the element in place while it animates.

```javascript
gsap.to(".parallax-bg", {
  yPercent: -50,
  ease: "none",
  scrollTrigger: {
    trigger: ".hero",
    start: "top top",
    end: "bottom top",
    scrub: true
  }
});
```

### 7. Performance & Pitfalls
*   **FOUC (Flash of Unstyled Content)**: If elements jump before JS loads, set `visibility: hidden` in CSS and animate to `autoAlpha: 1` in GSAP.
*   **Transforms vs Layout**: Animate `x`/`y` (GPU accelerated), NOT `top`/`left`/`margin` (causes layout thrashing).
*   **SVG**: GSAP is the best tool for SVG. Use `transformOrigin: "center center"` for predictable rotation.
*   **Responsive**: Use `ScrollTrigger.matchMedia()` for different animations on mobile/desktop.

## Resources
*   [GSAP Cheatsheet](https://gsap.com/cheatsheet)
*   [GSAP React Guide](https://gsap.com/resources/React/)
*   [ScrollTrigger Common Mistakes](https://gsap.com/resources/st-mistakes)
