
## Choosing a Host for Your Telegram Bot: Compute Engine vs Cloud Run

Just deployed your bot to Compute Engine and heard Cloud Run is cheaper? Here's what you actually need to know.

### Quick Comparison

| | Compute Engine | Cloud Run |
|---|---|---|
| **Pricing** | Always-on (~$7/month) | Pay per request (free when idle) |
| **Architecture** | Long-running server | Spins up only when needed |
| **Bot mode** | Long polling (no changes) | Requires webhook |
| **Startup time** | 30–60 seconds | 100–500ms (cold start) |

### Monthly Cost (~100 messages/day)

- **Compute Engine**: ~$7
- **Cloud Run**: < $1

### The Catch

Your bot uses **long polling** — it keeps asking Telegram "any new messages?" This works fine on Compute Engine.

But Cloud Run **doesn't allow long-lived connections**. You'd need to switch your bot to **webhook mode** (Telegram pushes messages to you). Requires code changes, but once done, costs drop to near zero.

### Which One?

**Choose Compute Engine if:**
- You want zero code changes
- You're okay paying ~$7/month for simplicity

**Choose Cloud Run if:**
- You want near-zero cost
- You're willing to spend an hour switching to webhook

### Bottom Line

- **Less work** → Compute Engine
- **Less money** → Cloud Run

For a personal low-traffic bot, Cloud Run is worth the one-time setup.

---