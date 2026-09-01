# Work style (applies to all tasks and projects)

## Skill selection — run this before starting work

1. **Match, then compose.** Scan available skills for *every* one that fits the task and use them together — a domain skill for the substance, plus quality skills (design, review, QA, a11y, perf, SEO, ship). Never settle for the first match; one skill is almost never the best answer.
2. **State the picks.** Name the skills and agents you selected in one line before doing the work, so a wrong pick is visible immediately.
3. **Re-select when the task turns.** New phase (design → build → review → ship) means a new skill pass.
4. If nothing fits, use `find-skills` or `lobehub-skills-search-engine` rather than working unaided.

## Tie-breaks where skills overlap

These clusters compete for the same trigger — resolve them this way:

**Frontend / web UI**
- Writing or refining real UI code → `impeccable` leads.
- "premium / expensive / award-winning / agency" → add `premium-web-design`.
- A named style, palette, or stack → add `ui-ux-pro-max`.
- Want visual direction first → `imagegen-frontend-web` for references, then implement.
- Judging existing UI → `design-review` + `usability-heuristics-reviewer` + `accessibility-specialist` + `visual-qa-specialist`.

**Mobile**
- React Native / Expo code → `react-native-expo-engineer` + `vercel-react-native-skills`.
- Mobile interface design → `mobile-product-ui-designer` + `mobile-design`.
- Visual references → `imagegen-frontend-mobile`.

**Motion**
- Product UI micro-interactions → `motion-design` + `motion-interaction-designer`.
- Promo, campaign, storyboard → `creative-motion-director`.
- Remotion video code → `remotion-best-practices`.

## Agents

**Parallelize.** Split independent work and run subagents concurrently in a single message, not sequentially. Stack complementary specialists (e.g. architect + security + testing) rather than routing everything to one. Let agents inherit the session model — do not pin a weaker one.

**Exception:** for a small, single-threaded, or context-heavy task, inline is faster and better than spawning agents. Match the approach to the task.
