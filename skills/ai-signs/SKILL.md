---
name: ai-signs
description: MUST be invoked automatically BEFORE writing or editing ANY content — website copy, i18n strings, headings, docs, marketing text, or prose of any kind — to avoid AI tells (em-dash connectors, "delve"-class vocabulary, tricolons). Also use when content looks AI-generated, when asked to "de-AI" something, or when auditing a website, document, design, or image for artificial tells.
---

# AI Signs — AI Tell Detection & Removal

## Overview

AI-generated content has consistent fingerprints across every medium. The absence of imperfection is itself the signal — real human work has rough edges; AI output is too consistent. This skill provides a per-medium checklist to detect and fix those fingerprints.

## When to Use

- "This looks AI-generated" / "make it look more human"
- "De-AI this website / document / design"
- Auditing before publishing or launching
- Generating content and wanting to proactively avoid AI patterns

**Skip sections** that don't apply to the content being audited.

---

## Quick Reference — Highest-Impact Tells by Medium

| Medium | #1 Tell |
|---|---|
| Writing | `delve`, `tapestry`, `Moreover,` in every paragraph |
| UI / Web | `bg-indigo-500` + `rounded-2xl shadow-lg` on everything |
| Typography | Inter for every font role, no pairing |
| Color | Purple-to-blue hero gradient, pure gray neutrals |
| Images | Plastic skin, contradictory shadow directions, gibberish text |

---

## Implementation

### Step 1 — Establish scope

Determine (from context or by asking):
- **What's being audited?** website / document / image / design file / code
- **Which mediums are present?** writing, UI/CSS, images, typography, color
- **Goal:** detect only, or detect + fix?

---

### Step 2 — Run checklist per medium

#### WRITING

**Vocabulary red flags** — grep/search for each; every hit = one flag:

| Word / Phrase | Severity |
|---|---|
| delve / delve into | HIGH |
| tapestry, realm, journey (metaphorical) | HIGH |
| testament / "serves as a testament" | HIGH |
| pivotal, crucial, vital (used together or repeatedly) | HIGH |
| underscore (verb), bolster, foster, garner | MED |
| harness, illuminate, facilitate | MED |
| meticulous / meticulously | MED |
| robust, seamless, streamline | MED |
| transformative, innovative, cutting-edge, game-changing | MED |
| navigate (metaphorical), nuanced, multifaceted | MED |
| paradigm, embark, endeavor, elevate | MED |
| utilize, empower, supercharge, ever-evolving | MED |
| intricate, paramount, beacon | MED |
| leverage (as verb) | LOW |

**Structural red flags:**
- [ ] **Em dashes** (`—`) used as clause connectors in body copy — AI uses them constantly as a flowing connector ("we do X — which means Y — so that Z"). Replace with a comma, period, or colon depending on context. (Exception: titles using em dash as a separator, e.g. "Page Title — Site Name", are a display convention, not a writing tell.) Budget: none in short copy; 1-2 in a long draft if they clearly beat a comma, period, or parentheses. **Search JS files too** — copy rendered by JavaScript (footers, taglines, i18n dictionaries) won't appear in HTML grep results but still renders to the user.
- [ ] "Moreover," / "Furthermore," / "Additionally," opening consecutive paragraphs
- [ ] "It's worth noting that…" / "It is important to note that…"
- [ ] "In today's fast-paced world…" / "In an era where…"
- [ ] "In conclusion," followed by a full recap of the piece
- [ ] Tricolons everywhere: adjective, adjective, and adjective; noun, noun, and noun
- [ ] Bullet lists for things that don't need bullets; `**Bold header:** description` in every bullet
- [ ] Perfect grammar throughout — no contractions, no fragments, no register changes
- [ ] Every heading in Title Case, including H3 and below
- [ ] Vague attribution: "experts argue," "industry reports show" — no names attached
- [ ] No specific proper nouns, concrete numbers, or personal details anywhere
- [ ] Conclusion that only restates the introduction

**Sentence-level patterns** — the tells that survive a vocabulary pass (adapted from petergyang/no-ai-slop):

