# Mīzān: The Life Investor — Game Design Document (GDD)

## 1. Vision & Core Philosophy

**Tagline:** *"Every choice teaches a real lesson."*

Mīzān (ميزان — "the balance") is an educational life-simulation game that teaches Islamic principles of wealth management, halal investing, and life balance. Players experience decades of financial and life decisions and see how choices compound: charity creates **barakah** (blessing that multiplies returns over time); haram choices (riba, gharar, israf) are available but clearly flagged and lead to long-term penalties discovered organically.

**Win condition:** At age 58+, three scores—**Social**, **Spiritual**, **Financial**—determine whether the player "won at life" or merely chased money. A balanced, halal path yields the highest total fulfillment.

---

## 2. Characters (Archetypes)

| Name    | Archetype      | Backstory / Traits                    | Starting Stats (flavor)        |
|---------|----------------|----------------------------------------|-------------------------------|
| **Ahmad**  | Ambitious Engineer | Driven, career-focused; must learn balance. | Slightly higher career growth potential. |
| **Fatima** | Teacher        | Values community; naturally inclined to charity. | Social/Spiritual bonuses from teaching. |
| **Yusuf**  | Entrepreneur   | Risk-taker; tests tawakkul vs gharar.  | Higher variance in business outcomes. |
| **Maryam** | Artist         | Creative; faces income instability.   | Variable income events; creativity boosts. |

- **Custom:** Player can enter own name; uses "Traveler" archetype (balanced stats).
- All characters start at **age 22**, **$3,000/month salary**, **$0 assets**.

---

## 3. Life Phases (10 Interactive Decisions)

Exact sequence and mechanics:

| Phase | Age | Decision Type | Options / Mechanics |
|-------|-----|---------------|---------------------|
| 1 | 22 | **First salary allocation** | Sliders: Save % / Invest % / Spend % / Charity %. Must sum to 100%. |
| 2 | 23 | **First investment** | Riba (conventional stocks/bonds) vs Halal: sukuk, gold, halal REITs. Education: why riba erodes barakah. |
| 3 | 25 | **Promotion → lifestyle inflation** | Resist (save difference) vs Inflate (upgrade car/lifestyle). Trap: spending creep. |
| 4 | 27 | **Marriage** | Simple nikah (modest, blessed) vs Lavish debt wedding (israf, loans). |
| 5 | 29 | **Expat job** | Accept (high pay, family strain) vs Decline (stay, lower income). Social trade-off. |
| 6 | 32 | **Real estate** | Halal: murabaha / ijara / musharakah vs Riba mortgage. Long-term barakah vs short-term "ease." |
| 7 | 35 | **Health crisis** | Tests emergency fund + takaful. Under-saving = debt spiral; prepared = barakah. |
| 8 | 38 | **Entrepreneurship** | Start business (risk + tawakkul) vs Stay employed. Random event flavor. |
| 9 | 42 | **Marriage crisis** | Invest in family (counseling, time) vs Neglect. Risk of divorce (wealth halved, social crash). |
| 10 | 48 | **Sadaqah Jariyah** | Perpetual charity (endowment, well, school). One-time cost, ongoing spiritual + barakah. |
| End | 58 | **Legacy (Wasiyah)** | Islamic will per faraidh. Allocate estate; final reflection. |

---

## 4. Scoring System (0–100 each)

- **Financial:** Net wealth (income − expenses + investment returns − losses). Barakah multiplies halal returns over time. Riba/haram choices add volatility and eventual "erosion" events.
- **Social:** Relationships, family, community. Marriage quality, divorce, expat choice, marriage crisis resolution. Events and choices feed into a hidden social meter.
- **Spiritual:** Halal adherence, charity %, riba avoidance. Quranic/hadith-aligned choices add; haram subtracts. Sadaqah jariyah and consistent charity boost.

**Display:** Final dashboard with all three scores + **Life Balance** radar chart. Message: "You won at life" (balanced high scores) vs "You chased money" (high financial, low social/spiritual) vs other permutations.

---

## 5. Barakah System

