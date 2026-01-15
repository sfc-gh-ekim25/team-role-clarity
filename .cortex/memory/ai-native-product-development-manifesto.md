# AI-Native Product Development Manifesto

**Authors**: shayak, rajhans, sridhar, Joe Witt, baris, luv
**Last Updated**: Nov 19, 2025
**Status**: CEO-level strategic direction for entire company

---

## Core Thesis

AI is significantly changing how products are created and rolled out. We need to rethink product conception, implementation and roll-out.

### The Fundamental Shift
- **From**: UI-first, artifact-driven development
- **To**: Chat/CLI-first, code-first discovery

### Key Implications
- Large group of users can take basic APIs, MCPs, and build scaffolding to create products
- Open-ended agentic workflows unlock new capabilities for product discovery
- Once core APIs exist, new recipes and variants can be built in **days, not weeks or months**
- Adopt chat/CLI-first interface during discovery to expose tools incrementally, recover gracefully, establish baseline before investing in high-fidelity UI

---

## What's "Inside" vs "Periphery"

### Inside Snowflake (Core - MUST be built properly)
- Interactive tables
- Cortex Search
- Agent representations
- Core platform functionality

### Periphery (Can be built with coding agents)
- Scaffolding and recipes
- Configuration flows
- Optimization tools
- Workflows and integrations

**Moral**: If something can be coded up outside Snowflake using core Snowflake functionality, make it easy for people to.

---

## Velocity Proof

### Old Way: Raven Sales Agent
- Took several engineers several months
- Basic answer from SI team: "it's complicated; we are busy, please wait"

### New Way: Agent Optimization Tools
- Small team built v1 for creating and optimizing agents + semantic views in **less than one week**
- Includes UI for optimizing the agent
- Turned into reusable skills for SI agent lifecycle management

---

## Open-Ended vs Deterministic Workflows

### Spectrum
```
[Open-ended/Agentic] ←————————————————→ [Deterministic/UI]
     Start here                              Move here with feedback
```

### Open-Ended Workflows (Discovery Sweet Spot)
- Loosely guided text-first interfaces
- Agent instructions + API calls + guardrails
- Guide user to specific goal BUT enable flexibility
- Enable product co-discovery between developers and users
- More interaction and opportunities for discovery

### Deterministic Workflows (Later Stage)
- Very specific steps
- Constrains user to well-defined actions
- Reduces opportunities for product discovery
- Appropriate after patterns are validated

---

## Joe Witt's Thesis: Why This Matters

### Great Software = Ease of Use + Utility

**Traditional Approach**: Help user "manipulate" controls (forms, buttons, syntax)
- If product hard to use → build more UI to guide workflows
- Fighting to make things easier through more controls

**AI-Native Approach**: Help user "delegate" by expressing intent
- System (or agent) just does what is needed
- AI accelerates making users smarter and more capable
- Instead of building more UX → AI brings users to the software

### The Support Call Insight
Traditional thinking:
- "Why can't the user just be smarter?"
- "Why can't they just read the docs?"
- "Please just give me control of the mouse!"

**New approach**: Build agents and skills that behave the way WE do on support calls.

Instead of checkboxes and clicks → let them say "I want CDC from my Postgres database to my Snowflake tables" → system works them through clarifying statements → live data flowing.

---

## Builder Dos and Don'ts

### DO
- Use simple tools/MCP as much as possible
- Learn/teach by example (solve task with agent first, then generalize)
- Make Skills your primary abstraction
- Treat CLAUDE.md/Skill.MD as guardrails, not a manual (short, opinionated, focused on what agent gets wrong)
- Prefer file IO over "LLM-based I/O"
- Keep slash commands minimal (shortcuts, not new language)
- Prefer "master-clone" over brittle subagents
- Enforce at commit time with hooks
- Operationalize CI, follow secret-handling best practices

### DON'T
- Don't gatekeep essential context inside narrow subagents
- Don't over-MCP your stack (creates context bloat and security surface)
- Don't treat as "set and forget" (mine history/telemetry to improve)
- Don't make workflows very rigid (resist urge to guide too much)
- Don't say "NEVER" in prompts (allow users to recover)
- Don't stuff context everywhere (@-mentioning large files)

---

## Pattern Discovery and Reinforcement

### What Are Patterns?
Shortcuts that models can utilize for more predictable, guided execution:
- Claude Skills
- Strict orchestration workflows
- Scripts/tools
- Agent orchestration prompts
- UI widgets

### How to Create Patterns
1. Work in realistic data and environments
2. Human domain experts co-create and review
3. Log examples, use strong reasoning models to generalize
4. Infrastructure to store and retrieve (skills, UI library, prompt memory)

### Example Pattern Creation
```
> Based on the work we did in this session, can you create a Claude skill 
> called optimize-cortex-agent that helps users build a test set, evaluate and iterate.
```

---

## Development Assumptions

### CAN Assume
- Early users/implementers can use coding agents
- Engineering teams, internal teams (Product DS, Data Analytics) should create first recipes
- State can be preserved in github repo or snowflake tables
- Significant code can run as SPCS containers
- Soon: coding agent inside snowsight that can run recipes without UX

### CANNOT Assume
- Can build core functionality with vibe coding (core must be industrial strength)
- This replaces industrial strength UI for vast bulk of users
- UX development remains the same (this is "pre-UI")

---

## What Chat-First Buys You

1. **Graceful recovery from edge cases** via tool use and planning
2. **Baseline performance quickly** (even if inefficient, learn what "good enough" looks like)
3. **Progressive concretization** (promote what works → stable skills → UI)
4. **Early, honest signals** (measure task completion, interventions, rework rates)

---

## Integration with Role Clarity Framework

This manifesto provides the **operational model** for the role clarity findings:

| Role | Traditional Work | AI-Native Work |
|------|-----------------|----------------|
| **Engineering** | Build features | Own system truth + core APIs |
| **Product** | Write specs | Own decision momentum + pattern validation |
| **Design** | Build UI | Own trust/coherence + when to move right on spectrum |

### Key Connection
- **Platform clarity** (from role clarity framework) = **Core APIs and system truth** (from manifesto)
- **Low-leverage human work** (from role clarity) = **Work that should be at periphery** (from manifesto)
- **High-leverage judgment** (from role clarity) = **When to move from open-ended to deterministic** (from manifesto)

---

## Success Metrics

This strategy succeeds when:
- Users fall in love with software products faster
- Time from 0→1 measured in days, not months
- Patterns discovered and reinforced through real usage
- Core platform enables peripheral innovation
- Users can express intent and system executes