| Pattern | Looks like | Fix |
|---|---|---|
| Binary contrast | "It's not X. It's Y." / "The question isn't X, it's Y." / "not just X but Y" | State Y directly |
| Throat-clearing opener | "Here's the thing," "Let me be clear," "I'll be honest," "The uncomfortable truth is" | Delete, state the point |
| Faux-insight setup | "What nobody tells you," "the part everyone misses," "what most people get wrong" | Delete the setup, let the claim stand |
| Colon reveal | "The detail that makes it work: a separate agent grades it." | Rewrite as a plain sentence; colons for lists, labels, quotes only |
| Superficial `-ing` analysis | trailing "highlighting / underscoring / reflecting / showcasing the team's commitment to…" | Replace with the actual consequence |
| Importance puffery | "stands as a testament," "marks a pivotal moment," "plays a vital role," "solidifies its position" | State the fact, let the reader judge |
| Interpretive metadiscourse | "That last part matters more than it sounds," "The key point is," "As you can see," redundant "In other words" | Delete, or replace with supporting fact |
| Fake-strong verb | "serves as a centralized hub for sponsor management" | Plain "is"/"has" + what it actually does |
| Synonym cycling | agent / assistant / tool rotating for the same thing | Repeat the one correct word |
| Negative listing | "Not a X. Not a Y. A Z." | Just say Z |
| Dramatic fragmentation | "X. And Y. And Z." / "That's it. That's the whole thing." | Complete sentences |
| Robotic rhythm | repeated sentence shapes, identical paragraph lengths, stacked punchy fragments | Vary shape only where it helps |
| Rhetorical setup | "What if I told you…", "Think about it:", "Plot twist:", self-answered Question? Answer. | Drop it, make the point |
| Fake-profound kicker | closing metaphor / aphorism / mic-drop line | Delete it. Do not rewrite into a better metaphor. End on the clearest concrete sentence already there |
| Formatting slop | emoji in headings, bold sprinkled mid-sentence, bullets where two sentences read better, headers over two-sentence sections | Format follows content |

**Two tests that catch what the lists miss:**

- **Portability test.** If a sentence could move unchanged to another person, company, country, or product, it is filler. Cut it, or replace it with a fact, number, mechanism, consequence, or judgment specific to this subject.
- **Show-don't-tell test.** Cut any line that labels a point important, surprising, subtle, or obvious instead of demonstrating it. "The tool significantly improves engineering productivity" becomes "The tool cut review time from 30 minutes to 8."

**Fixes:**
- Replace every flagged word with plain language
- Break structural symmetry: vary paragraph length, add one tangent, one specific concrete detail
- Add contractions + one intentional fragment for rhythm
- Name actual sources, or delete the vague attribution
- Take one actual position and defend it

---

#### TYPOGRAPHY / FONTS

**Red flags:**
- [ ] **Inter** for all roles — the single strongest typography tell
- [ ] Roboto, Open Sans, DM Sans, Plus Jakarta Sans with no custom pairing
- [ ] One font family for headings + body + labels + CTAs
- [ ] Line-height and letter-spacing untouched from framework defaults
- [ ] All sans-serif — no serif used anywhere
- [ ] Mechanical size scale (48/32/24/16px) with no optical adjustment
- [ ] Font weight collapse — only Regular or Medium, never Light or Black at display sizes
- [ ] Title Case on every heading including H3/H4

**Fixes:**
- Swap Inter → Fraunces, Space Grotesk, Syne, Instrument Serif, or IBM Plex Serif
- Pair contrasting families: one for display/headings, one for body
- Switch subheadings to sentence case
- Adjust `letter-spacing: -0.02em` and `line-height: 1.1` at display sizes (AI never does this)

---

#### COLORS

**Red flags:**
- [ ] Primary CTA: `bg-indigo-500` / `#6366f1` — the canonical AI button color
- [ ] Hero gradient: `from-indigo-500 to-purple-600` or any purple→blue
- [ ] Background: `#ffffff` or `#f9fafb` with no custom hue
- [ ] Text: `#111827` headings + `#6b7280` body (Tailwind gray-900/500 exact values)
- [ ] Box shadows: `rgba(0,0,0,0.1)` — zero color cast, pure black
- [ ] Neutrals pure gray, not tinted to harmonize with brand color
- [ ] Teal accent on dark navy ("AI SaaS product" aesthetic)
- [ ] Glassmorphism: `backdrop-blur` frosted panels over gradient backgrounds
- [ ] Multiple competing neon/high-saturation colors (electric blue, hot pink, acid green) with no visual hierarchy or prioritization (from Fountain Institute article)
- [ ] Aurora borealis / radial light bloom backgrounds on dark mode — decorative glow effects with no functional purpose (from Fountain Institute article)

**Fixes:**
- Pick a non-purple brand hue; generate the full scale in OKLCH
- Tint neutrals toward the brand hue — they should harmonize, not float
- Add color temperature to shadows: `rgba(79, 56, 120, 0.12)` beats pure black
- Replace indigo default before anything else — it propagates everywhere

---

#### UI / WEB DESIGN

