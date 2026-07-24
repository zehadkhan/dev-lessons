# Dev Lessons

**Animated, interactive walkthroughs of the hard engineering problems every developer eventually hits.**

Most technical concepts are hard to grasp from text alone. These lessons animate the *mechanism* — data flowing, states flipping, things breaking and being fixed — so the intuition clicks. Press play and watch it happen.

Each lesson is a single self-contained HTML file. No build step, no dependencies, no framework. Open it in a browser and it just works.

## 🔗 Live site

> Enable **GitHub Pages** (Settings → Pages → Deploy from `main` / root) and your site will be live at
> `https://<your-username>.github.io/dev-lessons/`

## 📚 Lessons

| # | Lesson | Topic | Status |
|---|--------|-------|--------|
| 01 | [Zero-downtime server migration](lessons/01-zero-downtime-migration/) | DevOps | ✅ Live |
| 02 | [Idempotent payment webhooks](lessons/02-idempotent-payment-webhooks/) | Payments | ✅ Live |
| 03 | [The N+1 query, seen live](lessons/03-n-plus-one-query/) | Database | ✅ Live |

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
