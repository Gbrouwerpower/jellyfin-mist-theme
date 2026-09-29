# Mist — a pastel-blue theme for Jellyfin

A refined, accessible custom-CSS theme for **Jellyfin Web 12.x** (it also works on 10.11): deep blue-slate surfaces, soft pastel-blue accents, the **Figtree** typeface, and a layout tuned for both desktop browsers and the **Xbox / TV** client.

## Install

1. In Jellyfin, open **Dashboard → Branding → Custom CSS** (server-wide), or **Settings → Display → Custom CSS** (just your account).
2. Remove any other theme already in that box.
3. Paste this line:

   ```css
   @import url("https://gbrouwerpower.github.io/jellyfin-mist-theme/mist.css");
   ```

4. Save, then hard-refresh the browser (or restart the Xbox app).
5. Set each client's **Theme** to *Dark*.

The import follows the `main` branch, so you get updates automatically: GitHub Pages publishes each push within a couple of minutes, and browsers check for a new copy every 10 minutes. To pin a version or tweak the theme yourself, paste the full contents of [`mist.css`](mist.css) instead.

### Branches

| Branch | Use it for |
| --- | --- |
| `main` | Everyone. Only tested changes land here. |
| `testing` | Work in progress; may break. Import `https://gbrouwerpower.github.io/jellyfin-mist-theme/testing/mist.css` instead. |

To see a push right away instead of waiting up to 10 minutes, hard-refresh Jellyfin once the push's **Publish to GitHub Pages** run on the Actions tab has finished.

The older jsDelivr imports (`https://cdn.jsdelivr.net/gh/Gbrouwerpower/jellyfin-mist-theme@main/mist.css`) still work, but browsers may keep an old copy for up to 7 days.

## What it does

**Look**
- Blue-slate background with pastel sky and periwinkle accents, set through Jellyfin 12's own colour variables so menus, forms and dialogs match.
- Figtree typeface with readable line lengths and tabular numbers.
- Clean rounded posters, with the watched badge and progress bar clipped inside the corner.
- A consistent page gutter and spacing scale, so rows and titles share one left edge.
- Soft rounded audio and subtitle pickers.

**Movie and show pages** (desktop and TV)
- The poster is sized to fit the first screen, with the title aligned to its top edge.
- Info, audio/subtitles and the description sit beside the poster.
- Play and the buttons beside it are round, icon-only circles.
- Shows keep Next Up, Seasons and the Episodes list beside the description.
- Cast & Crew, More Like This and other rows start just below the fold, full width.
- Tags and credits move to the very bottom, so there are fewer controller stops.
- On desktop, the title logo is centred in the backdrop, and the header turns see-through so the backdrop runs to the top of the screen.

**Desktop**
- Borrows the TV look: slightly larger text, a solid header, pill-shaped navigation, and roomier spacing.
- Hovering a poster shows the same sky ring as TV focus, and hovered buttons fill with sky blue.

**TV / Xbox**
- Even margins on every side and a tidy one-row header. If your TV crops the edges, set its picture size to *Just Scan*, *Screen Fit* or *Fit to Screen* (the name varies by brand).
- A bold, unambiguous focus: a pastel ring on posters, and a white ring on buttons.
- Fixes for the Xbox app's no-animation focus band and the seek-bar focus box.
- A slimmer video-player overlay.
- No scrollbars or blur effects, for smoother performance on TV hardware.

**Accessibility**
- Text contrast is WCAG AAA: body text about 16:1, secondary text about 8.9:1, and the accent about 10.6:1 against the background.
- Always-visible keyboard and remote focus.
- Respects the *reduce motion* and *more contrast* system settings.

## Customising

The variables at the top of `mist.css` control the look:

| Variable | What it changes |
| --- | --- |
| `--mist-sky`, `--mist-periwinkle` | Accent colours |
| `--mist-bg`, `--mist-surface*` | Background and surfaces |
| `--mist-edge` | Margin around the page on TV and desktop (sides, and above and below the poster on movie pages) |
| `--mist-card-gap` | Space between posters |
| `--mist-radius` | Poster corner roundness |

## Notes

- Since Jellyfin 10.11, the admin **Dashboard** ignores custom CSS, so the theme styles the main app, the login screen and the player.
- The font loads from Google Fonts. On an offline or LAN-only server, the theme falls back to Noto Sans.
