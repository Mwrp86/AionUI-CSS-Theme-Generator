AionUI Color Theory Reference Guide

This document defines the core color logic for the AionUI CSS Theme Generator. An AI agent must follow these mechanical rules to derive a complete CSS variable system from minimal input such as a single primary color or a style description.

🔓 Innovation Privilege
The rules below are the “safe baseline.” If the user requests a highly distinctive aesthetic such as cyberpunk, retro 8-bit, glassmorphism, wasteland, etc., you may deliberately break constraints (background brightness limits, contrast ranges, etc.) to achieve stronger visual impact. Advanced experimental logic can be written inside {{ADVANCED_EFFECTS_CSS}} at the end of the template.

---

1. Deriving a Full Palette from a Primary Color

The AionUI Brand Palette consists of 10 steps: --aou-1 through --aou-10.

Core Rule
--aou-6 must be the input Primary Color.

Derivation Logic
Use HSL adjustments for Lightness and Saturation.

Variable
--aou-1
Description: Ultra-light background
Lightness: fixed at 96%
Saturation: reduce to 10–15%

--aou-2
Light background
Lightness: fixed at 92%
Saturation: reduce to 20–25%

--aou-3
Hover background
Lightness: fixed at 85%
Saturation: reduce to 30–40%

--aou-4
Subtle border
Lightness: fixed at 75%
Saturation: keep or slightly reduce

--aou-5
Support primary
Lightness: Primary L + 10%
Saturation: unchanged

--aou-6
Primary
Lightness: original
Saturation: original

--aou-7
Hover primary
Lightness: Primary L − 8%
Saturation: unchanged

--aou-8
Active primary
Lightness: Primary L − 15%
Saturation: unchanged

--aou-9
Deep accent
Lightness: fixed at 25%
Saturation: increase 10% (max 100%)

--aou-10
Ultra-dark text
Lightness: fixed at 12%
Saturation: increase 20% (max 100%)

---

2. Background Color Derivation

Background tones should subtly reflect the hue temperature of the primary color.

Temperature Determination
Warm: Hue 0–60 (red/orange/yellow) or 300–360 (magenta/pink)
Cool: Hue 60–300 (green/cyan/blue/purple)

Light Mode (:root)

--color-bg-1 (Base)
Warm: hsl(H, 10%, 98%)
Cool: hsl(H, 8%, 98%)

--color-bg-2
Lightness 95%

--color-bg-3
Lightness 92%

--color-bg-4
Lightness 88%

--bg-hover
rgba(0, 0, 0, 0.04)

--bg-active
rgba(0, 0, 0, 0.08)

Dark Mode ([data-theme='dark'])

--color-bg-1
Warm: hsl(H, 15%, 10%)
Cool: hsl(H, 12%, 10%)

--color-bg-2
Lightness 14%

--color-bg-3
Lightness 18%

--color-bg-4
Lightness 22%

---

3. Text Color Derivation

Text must satisfy WCAG contrast standards.

--color-text-1 (Primary)
Light: hsl(H, 10%, 10%)
Dark: hsl(H, 10%, 95%)
Target contrast: 7:1

--color-text-2 (Secondary)
Light: hsl(H, 5%, 40%)
Dark: hsl(H, 5%, 70%)
Target contrast: 4.5:1

--color-text-3 (Disabled)
Light: hsl(H, 5%, 65%)
Dark: hsl(H, 5%, 45%)
Target contrast: 3:1

--text-primary
Same as --color-text-1

---

4. Semantic Color Selection

Semantic colors require brightness adjustments in dark mode.

Success
Light: #52c41a
Dark: increase lightness by 15%

Warning
Light: #faad14
Dark: increase lightness by 10%

Danger
Light: #ff4d4f
Dark: increase lightness by 15%

Info
Uses primary (--aou-6)
Dark: follow primary dark rules

---

5. Component Color Derivation

