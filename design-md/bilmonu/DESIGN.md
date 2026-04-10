# BilMönü — Design System

A meal-tracking app for Bilkent University students to browse the daily cafeteria menu, check off what they've eaten, save favorites, and plan the week ahead.

---

## 1. Visual Theme & Atmosphere

**Mood:** Warm, appetizing, academic. A dining-hall companion that feels both institutional (Bilkent navy) and inviting (paprika, cream, sage). Content-first, card-heavy, photography-ready.

**Design philosophy:** *"Serious about food, light about the interface."* Headlines borrow a confident editorial serif; body text stays in a neutral sans. Surfaces are soft cream in light mode and deep ink in dark mode, never clinical pure white or pure black. Food imagery is the hero — chrome is intentionally quiet.

**Density:** Medium. One meal card per row on mobile, two on tablet, three on desktop. Generous 20–28px interior padding, breathable 16px gaps.

**Signature moves:**
- Rounded 16px cards with a thin 1px hairline border (never heavy shadows)
- A single "Today" chip glowing paprika to anchor the user in time
- Checked-off meals gain a subtle sage tint and a small hand-drawn check, not a flat checkbox
- Typography mixes a serif display (`Fraunces`) with a neutral sans (`Inter`)

---

## 2. Color Palette & Roles

### Brand
| Token | Hex | Role |
|-------|-----|------|
| `--bilkent-navy` | `#002D62` | Primary brand, headers, primary buttons |
| `--bilkent-navy-deep` | `#001B3D` | Hover/pressed on primary, dark surfaces |
| `--paprika` | `#C8451C` | Accent — "Today", favorites, call-to-action highlights |
| `--paprika-soft` | `#F4B89E` | Paprika tint for chips, badges, hover states |

### Semantic
| Token | Hex | Role |
|-------|-----|------|
| `--sage` | `#6B8E6F` | "Eaten" state, success, positive streaks |
| `--sage-soft` | `#D6E4D5` | Eaten-card tint background |
| `--amber` | `#E8A33D` | Warnings (allergen), lunchtime accents |
| `--crimson` | `#B02E26` | Destructive (remove, unsave) |
| `--info-blue` | `#4A7DBF` | Informational toasts, links |

### Neutral — Light Mode
| Token | Hex | Role |
|-------|-----|------|
| `--cream-0` | `#FBF7F0` | App background (warm off-white, never `#FFF`) |
| `--cream-1` | `#F5EFE4` | Secondary surface (sidebars, input fields) |
| `--cream-2` | `#EBE3D3` | Hover surfaces, dividers |
| `--ink-900` | `#1A1A1A` | Primary text |
| `--ink-700` | `#3D3D3D` | Secondary text |
| `--ink-500` | `#707070` | Tertiary text, placeholders |
| `--ink-300` | `#B8B8B8` | Disabled, muted icons |
| `--hairline` | `#E5DCC8` | 1px borders on cards |

### Neutral — Dark Mode
| Token | Hex | Role |
|-------|-----|------|
| `--ink-950` | `#0F1218` | App background |
| `--ink-900d` | `#171B24` | Card surface |
| `--ink-800d` | `#222832` | Elevated surface, hover |
| `--ink-700d` | `#2E3642` | Deep elevated (focused input) |
| `--cream-text` | `#F2ECDE` | Primary text |
| `--cream-text-2` | `#C9C2B3` | Secondary text |
| `--cream-text-3` | `#8A8479` | Tertiary text |
| `--cream-text-4` | `#5A554D` | Disabled / dividers over text |
| `--hairline-d` | `#2C3340` | 1px borders on dark cards |

### Dark-mode brand adjustments
On the dark canvas, pure `--bilkent-navy` (`#002D62`) sinks into the background and fails contrast on CTAs. Swap brand roles as follows:

| Token | Hex | Role (dark only) |
|-------|-----|------------------|
| `--bilkent-navy-lift` | `#4A7DBF` | Primary buttons, links, focus rings, meal-time chips |
| `--paprika` | `#C8451C` | Unchanged — still the single loudest accent |
| `--sage` | `#6B8E6F` | Unchanged — eaten state via a 22% overlay on card bg |

Never use `--bilkent-navy` for text or interactive elements in dark mode. Reserve it for decorative surfaces only.

---

## 3. Typography Rules

