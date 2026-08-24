# VARETH — Player Portal

A player-facing site for a homebrew **Lancer** campaign, styled as an Atlas Corporation
contractor onboarding portal.

## Pages
| File | Contents |
|---|---|
| `index.html` | Landing / briefing, tone-setting, reading order |
| `setting.html` | The planet, its regions, Site Zero, in-fiction rumours |
| `factions.html` | Atlas, rumoured rivals, what "corporation" means in 2554 |
| `pilot-creation.html` | **The main page** — mechanical setup, backgrounds, the six integration questions, threads, party connections |
| `rules.html` | Where to get Lancer, house rules, downtime, table safety |
| `style.css` | Reference copy of the stylesheet (not linked — see below) |

**Each HTML file is fully self-contained.** The CSS is embedded in a `<style>` block in
every page, so any file works on its own — open it locally by double-clicking, email it,
drop it in Discord, or host it anywhere. No external stylesheet needs to load.

Everything here is **spoiler-free** and safe to hand to players.

## Deploying to GitHub Pages

1. Create a new repository on GitHub (public or private — Pages works with both on most plans).
2. Upload these files to the repository root, or run:
   ```bash
   git init
   git add .
   git commit -m "Vareth player portal"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
   git push -u origin main
   ```
3. In the repo: **Settings → Pages**
4. Under *Build and deployment* → *Source*, choose **Deploy from a branch**
5. Branch: `main`, folder: `/ (root)` → **Save**
6. Wait ~60 seconds. Your site will be live at
   `https://YOUR-USERNAME.github.io/YOUR-REPO/`

No build step, no dependencies, no framework. It's plain HTML and CSS.

### Custom domain (optional)
Add a file named `CNAME` containing just your domain (e.g. `vareth.example.com`),
then point a CNAME DNS record at `YOUR-USERNAME.github.io`.

## Editing

Content lives directly in the HTML — no templating, no build step.

Because the CSS is embedded in each page, **changing the palette means editing the
`:root` block at the top of all five HTML files** (or edit `style.css`, then paste it
back into each page's `<style>` block). A reference copy lives in `style.css`.

The palette variables:

```css
--bg:    #05080a;   /* near-black backdrop        */
--hud:   #5ef3e0;   /* HUD cyan — primary accent  */
--warn:  #ff9d2e;   /* amber — advisories         */
--alert: #ff4d4d;   /* red — restricted / danger  */
--ok:    #7ee787;   /* green — status nominal     */
--panel: #0b1216;   /* panel fill                 */
--line:  #1b2c33;   /* hairline borders           */
```

Fonts load from Google Fonts: **Chakra Petch** (angular technical display) and
**Share Tech Mono** (data readouts). If you'd rather they work fully offline, download
both and swap the `@import` for local `@font-face` rules.

## Design

Styled after an *Armored Core 6* mission briefing terminal: notched panel corners
(`clip-path`), cyan HUD accents, corner brackets, a live status rail, a slow scanning
sweep, CRT scanlines, and mission-parameter readouts. `prefers-reduced-motion` is
respected — the sweep and status pulse disable automatically.

## A note on the core rulebook

This site does **not** host the Lancer core book PDF, and shouldn't.

Lancer's *rules text* is released by Massif Press under Creative Commons, which is why
[COMP/CON](https://compcon.app) exists and why third-party content is legal and abundant.
The full core book — its art, layout, and setting fiction — is a commercial product.
Publicly hosting it would be redistributing someone's paid work to anyone with the URL.

Players don't need it. COMP/CON contains all the frames, weapons, systems, and talents
required to build and level a pilot, for free. If someone wants the book, send them to
[massifpress.com](https://massifpress.com).

## Credits

*Lancer* is © Massif Press. This is an unofficial, non-commercial fan campaign setting.
