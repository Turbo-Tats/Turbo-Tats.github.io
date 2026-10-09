# turbotats.com

Tatiana Crawford's portfolio site. GitHub Pages serves the `main` branch at https://www.turbotats.com (set by `CNAME`). It's a static site with no build step: a push to `main` goes live in about a minute.

## Files

- `index.html`: the whole site. CSS design tokens at the top, page sections in the middle, and the knowledge-graph script at the bottom.
- `404.html`: the "That page moved" page for old links. Keep its colors in step with `index.html`.
- `CNAME`: `www.turbotats.com`. Don't change it.
- `CLAUDE.local.md` and `private/` exist only on Tatiana's machine (gitignored). They hold her private career context. See "Source of truth."

## Page structure (`index.html`)

Sections, in order, by `id`: `top` (hero), `work` (case studies), `side` (side projects), `approach` (how I work), `experience`, `coverage`, `contact`.

- **Case study:** an `<article class="case">` with a `.body` (eyebrow label, `h3` title, problem paragraph, decision bullets, a `.role` "My role" line) and a `.readout` results panel (`.metric` rows: a short `<b>` figure plus a `<span>` label). Keep figures short enough to fit, like `99%`, `6 wks`, or `10 → 3`.
- **Domains:** `.chip` tags in the hero.
- **Graph:** the `nodes` and `edges` arrays in the bottom script. `kind` is `core`, `skill`, or `project`. When you add a node, check that its label doesn't overlap a neighbor's.

## Design rules

- Use the color tokens in `:root`. Every token has dark-mode values in both dark blocks (`prefers-color-scheme` and `[data-theme="dark"]`), so add any new token to all three places.
- Fonts: Bricolage Grotesque (display), IBM Plex Sans (body), IBM Plex Mono (labels and figures). No new libraries or frameworks.
- The page must work at 400px wide with no sideways scrolling. Check desktop and phone widths before committing.

## Copy rules

- **Positioning:** data and integrations first, then the AI built on top of them.
- **Voice:** plain, specific, active. Short sentences. No em-dash asides, no "not X but Y," no buzzwords.
- **Credit precisely.** Every "My role" line says what Tatiana did and what engineering or colleagues did. Never upgrade "led" to "built."
- **Public-page rules:**
  - No contract values or revenue figures.
  - Name only customers whose partnership with Novi is public (Ulta, Sephora, Target, Grove). The categorization customer stays unnamed.
  - Anything from the grocery-pricing study is simulated until real data exists. Never present it as a finding.

## Source of truth

Before any copy change, read `private/Tatiana_Crawford_Career_Source.md` if it exists. It holds the verified facts, metrics, and guardrails, and it wins over anything in `index.html`. Never copy private details from it into the site (phone number, dollar values, internal notes), and never commit anything from `private/`.

## Workflow

1. Edit `index.html`.
2. Open it in a browser at desktop and phone widths.
3. Commit with a clear message and push to `main`.