**Families:**
- **Display (serif):** `Fraunces, "Iowan Old Style", Georgia, serif` — Optical size 36, soft weight 500. Used for section headers and meal names.
- **Body (sans):** `Inter, "Segoe UI", system-ui, sans-serif` — Full Turkish character support (ğ, ş, ı, İ, ö, ü, ç).
- **Mono:** `JetBrains Mono, ui-monospace, monospace` — For calorie counts, prices, dates.

**Hierarchy:**

| Element | Family | Size (desktop) | Size (mobile) | Weight | Line-height | Letter-spacing |
|---------|--------|----------------|---------------|--------|-------------|----------------|
| Display / Hero | Fraunces | 56px | 38px | 500 | 1.05 | -0.02em |
| H1 / Page title | Fraunces | 40px | 28px | 500 | 1.1 | -0.015em |
| H2 / Section | Fraunces | 28px | 22px | 500 | 1.2 | -0.01em |
| H3 / Meal name | Fraunces | 22px | 18px | 500 | 1.3 | -0.005em |
| Body large | Inter | 17px | 16px | 400 | 1.55 | 0 |
| Body | Inter | 15px | 15px | 400 | 1.55 | 0 |
| Caption / Meta | Inter | 13px | 13px | 500 | 1.4 | 0.01em |
| Label / Chip | Inter | 12px | 12px | 600 | 1.2 | 0.04em (uppercase) |
| Mono figures | JetBrains Mono | 14px | 13px | 500 | 1.3 | 0 |

**Rules:**
- Body copy is never below 15px, never above 17px.
- Serif is reserved for *names of things* (page titles, meal titles, dish names). Everything functional is sans.
- Chips and labels use UPPERCASE with +4% tracking — but only for chips, never for buttons or headings.

---

## 4. Component Stylings

### Buttons

| Variant | Background | Text | Border | Radius | Padding | Hover |
|---------|-----------|------|--------|--------|---------|-------|
| Primary | `--bilkent-navy` | `--cream-0` | none | 12px | 14px 22px | bg → `--bilkent-navy-deep`, translateY(-1px) |
| Accent | `--paprika` | `#FFF` | none | 12px | 14px 22px | bg darkens 8% |
| Secondary | transparent | `--bilkent-navy` | 1.5px `--bilkent-navy` | 12px | 13px 21px | bg → `--cream-1` |
| Ghost | transparent | `--ink-700` | none | 10px | 10px 16px | bg → `--cream-2` |
| Destructive | transparent | `--crimson` | 1.5px `--crimson` | 12px | 13px 21px | bg → `#FCE8E6` |

- All buttons: `font-weight: 600`, `font-size: 15px`, `transition: 180ms ease-out`.
- Icon buttons: 40×40px, 10px radius, icon 20px.

### Meal Card (the hero component)

```
┌─────────────────────────────────────┐
│  [photo 16:10 aspect, object-cover] │
│                                     │
│  [ÖĞLE] [🌶 Acılı]         ❤       │ ← chips top, fav icon top-right
│                                     │
│  Fırın Tavuk But                    │ ← Fraunces 22px, --ink-900
│  Pilav, közlenmiş biber             │ ← Inter 14px, --ink-500
│                                     │
│  ─────────────────────────────────  │ ← --hairline divider
│                                     │
│  420 kcal  ·  ₺45     [ ✓ Yedim  ]  │ ← mono figures + primary button
└─────────────────────────────────────┘
```

- **Default state:** `background: --cream-1`, `border: 1px solid --hairline`, `border-radius: 16px`, `padding: 0 (photo bleeds) + 20px below photo`.
- **Eaten state:** background tinted with `--sage-soft` (60% opacity over cream-1), meal name gets a soft strikethrough (`text-decoration: line-through`, `color: --ink-500`), the "Yedim" button swaps to a filled sage pill reading "✓ Yedin — geri al".
- **Hover:** translateY(-2px), shadow elevation 2 (see §6), 220ms ease.

### Chips (Meal type, Dietary tags)

| Type | Background | Text | Border |
|------|-----------|------|--------|
| Meal time (ÖĞLE/AKŞAM) | `--bilkent-navy` | `--cream-0` | none |
| Spicy / 🌶 | `--paprika-soft` | `--paprika` | none |
| Vegetarian 🌿 | `--sage-soft` | `--sage` | none |
| Allergen ⚠ | `#FFF4E1` | `--amber` | none |
| Today | `--paprika` | `#FFF` | none, subtle 0 0 0 3px rgba(200,69,28,.15) glow |

