# Role Clarity Agent - Easy Setup Guide in Coco CLI

## What is this?

A conversational AI agent that answers questions about:
- Role clarity for Product, Design, and Engineering in AI-native development
- When to build UI vs CLI/AI
- High-leverage vs low-leverage work
- New design roles emerging from AI-native workflows

---

## One-Time Setup (5 minutes)

### Step 1: Install Cortex Code CLI

If you haven't already, install the CLI:

```bash
pip install snowflake-cli
```

Or with Homebrew:
```bash
brew install snowflake-cli
```

### Step 2: Clone this repo

Open Terminal and run:

```bash
cd ~/Desktop
git clone <REPO_URL>
cd team-role-clarity
```

*(Replace `<REPO_URL>` with the actual GitHub URL)*

### Step 3: Verify setup

```bash
ls -la .cortex/commands/
```

You should see `role-clarity.md` in the list.

---

## Using the Agent

### Start a session

From Terminal, navigate to the repo folder and start Cortex:

```bash
cd ~/Desktop/team-role-clarity
cortex
```

### Ask questions

Once Cortex starts, type `/role-clarity` followed by your question:

```
/role-clarity what are the new design roles?
```

```
/role-clarity when should we build UI vs AI?
```

```
/role-clarity what did we learn from the pilot teams?
```

```
/role-clarity how does design's role change in AI-native development?
```

---

## Example Questions for Designers

| Question | What you'll learn |
|----------|-------------------|
| `/role-clarity what does design own now?` | Design's new ownership areas |
| `/role-clarity when is UI appropriate vs AI?` | AI vs UI decision framework |
| `/role-clarity what are guardrails designers should create?` | Trust & safety design work |
| `/role-clarity what is the hybrid principle?` | CLI ↔ UI handoff design |
| `/role-clarity what is platform clarity?` | Why most slowdowns aren't role issues |
| `/role-clarity what new design roles will exist?` | Agent Experience Designer, etc. |

---

## Troubleshooting

**"command not found: cortex"**
→ Reinstall: `pip install snowflake-cli`

**"/role-clarity" doesn't work**
→ Make sure you're in the `team-role-clarity` folder before running `cortex`

**Need to update to latest version**
→ Run `git pull` in the repo folder

---

## Questions?

Reach out to Evelyn Kim or ask in the design Slack channel.
