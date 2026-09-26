<p align="center">
  <img src="logo.png" alt="ai-kit" width="480">
</p>

# ai-kit

A flat collection of subagents and skills for **Claude Code**. By Ivan K. (<https://github.com/ivklgn>)

- `agents/` — one `<name>.md` per subagent.
- `skills/` — one directory per skill, each with a `SKILL.md`.

## Agents

| Agent | For |
|-------|-----|
| `android-developer` | Native Android (Kotlin, Jetpack Compose, AndroidX); detects SDK/AGP versions and UI stack first. |
| `architect-reviewer` | Macro-level architecture review: service boundaries, scalability, coupling, tech-stack choices. Advises, doesn't implement. |
| `bdd-specialist` | Gherkin scenarios and acceptance tests; detects the BDD runner (Cucumber, Behave, pytest-bdd, godog, …). |
| `business-analyst` | Requirements analysis, specs, user stories, acceptance criteria, product docs. |
| `cli-developer` | Command-line tools: argument parsing, prompts, shell completions, cross-platform distribution. |
| `css-developer` | CSS/SCSS: layout, responsive behavior, animations, theming; modern-feature research and cleanup. |
| `deployment-engineer` | CI/CD and deployment strategies (blue-green, canary, rolling), GitOps, DORA metrics. |
| `documentation-developer` | Building docs sites (Starlight, Docusaurus, VitePress): SSG/SSR, components, styling. |
| `documentation-writer` | Developer-facing content: concept docs, guides, tutorials, references. Focuses on words and structure. |
| `frontend-developer` | Cross-cutting frontend lead; detects framework/stack. For narrow work, prefer the focused agents. |
| `frontend-figma-layout-designer` | Turns Figma-exported HTML/CSS into clean React components with organized CSS/SCSS. |
| `golang-pro` | High-performance Go: concurrency, cloud-native microservices, idiomatic patterns. |
| `instantdb-expert` | InstantDB realtime database: code generation, reviews, type-safe patterns. |
| `ios-developer` | Native iOS (Swift, SwiftUI, UIKit interop); detects deployment target and Swift version first. |
| `js-perf-analyzer` | JS/TS performance and memory-leak detection; V8/libuv internals, bundle regressions, Node tuning. |
| `llm-architect` | Production LLM systems: inference serving, RAG, fine-tuning, multi-model orchestration, cost. |
| `mcp-developer` | MCP servers and clients: build, debug, optimize. |
| `npm-updater` | Checks npm updates, reads changelogs, runs security audits, writes update reports. |
| `platform-engineer` | Internal developer platforms: self-service infra, Backstage portals, golden paths, GitOps. |
| `playwright-e2e` | Playwright E2E: write, review, debug, and optimize tests. |
| `postgres-pro` | PostgreSQL design and performance: relational modeling, normalization, internals. |
| `prompt-engineer` | Production prompt design: A/B testing, eval frameworks, token/cost optimization. |
| `python-pro` | Idiomatic, type-safe Python; detects version, package manager, toolchain first. |
| `react-code-optimizer` | Fixes re-renders, duplicates, and component splitting per the project's React version. |
| `react-specialist` | Modern React patterns per the detected version: performance, hooks, server components. |
| `reatom-guru` | React + Reatom state manager: write, review, refactor by Reatom best practices. |
| `security-auditor` | Code/infra vulnerability audit (OWASP Top 10, CVEs), threat modeling. |
| `security-engineer` | DevSecOps, zero-trust, compliance (SOC2, ISO27001), CI/CD security. |
| `typescript-pro` | Advanced TypeScript: type system, full-stack, build optimization. |
| `unit-test-master` | Isolated, deterministic unit tests; detects language and framework. Unit scope only. |

## Skills

| Skill | For |
|-------|-----|
| `12-factor-apps` | 12-Factor App compliance analysis of a codebase. |
| `ask-me` | Turns the current plan into a list of what only you can supply — decisions, facts, credentials, real-world actions. |
| `audit-website` | Automated technical site audit via the squirrelscan CLI (230+ rules, health score, broken links, meta tags). |
| `can-i-use` | Browser support for web features against the project's browserslist targets; Baseline status, fallbacks. |
| `code-reviewer` | Diff/file review for bugs, security issues, code smells, and N+1; structured, prioritized report. |
| `compatibility-audit` | Whether a change fits across contract, conventions, completeness, and runtime; per-axis verdict and migration path. |
| `explain-branch-changes` | Explains the branch's changes in plain product language for a non-technical audience. |
| `humanizer` | Removes signs of AI-generated writing (English); based on Wikipedia's "Signs of AI writing". |
| `humanizer-ru` | Очеловечивание русскоязычного текста; убирает следы AI-генерации. |
| `jsdoc` | Write/fix/review JSDoc for JS/TS; detects typed-JSDoc vs TypeScript vs a doc generator. |
| `load-branch-changes` | Loads the branch diff, commits, and changed files into session context. |
| `nextjs-developer` | Next.js App Router work: server components/actions, route handlers, middleware, metadata. |
| `recap` | Dense five-slot session status (goal, done, current step, open items, next step) in the session's language. |
| `reset-permissions` | Resets accumulated permissions in `.claude/settings.local.json`. |
| `review-golang` | Comprehensive Go review on git-changed files via the `golang-pro` agent plus Context7 docs. |
| `seo-audit` | Manual, strategic SEO review (crawlability, on-page, content, keywords); no tooling required. |
| `simplify-code-comments` | Keeps comments signal-only in any language; deletes noise, preserves doc/why comments. |
| `test-health-check` | Proves a test genuinely guards its behavior via targeted fault probes, instead of trusting coverage. |
| `update-golang-deps` | Audits and updates Go modules (go toolchain + govulncheck); patch auto, minor/major confirmed. |
| `update-node-deps` | Audits and updates Node deps (npm/pnpm/yarn/bun); patch auto, minor/major confirmed. |

## Credits

Several agents and skills are ports of, or are adapted from, third-party MIT-licensed projects. The complete component → source map with full license texts lives in [`THIRD-PARTY-LICENSES.md`](THIRD-PARTY-LICENSES.md); ported skills additionally carry an `ATTRIBUTION.md` in their directory describing what was changed.

- **`12-factor-apps`** — port of the [`12-factor-apps`](https://clawhub.ai/anderskev/12-factor-apps) skill by **anderskev** (clawhub.ai, MIT-0), built on the [Twelve-Factor App](https://12factor.net) methodology by Adam Wiggins
- **`audit-website`** — port from [squirrelscan/skills](https://github.com/squirrelscan/skills) by **squirrelscan** (MIT)
- **`seo-audit`** — condensed adaptation from [marketingskills](https://github.com/coreyhaines31/marketingskills) by **Corey Haines** (MIT)
- **`code-reviewer`** and **`nextjs-developer`** — ports from [jeffallan/claude-skills](https://github.com/Jeffallan/claude-skills) by **Jeff Allan** (MIT); two code-reviewer references were adapted upstream from [obra/superpowers](https://github.com/obra/superpowers) by **Jesse Vincent** (MIT)
- **`humanizer`** — port of [blader/humanizer](https://github.com/blader/humanizer) by **Siqi Chen** (MIT), based on Wikipedia's "Signs of AI writing" guide; **`humanizer-ru`** — port of [ilyautov/humanizer-ru](https://github.com/ilyautov/humanizer-ru) by **Ilya Utov** (MIT)
- **`python-pro`**, **`ios-developer`**, **`frontend-developer`** agents — adapted from [wshobson/agents](https://github.com/wshobson/agents) by **Seth Hobson** (MIT)
- **`android-developer`**, **`typescript-pro`**, **`golang-pro`**, **`mcp-developer`**, **`cli-developer`**, **`llm-architect`**, **`architect-reviewer`**, **`platform-engineer`**, **`prompt-engineer`** agents — adapted from [VoltAgent/awesome-claude-code-subagents](https://github.com/VoltAgent/awesome-claude-code-subagents) (MIT)
- **`unit-test-master`**, **`bdd-specialist`**, **`compatibility-audit`** — original text drawing on patterns from [testland/qa](https://github.com/testland/qa) (MIT) and wshobson/agents

All adaptations are substantially rewritten for ai-kit's detect-the-project-first conventions.

## License

[MIT](LICENSE) © ivklgn
