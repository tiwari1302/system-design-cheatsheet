# System Design Patterns — Interactive Interview-Prep Guide

A single, self-contained HTML page explaining 40 system design patterns in plain
English, with everyday analogies, real-world examples, and concise, interview-ready
notes on *when to reach for each one* and the *trade-off* you accept.

The 30 patterns from the original cheatsheet, plus a **Data Platform & Pipelines**
category covering data-engineering essentials: Write-Ahead Log, Change Data Capture,
Batch Processing, Lambda/Kappa, Data Lakehouse, Columnar Storage, Transactional
Outbox, Idempotency/Exactly-Once, Schema Evolution, and Backpressure.

- **Zero dependencies** — everything (HTML, CSS, JS) is in `index.html`. Works offline.
- **Responsive** — adapts to laptop and phone; the detail view becomes a bottom sheet on mobile.
- **Interactive** — live search, category filters, tap-to-expand detail cards, keyboard navigation (← → Esc), and a light/dark theme toggle that remembers your choice.
- **Navigation drawer** — the ☰ button opens a table-of-contents listing all patterns grouped by category. Click a category to filter to it, or click a pattern to jump straight to its detail. There's also a back-to-top button.
- **Data-application focus** — the 23 patterns most central to data-intensive systems (storage, replication, partitioning, consistency, processing, and the whole Data Platform category) are marked with a ⭐ gold badge and accent. Use the **⭐ Data Apps** filter to see just those.

## View it locally

Just double-click `index.html`, or open it in any browser. That's it.

To serve it over your local network (so you can open it on your phone on the same Wi-Fi):

```bash
cd system-design-patterns
python3 -m http.server 8000
# find your laptop's IP (macOS): ipconfig getifaddr en0
# then open http://<your-laptop-ip>:8000 on your phone
```

## Deploy it (pick one — all free)

**GitHub Pages**
1. Push this folder to a GitHub repo.
2. Repo → Settings → Pages → Source: `main` branch, `/ (root)`.
3. Your page goes live at `https://<username>.github.io/<repo>/`.

**Netlify / Vercel / Cloudflare Pages (drag-and-drop)**
- Open the dashboard and drag the folder (or just `index.html`) into the deploy area.
- You get a public URL in seconds — no build step, it's a static file.

**Surge.sh**
```bash
npm install -g surge
cd system-design-patterns
surge
```

## Editing the content

All patterns live in the `PATTERNS` array near the top of the `<script>` block
in `index.html`. Each entry has `cat`, `icon`, `name`, `when`, `trade`, `whenMore`,
`tradeMore`, `explain`, `analogy`, and `example` (`when`/`trade` are the short card
labels; `whenMore`/`tradeMore` are the longer interview notes shown in the detail
view). Add `data: true` to any entry to mark it as a data pattern (gold ⭐ badge +
"Data Apps" filter). Add or edit entries there and reload — no build required.

The categories (and their colors) are defined in the `CATEGORIES` object just
above it; counts, filters, and the navigation drawer all derive automatically.
