# Bible in a Year — Historical Companion

A single-page, offline-friendly companion for reading the Bible in a year. It walks through all **66 books of the Protestant canon in the chronological order the events happened** — and for each book gives you:

- **Who wrote it and when** — presented in two columns side by side: the **traditional** attribution held in Jewish & Christian tradition, and the **academic / critical** view of modern scholarship. Where they agree the columns look alike; where they diverge (Genesis, Isaiah, Daniel, the Pastoral Epistles) you see both.
- **The world of the writing** — the author or community, the political moment of composition, the purpose, and how the book was transmitted.
- **The world of the events** — the geopolitical stage (Egypt, Assyria, Babylon, Persia, Rome), key rulers, daily life, customs, and the timeframe of what's being described.

It's built as **one self-contained HTML file** — no build step, no dependencies, no tracking. Open it in any browser, or host it for free on GitHub Pages.

## Features

- 📖 All 66 books in events-chronological order, grouped into 8 historical eras
- ⚖️ Traditional and academic views shown side by side for every book
- 🔍 Instant search across book names, authors, places, and empires (try `Babylon` or `Paul`)
- 🏷️ Filter by Old / New Testament
- 📑 Expand-all / collapse-all and tap-to-open cards
- 📱 Responsive and readable on phone, tablet, and desktop
- 🔌 Zero dependencies — works fully offline

## Quick start

Just open `index.html` in your browser. That's it.

Or serve it locally:

```bash
# Python
python3 -m http.server 8000
# then visit http://localhost:8000

# or Node
npx serve .
```

## Deploy to GitHub Pages

This repo includes a GitHub Actions workflow (`.github/workflows/deploy.yml`) that publishes the site automatically.

1. Push this repo to GitHub.
2. In your repo, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **GitHub Actions**.
4. Push to the `main` branch (or re-run the workflow). Your site goes live at:
   `https://<your-username>.github.io/bible-in-a-year-companion/`

## How to use it as a reading companion

Read a book's card on the day you start that book in your plan. Because the cards are ordered by *when the events happened*, the prophets sit beside the kingdom years they spoke into, Job sits beside Genesis, and the New Testament letters are slotted into the Acts timeline.

## Editing the content

All book data lives in a single JavaScript array named `BOOKS` inside `index.html`. Each entry looks like this:

```js
{
  n: "Genesis",          // book name
  t: "OT",               // "OT" or "NT"
  era: "primeval",       // matches an id in the ERAS array
  genre: "Law / Torah",
  ta: "Moses",                       // traditional author
  td: "c. 1446–1406 BC",             // traditional date
  aa: "Multiple sources (J, E, P)…", // academic author
  ad: "Sources c. 950–500 BC…",      // academic date
  wctx: ["paragraph 1…", "paragraph 2…"],  // world of the writing
  ewhen: "Events: creation to c. 1800 BC", // events timeframe label
  ectx: ["paragraph 1…", "paragraph 2…"]   // world of the events
}
```

The 8 eras are defined in the `ERAS` array just above `BOOKS`. Edit the text, refresh the page, and your changes appear — no build step required.

## A note on accuracy

Dates and authorship are scholarly approximations and are genuinely debated. This project deliberately presents **both** the traditional and the academic/critical positions rather than picking a winner, so you can weigh them yourself. It is a study aid, not a substitute for the biblical text or for deeper scholarship.

## License

- **Code** (HTML/CSS/JavaScript): [MIT](LICENSE)
- **Written content** (the historical descriptions): [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE-CONTENT.md)

You're free to use, adapt, and share both — just keep the code's MIT notice and attribute the content. See the license files for details.

## Contributing

Corrections and refinements are welcome — especially on dating, authorship nuance, and historical context. Open an issue or a pull request. Because the content tries to represent multiple scholarly views fairly, please cite a source when proposing factual changes.
