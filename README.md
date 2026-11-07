# Finnews-Ai-project

AI-powered Financial News Simplifier using FastAPI, Groq LLM and NewsAPI.

**Author:** Dhiraj

## Live Project

[Open FinNews AI](https://lovable.dev/projects/1dbbb65b-3179-50e2-9489-1f6feb821a26)

## Source Code
@import "tailwindcss" source(none);
@source "../src";
@import "tw-animate-css";

@custom-variant dark (&:is(.dark *));

/*
 * FinNews AI design system — "plain-language newspaper".
 * Warm newsprint paper, deep ledger-green ink, saffron marker highlights.
 * All colors are oklch tokens; components use semantic utilities only.
 */

@theme inline {
  --font-display: "Fraunces", ui-serif, Georgia, serif;
  --font-sans: "Manrope", ui-sans-serif, system-ui, sans-serif;
  --font-mono: "JetBrains Mono", ui-monospace, monospace;

  --radius-sm: calc(var(--radius) - 4px);
  --radius-md: calc(var(--radius) - 2px);
  --radius-lg: var(--radius);
  --radius-xl: calc(var(--radius) + 4px);
  --radius-2xl: calc(var(--radius) + 8px);
  --radius-3xl: calc(var(--radius) + 12px);
  --radius-4xl: calc(var(--radius) + 16px);
  --color-background: var(--background);
  --color-foreground: var(--foreground);
  --color-card: var(--card);
  --color-card-foreground: var(--card-foreground);
  --color-popover: var(--popover);
  --color-popover-foreground: var(--popover-foreground);
  --color-primary: var(--primary);
  --color-primary-foreground: var(--primary-foreground);
  --color-secondary: var(--secondary);
  --color-secondary-foreground: var(--secondary-foreground);
  --color-muted: var(--muted);
  --color-muted-foreground: var(--muted-foreground);
  --color-accent: var(--accent);
  --color-accent-foreground: var(--accent-foreground);
  --color-destructive: var(--destructive);
  --color-destructive-foreground: var(--destructive-foreground);
  --color-border: var(--border);
  --color-input: var(--input);
  --color-ring: var(--ring);
  --color-ring-offset-background: var(--background);
  --color-chart-1: var(--chart-1);
  --color-chart-2: var(--chart-2);
  --color-chart-3: var(--chart-3);
  --color-chart-4: var(--chart-4);
  --color-chart-5: var(--chart-5);
  --color-sidebar: var(--sidebar);
  --color-sidebar-foreground: var(--sidebar-foreground);
  --color-sidebar-primary: var(--sidebar-primary);
  --color-sidebar-primary-foreground: var(--sidebar-primary-foreground);
  --color-sidebar-accent: var(--sidebar-accent);
  --color-sidebar-accent-foreground: var(--sidebar-accent-foreground);
  --color-sidebar-border: var(--sidebar-border);
  --color-sidebar-ring: var(--sidebar-ring);

  --color-gain: var(--gain);
  --color-gain-soft: var(--gain-soft);
  --color-loss: var(--loss);
  --color-loss-soft: var(--loss-soft);
  --color-mixed: var(--mixed);
  --color-mixed-soft: var(--mixed-soft);
  --color-marker: var(--marker);
  --color-ink: var(--ink);
  --color-paper: var(--paper);

  --shadow-press: 0 2px 0 0 var(--ink), 0 10px 24px -12px oklch(0.3 0.06 160 / 0.55);
  --shadow-press-hover: 0 4px 0 0 var(--ink), 0 16px 32px -14px oklch(0.3 0.06 160 / 0.6);
  --shadow-card: 0 1px 0 0 oklch(0.25 0.03 160 / 0.08), 0 18px 40px -28px oklch(0.25 0.04 160 / 0.45);
}

:root {
  --radius: 0.875rem;

  --paper: oklch(0.972 0.014 85);
  --ink: oklch(0.21 0.035 162);

  --background: var(--paper);
  --foreground: var(--ink);
  --card: oklch(0.992 0.006 85);
  --card-foreground: var(--ink);
  --popover: oklch(0.992 0.006 85);
  --popover-foreground: var(--ink);
  --primary: oklch(0.36 0.085 162);
  --primary-foreground: oklch(0.975 0.012 85);
  --secondary: oklch(0.935 0.022 85);
  --secondary-foreground: var(--ink);
  --muted: oklch(0.935 0.018 85);
  --muted-foreground: oklch(0.47 0.03 155);
  --accent: oklch(0.8 0.15 72);
  --accent-foreground: var(--ink);
  --destructive: oklch(0.55 0.19 28);
  --destructive-foreground: oklch(0.98 0.01 85);
  --border: oklch(0.86 0.022 85);
  --input: oklch(0.86 0.022 85);
  --ring: oklch(0.36 0.085 162);

  --gain: oklch(0.5 0.13 152);
  --gain-soft: oklch(0.93 0.05 152);
  --loss: oklch(0.53 0.18 28);
  --loss-soft: oklch(0.94 0.04 28);
  --mixed: oklch(0.58 0.13 70);
  --mixed-soft: oklch(0.94 0.06 85);
  --marker: oklch(0.9 0.14 95);

  --chart-1: oklch(0.5 0.13 152);
  --chart-2: oklch(0.8 0.15 72);
  --chart-3: oklch(0.53 0.18 28);
  --chart-4: oklch(0.36 0.085 162);
  --chart-5: oklch(0.47 0.03 155);
  --sidebar: var(--card);
  --sidebar-foreground: var(--ink);
  --sidebar-primary: var(--primary);
  --sidebar-primary-foreground: var(--primary-foreground);
  --sidebar-accent: var(--secondary);
  --sidebar-accent-foreground: var(--ink);
  --sidebar-border: var(--border);
  --sidebar-ring: var(--ring);
}

@layer base {
  * {
    border-color: var(--color-border);
  }

  body {
    background-color: var(--color-background);
    color: var(--color-foreground);
    font-family: var(--font-sans);
    -webkit-font-smoothing: antialiased;
    background-image: radial-gradient(oklch(0.21 0.035 162 / 0.045) 1px, transparent 1px);
    background-size: 18px 18px;
  }

  h1,
  h2,
  h3 {
    font-family: var(--font-display);
    letter-spacing: -0.015em;
  }
}

/* Marker-pen highlight behind words */
@utility marker {
  background-image: linear-gradient(
    100deg,
    transparent 0.2em,
    var(--marker) 0.25em,
    var(--marker) calc(100% - 0.2em),
    transparent calc(100% - 0.1em)
  );
  background-size: 100% 0.55em;
  background-position: 0 88%;
  background-repeat: no-repeat;
  padding: 0 0.08em;
  box-decoration-break: clone;
}

@utility rule-double {
  border-top: 3px double var(--ink);
}

@utility eyebrow {
  font-family: var(--font-mono);
  font-size: 0.6875rem;
  letter-spacing: 0.14em;
  text-transform: uppercase;
}

@utility shimmer {
  background: linear-gradient(
    90deg,
    var(--muted) 0%,
    oklch(0.97 0.012 85) 50%,
    var(--muted) 100%
  );
  background-size: 200% 100%;
  animation: shimmer 1.6s ease-in-out infinite;
}

@utility ticker-track {
  animation: ticker 40s linear infinite;
}

@keyframes shimmer {
  0% {
    background-position: 200% 0;
  }
  100% {
    background-position: -200% 0;
  }
}

@keyframes ticker {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}

@media (prefers-reduced-motion: reduce) {
  .ticker-track,
  .shimmer {
    animation: none;
  }
}

