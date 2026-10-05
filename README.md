# bokyapps.github.io

Source for the BokyApps website, published with GitHub Pages at:

**https://bokyapps.github.io/**

This is the org user/organization site for the
[BokyApps](https://github.com/BokyApps) GitHub organisation. It is not an app
repository — the apps live under the
[BokyApps](https://github.com/BokyApps) organisation.

---

## What is on the site

| URL | Path | Purpose |
| --- | --- | --- |
| https://bokyapps.github.io/ | `index.html` | Landing page: Boky ethos plus a card for each app |
| https://bokyapps.github.io/apps/bokyqr/ | `apps/bokyqr/index.html` | BokyQR — offline Android QR scanner |
| https://bokyapps.github.io/apps/bokylearn/ | `apps/bokylearn/index.html` | BokyLearn — fun-fact learning app |
| https://bokyapps.github.io/apps/bokydo/ | `apps/bokydo/index.html` | BokyDo — self-hosted task manager |
| https://bokyapps.github.io/apps/bokydojo/ | `apps/bokydojo/index.html` | BokyDojo — dojo Student Information System |
| https://bokyapps.github.io/privacy/ | `privacy/index.html` | **Canonical privacy policy for all Boky apps** |
| https://bokyapps.github.io/support/ | `support/index.html` | Support the creators (placeholder payment details) |
| https://bokyapps.github.io/404.html | `404.html` | Not-found page |

Shared assets:

| Path | Purpose |
| --- | --- |
| `assets/style.css` | The entire stylesheet. Light mode by default, dark mode via `prefers-color-scheme`. |
| `assets/favicon.svg` | Local SVG favicon, also inlined in the header of each page |

### Canonical privacy URL

The privacy policy is a **directory with an `index.html`**, so the canonical URL is
exactly:

```
https://bokyapps.github.io/privacy/
```

with the trailing slash. `privacy/index.html` declares this in a `<link rel="canonical">`.
Do not add a `privacy.html` file — that would create a second, competing URL.

This page is the **canonical hosted version** of the Boky privacy policy for the whole
app family. The `PRIVACY.md` file inside the BokyQR repository mirrors it; where the two
differ, this page is the version to rely on. If you update one, update the other.

---

## The apps

These apps live in the `BokyApps` GitHub organisation. Old `github.com/sarel-myburgh/<app>`
URLs redirect to the matching `github.com/BokyApps/<app>` repository.

| App | Repository | Licence | Distribution |
| --- | --- | --- | --- |
| BokyQR | https://github.com/BokyApps/BokyQR | Apache-2.0 | Android — GitHub releases; F-Droid and Play listings "coming soon" |
| BokyLearn | https://github.com/BokyApps/BokyLearn | not declared in the repository — the page says "see repository" | Android — GitHub releases; F-Droid and Play listings "coming soon" |
| BokyDo | https://github.com/BokyApps/BokyDo | AGPL-3.0 | Self-hosted server (Docker Compose); Android app planned later |
| BokyDojo | https://github.com/BokyApps/BokyDojo | AGPL-3.0 | Self-hosted web app (Docker Compose) |

---

## Placeholders

The site deliberately contains **marked placeholders** rather than invented values. Never
put a guessed store URL, crypto address, payment handle, email address or phone number
into this repository. Fill in a real value, or leave the placeholder.

Filled:

* `support/index.html` — Ko-fi: https://ko-fi.com/bokyapps
* `support/index.html` — BTC (native SegWit): `bc1qfukuse3r0uhf6gc5zkpyxaf0snqwejrc5w9j4j`
* `support/index.html` — ETH/USDC on Base: `0xC8F53137c521F27Ff9a1D82EA8508B1c59f2EF84`
* `support/index.html` — SOL/SPL on Solana: `4EsZgfctQ45y7JX4gsNaRDkGs6MVXVMSUNwJFBzvgUNP`

Current placeholders:

* `support/index.html` — GitHub Sponsors URL,
  Lightning address or LNURL, XMR address.
* `privacy/index.html` — `[PLACEHOLDER: contact email]`.
* `support/index.html` — `[PLACEHOLDER: contact email]`.

They are styled with `.placeholder` (dashed border) and `.tag-placeholder`, and are
announced as placeholders on the page so nobody mistakes one for a live address.

---

## Design and accessibility notes

* **No build step.** Plain HTML and one CSS file. Open `index.html` and it renders.
* **No third-party anything.** No CDNs, no Google Fonts, no external JavaScript, no
  remote images, no analytics, no cookies, no trackers, no embed. Every asset is served
  from this repository.
* **System fonts only** (`-apple-system`/`Segoe UI`/`Roboto`/…), so there is no font
  request at all.
* **Dark mode is pure CSS** via `prefers-color-scheme: dark`, with a light fallback.
  There is no theme toggle and no JavaScript; the OS setting decides.
  `prefers-reduced-motion: reduce` is honoured.
* **Mobile-friendly**: responsive viewport meta, a single-column layout that expands to
  two columns at `34rem`, tables in a horizontally scrollable container so they do not
  break narrow screens.
* **Readable**: generous line height, content capped at `42rem`.
* **Accessible**: real `<a>` elements for navigation, a skip link, semantic heading
  order, `<th scope>` on every table header, visible `:focus-visible` outlines,
  `aria-current="page"` on the active nav item, `aria-label` on nav landmarks, and
  `rel="noopener"` on external links.

## How GitHub Pages is enabled

The site is plain static HTML served from the root of `main`, which is all Pages needs.

1. Go to the repository on GitHub: <https://github.com/BokyApps/bokyapps.github.io>
2. **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Branch: **`main`**, folder: **`/ (root)``.
5. Save. The first build takes a minute or two; the site is then live at
   <https://bokyapps.github.io/>.

Nothing else is required:

* No GitHub Actions workflow and no build job — Pages serves the files as they are.
* No Jekyll configuration (no `_config.yml`, no `Gemfile`). Without a `Gemfile`, Pages
  does not try to run Jekyll, so the HTML is served verbatim.
* No `CNAME` file: the site is served at the default `https://bokyapps.github.io/`
  address. Add a `CNAME` file only if a custom domain is actually configured.

### Updating the site

Edit the files, commit to `main`, push. Pages rebuilds and the change is live in about a
minute. There is nothing to rebuild locally.

Because the privacy page and the app pages repeat some content (permissions tables,
feature lists, download status), a change in one place may need the same change in
another. Search the repository for the string you are changing before you assume you have
found every occurrence.

## Licence

The site's own content and stylesheet are licensed under the
[Apache License 2.0](LICENSE), matching this repository.

The apps keep their own licences: BokyQR is Apache-2.0, BokyDo and BokyDojo are AGPL-3.0,
and BokyLearn's licence is whatever its repository declares. Linking to an app does not
relicense it.