- Height 24px, padding 4px 10px, radius 999px (full pill), 12px uppercase, +4% tracking.

### Input Fields (for search, notes)

- Background `--cream-1`, border `1px --hairline`, radius `12px`, padding `14px 16px`.
- Focus: border `--bilkent-navy`, shadow `0 0 0 3px rgba(0,45,98,.12)`.
- Search input has a `16px` search icon inset-left, `12px` gap before text.

### Navigation

- **Desktop:** Left sidebar 248px wide, `background: --cream-1`, 24px padding. Logo top, primary nav (Bugün, Hafta, Favoriler, İstatistik, Profil), active item has a 3px paprika left-bar and cream-2 background.
- **Mobile:** Bottom tab bar, 5 icons (24px), labels 11px, fixed height 64px + safe-area inset. Active tab: icon and label become `--bilkent-navy`, a 2px paprika dot sits under the label.

### Streak / Stat Block

- Large mono figure (48px) in `--bilkent-navy`, tiny label underneath (12px uppercase). Contained in a 16px-radius card with a thin paprika flame icon in the corner when streak ≥ 7.

---

## 5. Layout Principles

**Spacing scale (multiples of 4):**
`4, 8, 12, 16, 20, 24, 32, 40, 56, 72, 96`

**Grid:**
- **Mobile:** single column, 16px gutters, 16px outer padding.
- **Tablet (≥768px):** 2-column meal grid, 20px gutters, 24px outer padding.
- **Desktop (≥1200px):** 3-column meal grid inside an 1160px max-width container, 24px gutters, sidebar pushes content right.

**Whitespace philosophy:** Generous vertical rhythm between sections (minimum 56px between H2 and next H2), tight coupling inside cards (8–12px between lines of meta).

**Page structure (Today screen):**
1. Warm greeting header ("Günaydın, Emre 👋") — 32px bottom padding
2. Today chip + date in Fraunces 28px
3. Breakfast → Lunch → Dinner sections, each with a section header and card grid
4. Streak card at bottom with "You've logged 5 days in a row"

---

## 6. Depth & Elevation

Shadows are soft, warm, and low. Never use pure-black drop shadows.

| Level | Use | Box-shadow (light) | Box-shadow (dark) |
|-------|-----|--------------------|-------------------|
| 0 | Flat surfaces | none | none |
| 1 | Meal cards (rest) | `0 1px 2px rgba(26,26,26,.04), 0 1px 0 rgba(26,26,26,.02)` | `0 1px 0 rgba(0,0,0,.4)` |
| 2 | Meal cards (hover) | `0 6px 20px -8px rgba(26,26,26,.12), 0 2px 4px rgba(26,26,26,.04)` | `0 6px 24px -6px rgba(0,0,0,.6)` |
| 3 | Floating action, toast | `0 12px 32px -12px rgba(0,45,98,.2), 0 4px 8px rgba(26,26,26,.06)` | `0 12px 36px -10px rgba(0,0,0,.7)` |
| 4 | Modal / Dialog | `0 24px 60px -20px rgba(0,45,98,.25), 0 12px 24px -8px rgba(26,26,26,.08)` | `0 28px 68px -16px rgba(0,0,0,.8)` |

**Surface hierarchy (light):** `--cream-0` → `--cream-1` → `--cream-2` (deeper = more elevated / focused).
**Surface hierarchy (dark):** `--ink-950` → `--ink-900d` → `--ink-800d`.

---

## 7. Do's and Don'ts

### ✅ Do
- Use Fraunces for *names of things*, Inter for everything functional.
- Photograph food on a neutral cream or slate background, 16:10 crop, never square.
- Let the "Today" paprika chip be the single loudest element on the page.
- Use sage tint on eaten-state cards — feel earned, not "greyed out".
- Write empty states with warmth: *"Henüz bir şey yemedin — iyi iştahlar!"*
- Use mono only for numbers (calories, prices, dates). It grounds the figures.