- **Charity** (sadaqah, zakat-style giving) adds a **barakah multiplier** (e.g., 1.0 → 1.05 → 1.10 over time). Applied to halal investment returns and spiritual score growth.
- **Haram choices** (riba, gharar, israf) reduce or cap barakah; random "loss" or "crisis" events are more likely or severe.
- Implemented as a hidden modifier that scales halal gains and softens/hardens random events.

---

## 6. Haram Choices & Education Layer

- **Riba:** Interest-based products. Flagged ⚠️ in red. Education: "Riba erodes barakah; wealth may increase in number but not in blessing."
- **Gharar:** Excessive uncertainty/speculation. Flagged. Education: Gambling-like risk, not permitted.
- **Israf:** Wasteful spending. Flagged. Education: Moderation; lavish weddings, lifestyle creep.

**Per-decision pop-up:**  
- Why the haram option is risky (short paragraph).  
- Halal alternative explained.  
- 1 Quranic verse or hadith excerpt.  
- 1 real-world example (e.g., "Many who took riba mortgages lost homes in 2008.").

---

## 7. Random Events (Prototype)

3–5 triggerable events (can be tied to phase or RNG):

1. **Job loss** — Tests emergency fund; if low, debt.
2. **Market crash** — Halal portfolio dips less (or recovers faster with barakah); riba-heavy portfolio hit harder.
3. **Inheritance** — Modest sum; choice to spend vs give vs invest (halal).
4. **Haram opportunity** — High-return but riba/gharar; refuse = spiritual + barakah; accept = short-term gain, long-term penalty.
5. **Community need** — Chance to give sadaqah; boosts social + spiritual.

---

## 8. UI/UX (Islamic-Inspired)

- **Colors:** Greens (emerald, olive), golds (accents), cream/white backgrounds. Minimalist.
- **Typography:** Clean, readable; optional Arabic-supporting font for RTL verses.
- **Progress:** Age bar (22 → 58); phase indicator.
- **Inputs:** Sliders (allocation), buttons (binary/multi-choice). Touch-friendly, responsive.
- **Animations:** Subtle transitions; wealth graph that updates per phase.
- **RTL:** Arabic verse/hadith in pop-ups with RTL support.

---

## 9. Technical Specs (Prototype)

- **Single HTML file;** no external dependencies (no React/CDN).
- **State:** JSON-like object (age, wealth, scores, barakah, choices[], events[]). React-like updates (re-render key sections).
- **Save/Load:** localStorage; one slot (e.g., `mizan_save`).
- **Final screen:** Dashboard with Financial/Social/Spiritual scores, radar chart (canvas or SVG), replay and share (copy link or text summary) buttons.
- **Sound:** Optional; Web Audio API for gentle feedback (click, success, caution). No external assets.
- **Responsive:** Mobile-first; breakpoints for tablet/desktop.

---

## 10. Monetization Ideas (Future)

- **Premium "Life Extension":** Play beyond 58 (e.g., to 70) with more phases.
- **New archetypes** or story branches (DLC).
- **Multiplayer compare:** Anonymous "how did others choose?" after each phase.
- **Curriculum pack:** Teacher dashboard, lesson plans, printable reflection sheets.

---

## 11. Alternative Versions

1. **Shorter web version:** 5 phases (22, 27, 32, 42, 58); same three scores; 10–15 min play.
2. **VR life sim:** First-person "walk through" key moments (e.g., signing mortgage vs musharakah contract).
3. **Kids' edition:** Simplified (save vs spend, share with others); no riba detail; age 10–14 friendly; cartoon characters.

---

## 12. Design Principles

- **Teach without preaching:** Haram is clearly bad in-game terms (risk, volatility, narrative consequence), not moral lecture.
- **Accuracy:** Islamic finance terms (sukuk, murabaha, ijara, musharakah, takaful, faraidh) used correctly; consult scholars for release.
- **Fun:** Meaningful choices, visible impact, replayability via different archetypes and paths.
- **Inclusive:** Playable by non-Muslims as a "values-based finance" sim; deeper for Muslims with verses and hadith.

---

*End of GDD. Prototype implements the 10-phase flow, 4 archetypes + custom, barakah, three scores, education pop-ups, random events, save/load, and radar chart in a single HTML file.*
