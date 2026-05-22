<div align="center">

<br/>

<img alt="claude-code-handbook" src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=800&size=36&duration=2400&pause=900&color=A78BFA&center=true&vCenter=true&width=900&height=80&lines=claude-code-handbook"/>

**The definitive open-source guide to Claude Code.**
_From zero to expert. Skills · Hooks · MCP · Agents · Best Practices._

<br/>

```bash
# Read online
open https://handbook.claude.dev   # (coming soon)
```

```bash
# Or clone and build locally
git clone https://github.com/kasimmj/claude-code-handbook
cd claude-code-handbook && mdbook serve
```

<br/>

<p>
<img src="https://img.shields.io/badge/Claude%20Code-D97757?style=for-the-badge&logo=anthropic&logoColor=white"/>
<img src="https://img.shields.io/badge/mdBook-FFA500?style=for-the-badge"/>
<img src="https://img.shields.io/badge/CC--BY--4.0-000000?style=for-the-badge"/>
</p>

<p>
<img src="https://img.shields.io/github/stars/kasimmj/claude-code-handbook?style=social"/>
<img src="https://img.shields.io/github/forks/kasimmj/claude-code-handbook?style=social"/>
<img src="https://img.shields.io/github/contributors/kasimmj/claude-code-handbook"/>
</p>

</div>

---

## 📖 What's inside

A comprehensive, community-maintained, **always-up-to-date** guide to Claude Code — covering everything from installation to advanced multi-agent patterns.

```
                         CLAUDE CODE HANDBOOK
                         ─────────────────────

  Part I.  Getting Started
    1. Install + first run
    2. The command-line flow
    3. Understanding tool use
    4. Costs, billing, and limits

  Part II. The Building Blocks
    5. Skills — what, when, how
    6. Hooks — events and policy enforcement
    7. MCP Servers — the protocol & ecosystem
    8. Memory — persistent context across sessions
    9. Sub-agents and Task tool

  Part III. Patterns
    10. Architecture: monorepo with shared skills
    11. Solo workflow: paired with a daemon
    12. Team workflow: shared config, individual memory
    13. CI: Claude in GitHub Actions
    14. Multi-agent orchestration patterns

  Part IV. Best Practices
    15. Prompt engineering for tool use
    16. Cost optimization (Haiku/Sonnet/Opus)
    17. Privacy + secrets handling
    18. Eval and regression testing
    19. Debugging when Claude gets stuck

  Part V. Recipes
    20. Refactoring a legacy codebase
    21. Generating tests at scale
    22. Migrating between frameworks
    23. Open-sourcing an internal project
    24. Building your first MCP server

  Part VI. Ecosystem
    25. claude-code-skills-factory
    26. claude-code-orchestrator
    27. claude-code-hooks-cookbook
    28. claude-code-mcp-marketplace
    29. Other community tools

  Appendix
    A. Settings.json reference (complete)
    B. Hooks event reference
    C. MCP protocol reference
    D. Glossary
    E. Migration notes between versions
```

---

## 🎯 Who this is for

- 🆕 **First-time users** — start at Chapter 1
- 🛠️ **Daily users** — Part III + Part V for patterns
- 🏢 **Team leads** — Part III + Part IV for adoption
- 🧪 **Power users** — Part IV + Part VI for advanced tooling
- 🤝 **Contributors** — see [CONTRIBUTING.md](CONTRIBUTING.md)

---

## 📐 How it's built

- **mdBook** for the static site
- **Mermaid** for diagrams
- **Code samples** are tested in CI (yes, this entire book is `make test`-able)
- **Versioned** — when Claude Code changes, the handbook tracks it via tags
- **Translatable** — Arabic, French, Spanish, Mandarin versions in `i18n/`

---

## 🚀 Build locally

```bash
git clone https://github.com/kasimmj/claude-code-handbook
cd claude-code-handbook

# Install mdBook (requires Rust)
cargo install mdbook mdbook-mermaid

# Serve at localhost:3000
mdbook serve --open
```

---

## 🌟 Why a handbook?

The official docs are great for **reference**. They're not great for **learning**.

This handbook fills the gap:
- **Narrative-driven** — concepts build on each other
- **Example-heavy** — every claim has working code you can run
- **Opinionated** — picks one way to do something, explains why
- **Practical** — assumes you want to ship things, not just understand

---

## 📚 Sample chapter

> ### Chapter 5: Skills
>
> ### What's a skill?
>
> A skill is a reusable instruction Claude follows when triggered by a user phrase. Think of it as a "recipe" — Claude consults the skill, follows it, then returns to its normal flow.
>
> Three properties make a skill different from a normal prompt:
>
> 1. **Lazy-loaded** — Claude doesn't read it until it's needed
> 2. **Triggered by patterns** — specific user phrases activate it
> 3. **Reusable** — same skill applies across all your projects
>
> ### When to write a skill
>
> Write a skill when:
> - You find yourself giving Claude the same multi-step instruction repeatedly
> - You want the team to share a workflow
> - You're encoding a checklist (security audit, code review, deploy steps)
>
> Do NOT write a skill when:
> - The instruction is one-off
> - It's something Claude already does well by default
> - You're embedding company secrets (skills go on disk in plain text)
>
> ### Anatomy of a skill
>
> ```markdown
> ---
> name: security-audit
> description: Run an OWASP-style security audit on the current diff or repo.
> triggers:
>   - "audit security"
>   - "find vulnerabilities"
>   - "OWASP scan"
> ---
>
> # Security Audit
>
> When invoked, do the following:
> 1. ...
> ```
>
> ### Lifecycle
>
> ```mermaid
> sequenceDiagram
>     User->>Claude: "Audit my code for security"
>     Claude->>SkillsRegistry: Match trigger
>     SkillsRegistry-->>Claude: Load security-audit skill
>     Claude->>Tools: Execute audit steps
>     Claude-->>User: Audit report
> ```
>
> [Continue to: How Claude matches triggers →](skills-triggers.md)

---

## 🤝 Contributing

We need contributors for:
- 📝 New chapters / sections (open an issue first to discuss)
- 🌐 Translations (Arabic, French, Spanish, Mandarin priorities)
- 🐛 Corrections (typos, outdated examples)
- 💡 Real-world case studies

See [CONTRIBUTING.md](CONTRIBUTING.md). PRs reviewed weekly.

---

## 📜 License

Content: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
Code samples: MIT

---

<div align="center">

**Star ⭐ to support open knowledge.**

</div>
