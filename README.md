# shadiossamamain-rgb.github.io

Personal portfolio — one hand-written page. No framework, no build step, no dependencies.

**Live URL (once published):** https://shadiossamamain-rgb.github.io

## Layout

```
index.html     the entire site — HTML, CSS and JS in one file
.nojekyll      tells GitHub Pages to serve the files as written
assets/        portrait.jpg and CV.pdf go here (both optional)
```

## Editing

Open `index.html` and edit it. There is nothing to compile and nothing to install.

The design is token-driven — every colour and typeface is a CSS custom property in the `:root` block at the top of the `<style>` tag. Change a token there and it changes everywhere:

| Token | Value | Role |
|---|---|---|
| `--paper` | `#EDE3D1` | Page ground |
| `--paper-2` | `#F7F1E6` | Cards and form fields |
| `--wine` | `#5A1020` | Display ink, and the ground for the Skills field + footer |
| `--wine-2` | `#8C1D31` | Links and active states |
| `--ink` | `#2A1C18` | Body text |
| `--muted` | `#6E5B4C` | Secondary text |

Type is Fraunces (display), Archivo (body), Space Mono (labels and counts), loaded from Google Fonts.

## Publishing

The repo name **must** be `shadiossamamain-rgb.github.io` exactly — that is what makes GitHub serve it as a user site from the repo root.

```bash
git push -u origin main
```

Then in the repo's **Settings → Pages**, set the source to the `main` branch, root folder. First build takes a minute or two.

## Still to fill in

- [ ] **Contact form** — the `action` on `#contact-form` is `https://formspree.io/f/YOUR_FORM_ID`. Create a free endpoint at [formspree.io](https://formspree.io) and paste it in. Until then the form stays inert and says so; the *Email me* link is the working path.
- [ ] **LinkedIn** — commented out in the Contact section. Uncomment and replace `YOUR_HANDLE`.
- [ ] **CV** — commented out. Drop the PDF at `assets/CV.pdf` and uncomment.
- [ ] **Portrait** — optional. Drop a photo at `assets/portrait.jpg`; a JS probe loads it and hides the monogram only if it resolves, so the page is correct either way.
- [ ] **University** — the education entry reads "In progress". Add the institution once it's decided.

## Check before publishing

The stat rows and the per-project numbers were derived from build records, not typed in by hand. Read them once — `08` projects, `175` pages of notes, `04` languages, and each card's receipts line — and confirm they're accurate before the page is public.

## Notes

- Google Fonts is the only external request. Everything else is inline.
- Verified with no horizontal overflow at 1280px and 375px; contrast measures 9.3:1 for body text and 7.8:1 for headings on the burgundy field.
- Two layout traps are commented in the source: grid children default to `min-width:auto` (which lets the project deck push the page wide), and `.card { display:flex }` outranks the browser's `[hidden] { display:none }` (which breaks the filter).