--message-user-bg
Light: --aou-1
Dark: --aou-9

--message-tips-bg
Light: rgba(0, 0, 0, 0.02)
Dark: rgba(255, 255, 255, 0.05)

--workspace-btn-bg
Light: #ffffff
Dark: --color-bg-3

--dialog-fill-0
Light: rgba(255, 255, 255, 0.8)
Dark: rgba(30, 30, 30, 0.8)

--sidebar-bg
Light: brightness −2% from --color-bg-1
Dark: brightness −3% from --color-bg-1

---

6. From Style Description to Primary Color

If the user provides a style instead of a color, map it as follows:

Cyberpunk → #00f0ff (HSL 184, 100%, 50%)
Nature/Fresh → #4caf50 (122, 39%, 49%)
Gothic/Dark → #8b0000 (0, 100%, 27%)
Muji/Minimalist → #d4a574 (31, 53%, 64%)
Ocean/Deep Blue → #0077be (202, 100%, 37%)
Lavender → #967bb6 (267, 30%, 60%)
Energetic Orange → #ff8c00 (33, 100%, 50%)
Hacker/Matrix → #00ff41 (135, 100%, 50%)
Elegant Gold → #d4af37 (45, 64%, 52%)
Sakura Pink → #ffb7c5 (348, 100%, 86%)
Corporate Blue → #1890ff (209, 100%, 54%)
Coffee/Brown → #6f4e37 (25, 34%, 33%)
Glacier/Ice → #f0f8ff (208, 100%, 97%)
Sunset → #fd5e53 (4, 98%, 66%)
Deep Forest → #013220 (156, 96%, 10%)
Royal Purple → #7851a9 (266, 35%, 49%)
Lemonade → #fff44f (56, 100%, 66%)

---

7. Extracting Colors from Background Image

If a background image is provided:

Identify dominant non-neutral color.
If color-rich, choose visually central color as --color-primary.
If grayscale-heavy, find most saturated accent.
Adjust background hue shift according to overall warm/cool atmosphere.

---

8. Dark Mode Conversion Rules

Dark mode is redistribution of brightness, not inversion.

Primary Adjustment
If Primary L < 40%, increase to 55–60% in dark mode.
--color-primary (Dark) = hsl(H, S, 60%)

Background Compression
Light mode spans 98% → 88%
Dark mode spans 10% → 22%

Border
Light: rgba(0, 0, 0, 0.1)
Dark: rgba(255, 255, 255, 0.12)

Shadow
Use deeper, tighter shadows or glow instead.

---

9. Other Derived Variable Rules

9.1 Sidebar Header Gradient

Light
FROM = Primary
TO = Primary −15% Lightness

Dark
FROM = hsl(H, S×0.8, 20%)
TO = hsl(H, S×0.8, 14%)

If saturation < 10%, use --aou-8 / --aou-9

---

9.2 Overlay Gradient Anchors

Light
rgba(R, G, B, 0.03)
transparent
rgba(R, G, B, 0.02)
Alpha range 0.02–0.05 (max 0.08)

Dark
rgba(R, G, B, 0.08)
transparent
rgba(R, G, B, 0.05)
Alpha range 0.05–0.12

---

9.3 Fill

Light: hsl(H, 10%, 80%)
Dark: hsl(H, 10%, 30%)

---

9.4 Background RGB Components

Convert hex to decimal RGB without parentheses.

Example
#f0f0f0 → 240, 240, 240

---

9.5 PRIMARY_RGB / ACCENT_RGB / D_ACCENT_RGB

Convert respective hex values to decimal R, G, B format.

---

9.6 Accent System

Warm primary → use complementary green (#4caf50 style)
Cool blue/purple → use teal or warm green
Neutral primary (S < 15%) → use complementary hue, saturation 50%+

ACCENT_LIGHT = L +15%
ACCENT_DARK = L −15%
If Accent L < 40%, raise to 55–60% in dark mode.

---
