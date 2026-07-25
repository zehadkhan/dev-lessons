# Dev Lessons

**Animated, interactive walkthroughs of the hard engineering problems every developer eventually hits.**

🔗 **Live site: [zehadkhan.github.io/dev-lessons](https://zehadkhan.github.io/dev-lessons/)**

Most technical concepts are hard to grasp from text alone. These lessons animate the *mechanism* — data flowing, states flipping, things breaking and being fixed — so the intuition clicks. Press play and watch it happen.

Each lesson is a single self-contained HTML file. No build step, no dependencies, no framework. Open it in a browser and it just works.

## 🔗 Live site

The site is served with **GitHub Pages** from `main` / root:

**→ [https://zehadkhan.github.io/dev-lessons/](https://zehadkhan.github.io/dev-lessons/)**

Light and dark themes are both supported — it follows your system setting, with a ☀/☾ toggle on every page.

## 📚 Lessons

| # | Lesson | Topic | Status |
|---|--------|-------|--------|
| 01 | [Zero-downtime server migration](lessons/01-zero-downtime-migration/) | DevOps | ✅ Live |
| 02 | [Idempotent payment webhooks](lessons/02-idempotent-payment-webhooks/) | Payments | ✅ Live |
| 03 | [The N+1 query, seen live](lessons/03-n-plus-one-query/) | Database | ✅ Live |
| 04 | [The inventory race condition](lessons/04-inventory-race-condition/) | Concurrency | ✅ Live |
| 05 | [The cache stampede](lessons/05-cache-stampede/) | Caching | ✅ Live |
| 06 | [What an index actually does](lessons/06-what-an-index-does/) | Database | ✅ Live |
| 07 | [Deploys that can't take the site down](lessons/07-rolling-deploys/) | DevOps | ✅ Live |
| 08 | [Read replicas and the vanishing write](lessons/08-read-replicas/) | Scaling | ✅ Live |
| 09 | [Surviving a server crash at peak traffic](lessons/09-surviving-a-server-crash/) | Reliability | ✅ Live |
| 10 | [MCP: how AI gets hands on your systems](lessons/10-mcp-model-context-protocol/) | AI Tooling | ✅ Live |

This is the beginning of a much bigger curriculum — **48 chapters across networking, backend, databases, DevOps, deployment, distributed systems and AI tooling**. See the full plan in **[ROADMAP.md](ROADMAP.md)**.

## 💡 What makes these different

- **See the motion** — animation carries intuition that static diagrams can't.
- **Real commands** — every lesson pairs the animation with the exact commands you'd run, so it doubles as a reference.
- **Failure-first** — each one shows *what breaks and why* before showing the fix.

## 🛠 Built with

Plain HTML, CSS and vanilla JavaScript. Deliberately zero-dependency so anyone can read the source, fork a lesson, and adapt it.

## 🤝 Contributing

Ideas, corrections and new lessons are welcome. Open an issue to propose a topic, or a PR with a new lesson folder following the structure of Lesson 01.

## 📄 License

[MIT](LICENSE) — free to use, adapt and share. Attribution appreciated.