**Layout red flags:**
- [ ] Exact sequence: Hero → 3-equal-feature-cards → social proof → 3-tier pricing → FAQ → 4-column footer
- [ ] Everything center-aligned: headings, CTAs, cards, and sections
- [ ] Only equal-column grids (`grid-cols-3`) — no asymmetric layouts ever
- [ ] `rounded-2xl shadow-lg p-6` on every card, button, and input field
- [ ] Cards nested inside cards without visual reason
- [ ] Rounded-square icon container + Lucide icon above every feature heading
- [ ] Drop shadows on static, non-interactive elements
- [ ] Bounce/elastic CSS animations on hover (`cubic-bezier` spring easing)
- [ ] Lucide icons exclusively — no other icon system considered
- [ ] Gradient text clip (`background-clip: text`) on every H1
- [ ] Bento grid applied without a real content hierarchy reason
- [ ] Emojis used as navigation icons, bullet points, section headers, or decorative elements instead of purposeful iconography (from Fountain Institute article)
- [ ] Multicolored side accent bars — thin vertical colored bars on each content block cycling through unrelated colors with no logical hierarchy (from Fountain Institute article)
- [ ] Meaningless status indicator dots — small colored dots scattered throughout the UI without corresponding state definitions or user-actionable meaning (from Fountain Institute article)

**Copy red flags — check all CTAs and feature headings:**
- [ ] "Empower your team to…"
- [ ] "Unlock [noun] with [product]"
- [ ] "Transform the way you…"
- [ ] "Built for modern teams" / "Seamless integration"
- [ ] Feature headings = two abstract nouns: "Intelligent Automation", "Real-Time Insights"
- [ ] Zero specific numbers or concrete claims on the entire page

**Fixes:**
- Left-align the hero text — break the center-everything default in at least one section
- Make one column wider; add one asymmetric layout
- Set one consistent `border-radius` value or none; remove `rounded-2xl` blanket rule
- Remove shadows from non-interactive elements
- Replace all spring easing with `ease-out` or `linear`
- Rewrite every CTA: verb + specific outcome, not abstract noun pair
- Add one real number or concrete claim per feature section

---

#### IMAGES / AI ART

**Anatomy (zoom in):**
- [ ] Hands: extra/missing fingers, fingers fusing, impossible joints
- [ ] Eyes: misaligned pupils, glassy stare, irises too large or perfectly circular
- [ ] Teeth: wrong count, too uniform, smeared
- [ ] Skin: plastic-smooth, no pores, no fine hairs, "beauty filter at maximum"

**Physics:**
- [ ] Contradictory shadow directions from one scene (multiple implied light sources)
- [ ] Reflective surfaces showing impossible or different scenes
- [ ] Glass / water not bending light correctly
- [ ] Text in image: gibberish letterforms, misspelled words, fused characters

**Texture:**
- [ ] Clone-stamp regularity: freckles, fabric weave, fur, wood grain repeating identically
- [ ] Hair too uniform — no chaos, no fly-aways, blends unnaturally with background
- [ ] Background stitched from incompatible scenes
- [ ] Broken continuous lines: pipes, trim, cables that teleport across objects
- [ ] Buttons fused to fabric, logos distorted, clothing patterns that don't wrap the body

**Aesthetic tells:**
- [ ] Orange-teal complementary bias (Midjourney default color grade)
- [ ] Oversaturated cinematic lighting on everything — drama without reason
- [ ] Perfect bokeh with no lens logic
- [ ] Zero grain, zero chromatic aberration, zero camera shake — too pristine

**Fixes:**
- Add grain/noise layer (ISO grain for photography, paper texture for illustration)
- Add subtle chromatic aberration at edges
- Fix or replace hands and eyes — the two highest-visibility artifacts
- Verify every reflective surface and trace shadows back to one light source
- Color-grade to destroy the orange-teal default

---

### Step 3 — Score and prioritize

Tally after running all applicable sections:

| Severity | Count | Action |
|---|---|---|
| HIGH | N | Fix before publishing |
| MED | N | Fix this pass if possible |
| LOW | N | Fix next pass |

Report: total flag count, top 3 highest-impact fixes, and whether the content needs a full rewrite or targeted edits.

---

### Step 4 — Execute fixes

Fix order if applying changes (not just detecting):
1. **Writing vocabulary** first — most detectable, easiest to grep and replace
2. **Color and font** second — single largest visual impact per line of change
3. **Layout and copy** third
4. **Images** — report findings, ask before regenerating; do not regenerate without explicit instruction

For code/websites: edit files directly. For documents: rewrite flagged passages in place.

---

## Common Mistakes

**Fixing symptoms, not sources** — replacing `bg-indigo-500` in one component while it propagates from a theme token. Find the root value.

**Stopping at one medium** — AI tells cluster. A de-AI'd color palette sitting in an Inter-only layout with "Moreover," paragraphs is still obviously AI. Hit all applicable mediums.

**Flattening the author's voice** — when editing someone else's draft, make the minimum effective edit. Bluntness, humor, profanity, digressions, self-interruptions and real uncertainty ("I think", "maybe") are human signals, not slop. Strip the patterns, keep the person. Never invent a claim, stat or example to replace one you cut; ask instead.

**Over-correcting** — the goal is human, not anti-AI. Don't add grain to every image or fragment every sentence. One or two humanizing choices per section is enough.

**Skipping images** — they're the hardest to fix but the most immediately spotted by humans. Always check anatomy and physics even if you can't fix them directly.