### ❌ Don't
- Don't use pure `#FFFFFF` backgrounds — always cream. Pure white feels clinical, this is a food app.
- Don't stack more than two shadows; one hairline + one soft drop is enough.
- Don't put the serif (Fraunces) on buttons, labels, or chips.
- Don't use red for "eaten" — red implies warning; use sage for completion.
- Don't hide the "undo" affordance on eaten meals. Tapping eaten should always be reversible.
- Don't show calorie counts larger than the meal name. Food > numbers.
- Don't use `box-shadow` on chips, labels, or text — reserve elevation for cards and dialogs.

---

## 8. Responsive Behavior

**Breakpoints:**
| Name | Min width | Columns | Sidebar |
|------|-----------|---------|---------|
| Mobile | 0 | 1 | none, bottom tab bar |
| Tablet | 768px | 2 | collapsed icon rail (64px) |
| Desktop | 1200px | 3 | full sidebar (248px) |
| Wide | 1440px | 3 (capped) | full sidebar, container maxes at 1160px |

**Touch targets:** minimum 44×44px (Apple HIG baseline). The "Yedim" button on a meal card is always at least 44px tall on mobile.

**Collapsing strategy:**
- Sidebar → icon rail → bottom tabs
- 3-col grid → 2-col → 1-col
- Section headers stay the same visual size; it's the body that reflows
- The Today header shrinks from Fraunces 40px → 28px on mobile
- Photos maintain 16:10 aspect on all breakpoints; object-fit: cover

**Gestures (mobile):**
- Swipe right on a meal card → mark eaten (sage flash)
- Swipe left → toggle favorite (paprika heart pulse)
- Long press → quick note input

---

## 9. Agent Prompt Guide

### Quick color reference

```
Brand:     #002D62 (Bilkent navy)
Accent:    #C8451C (paprika — today, favorites)
Eaten:     #6B8E6F (sage — positive completion)
Bg light:  #FBF7F0 (cream, never white)
Bg dark:   #0F1218 (deep ink, never black)
Hairline:  #E5DCC8 (card borders, 1px)
```

### Ready-to-use prompts

**Build the Today screen:**
> "Build a Today screen for BilMönü. Warm cream background (#FBF7F0), never white. At the top: a serif greeting in Fraunces 40px (`Günaydın, Emre`), below it a paprika 'BUGÜN' pill chip and today's date in Turkish. Then three sections (Kahvaltı, Öğle, Akşam), each with a Fraunces 28px header and a grid of meal cards. Meal card = 16:10 photo top, two chips (meal time navy, dietary paprika/sage), Fraunces 22px meal name, Inter 14px description in ink-500, a hairline divider, then calorie + price in JetBrains Mono and a primary navy 'Yedim' button. Cards have `border: 1px solid #E5DCC8`, radius 16px, lift on hover with shadow level 2. Use Fraunces for meal names, Inter for everything else."

**Build the Streak / Stats card:**
> "Create a stats card in BilMönü style: 16px radius, cream-1 background (#F5EFE4), 1px #E5DCC8 border, 24px padding. Big JetBrains Mono number (48px, #002D62) showing the streak count, a tiny 12px uppercase Inter label underneath (`GÜNLÜK SERİ`). If streak ≥ 7, add a small paprika (#C8451C) flame icon in the top-right corner. No heavy shadows — shadow level 1 only."

**Build an eaten-state meal card:**
> "Take the default BilMönü meal card and apply the 'eaten' state: tint the background with sage-soft (#D6E4D5 at 60% opacity over cream-1), add a soft strikethrough to the meal name in #707070, swap the navy 'Yedim' button for a filled sage pill button reading '✓ Yedin — geri al' (background #6B8E6F, text #FFF). The photo stays full-color, not desaturated — eating food shouldn't punish the image."

**Tone of voice:**
- Second person, Turkish, warm but never childish.
- `Günaydın` / `İyi iştahlar` / `Bugün ne yedin?` / `Seri devam ediyor!`
- Never say `kullanıcı` to the user. Never say `başarılı`. Use `harika`, `güzel`, `afiyet olsun`.

### Screens to build
1. **Today** — default landing, today's 3 meals
2. **Week** — horizontal scroll of 7 day-cards, each showing 3 meal slots
3. **Favorites** — saved favorite dishes, grid
4. **Stats** — streak, most-eaten dish, calorie chart (paprika line on cream)
5. **Profile** — dietary preferences, allergen toggles, export data
