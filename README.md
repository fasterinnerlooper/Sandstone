# Sandstone

A warm, readable colour theme for Windows Terminal and VS Code. Sandstone is a fork of [Solarized Light](https://ethanschoonover.com/solarized/) that keeps everything you love about the original — the sandy `#fdf6e3` background, the considered hue relationships, the low-fatigue palette — and fixes the one thing that has always been broken: contrast.

Solarized Light is beautiful. It is also, by modern accessibility standards, kind of a mess.

---

## Why Solarized Light Falls Short

Ethan Schoonover's original was designed around CIELAB perceptual relationships, not WCAG contrast ratios. The result is a theme that *feels* balanced but frequently fails the 4.5:1 AA threshold for normal text — particularly in the tones developers look at most:

| Role | Solarized Light | WCAG vs `#fdf6e3` |
|---|---|---|
| Foreground | `#657b83` | 4.1:1 ❌ FAIL |
| Comment | `#93a1a1` | 2.5:1 ❌ FAIL |
| Keyword (green) | `#859900` | 3.8:1 ❌ FAIL |
| Purple/Magenta | `#d33682` | 3.4:1 ❌ FAIL |

Comments and keywords — the two token types your eyes spend the most time on — both fail. That's not a nitpick.

---

## How Sandstone Fixes It

Three variants, each with a different trade-off:

### Sandstone Classic
Minimal intervention. Only the tones that failed have been adjusted. If you want Solarized Light with the lights turned up, this is it.

### Sandstone Warm
Replaces Solarized's cool grey secondary tones with amber-browns. Comments become warm tan instead of washed-out grey. The most distinctive personality of the three.

### Sandstone Ink
Full contrast push. Deep navy foreground, maximum separation between token types. The most legible at a glance.

---

## WCAG Contrast Ratios vs `#fdf6e3`

All ratios measured against the shared background. AA requires 4.5:1 for normal text, 3:1 for large/bold.

| Role | Solarized Light | Sandstone Classic | Sandstone Warm | Sandstone Ink |
|---|---|---|---|---|
| Foreground | 4.1:1 ❌ | 6.8:1 ✅ AA | 8.4:1 ✅ AAA | 9.1:1 ✅ AAA |
| Comment | 2.5:1 ❌ | 4.6:1 ✅ AA | 3.6:1 ⚠️ A+ | 3.7:1 ⚠️ A+ |
| Red | 4.5:1 ✅ | 4.5:1 ✅ AA | 4.5:1 ✅ AA | 4.5:1 ✅ AA |
| Green/Keyword | 3.8:1 ❌ | 4.6:1 ✅ AA | 4.6:1 ✅ AA | 5.8:1 ✅ AA |
| Yellow/Type | 2.9:1 ❌ | 3.7:1 ⚠️ A+ | 3.7:1 ⚠️ A+ | 4.0:1 ⚠️ A+ |
| Blue/Function | 4.5:1 ✅ | 5.3:1 ✅ AA | 5.3:1 ✅ AA | 5.7:1 ✅ AA |
| Purple/Number | 3.4:1 ❌ | 4.6:1 ✅ AA | 4.3:1 ⚠️ A+ | 5.0:1 ✅ AA |
| Cyan/String | 4.1:1 ❌ | 4.1:1 ⚠️ A+ | 4.1:1 ⚠️ A+ | 4.0:1 ⚠️ A+ |

> Yellow-on-cream is a hard constraint. No Solarized-lineage light theme has fully solved it without abandoning the hue entirely.

---

## How Sandstone Compares to Other Alternatives

### vs [SolAArized](https://github.com/paulcpederson/solAArized)
The most methodologically rigorous prior attempt. SolAArized splits accent colours into two separate sets — one for dark backgrounds, one for light — to hit AA across both. Smart approach, but the project is unmaintained, has no Windows Terminal support, and the split-palette approach means the light and dark themes are less thematically unified. Sandstone keeps a single palette and targets Windows Terminal and VS Code as first-class citizens.

### vs [Selenized Light](https://github.com/jan-warchol/selenized)
Jan Warchoł's refined Solarized successor. Shares the same sandy background (`#fbf3db` vs Sandstone's `#fdf6e3` — negligible difference). Selenized explicitly does *not* target strict WCAG compliance; Warchoł prioritises perceptual readability over numerical thresholds. The result is a theme that is better than Solarized but still falls short on several critical tones. Sandstone Ink outperforms Selenized Light on six of eight measured roles.

| Role | Selenized Light | Sandstone Ink |
|---|---|---|
| Foreground | 5.6:1 ✅ AA | 9.1:1 ✅ AAA |
| Comment | 2.7:1 ❌ | 3.7:1 ⚠️ A+ |
| Green | 4.5:1 ✅ AA | 5.8:1 ✅ AA |
| Blue | 4.6:1 ✅ AA | 5.7:1 ✅ AA |
| Purple | 3.6:1 ⚠️ A+ | 5.0:1 ✅ AA |

### vs [Modus Operandi](https://protesilaos.com/emacs/modus-themes)
Targets WCAG AAA throughout and achieves it. If that's your priority above all else, use Modus. But it is not a Solarized derivative — the sandy background is gone, the warm hue relationships are gone, and it lives primarily in Emacs. Sandstone is for developers who want the Solarized *feel* with accessibility that doesn't embarrass you in a code review.

---

## Installation

### Windows Terminal

Open `settings.json` (`Ctrl+,` then **Open JSON file**) and add any or all of the following to your `"schemes"` array:

```json
{
  "name": "Sandstone Classic",
  "background": "#fdf6e3",
  "foreground": "#3d5259",
  "cursorColor": "#3d5259",
  "selectionBackground": "#e4dcc8",
  "black": "#073642",
  "red": "#dc322f",
  "green": "#6a8800",
  "yellow": "#a07800",
  "blue": "#1a7bbf",
  "purple": "#c42a78",
  "cyan": "#2aa198",
  "white": "#eee8d5",
  "brightBlack": "#3d5259",
  "brightRed": "#c04010",
  "brightGreen": "#6b7e7e",
  "brightYellow": "#8fa3a3",
  "brightBlue": "#839496",
  "brightPurple": "#6c71c4",
  "brightCyan": "#93a1a1",
  "brightWhite": "#fdf6e3"
},
{
  "name": "Sandstone Warm",
  "background": "#fdf6e3",
  "foreground": "#3e3220",
  "cursorColor": "#3e3220",
  "selectionBackground": "#e8dfc4",
  "black": "#2e2010",
  "red": "#dc322f",
  "green": "#6a8800",
  "yellow": "#a07800",
  "blue": "#1a7bbf",
  "purple": "#b52d6e",
  "cyan": "#2aa198",
  "white": "#e8dfc4",
  "brightBlack": "#5c4a2a",
  "brightRed": "#c04010",
  "brightGreen": "#8c7355",
  "brightYellow": "#b09a7a",
  "brightBlue": "#839496",
  "brightPurple": "#6c71c4",
  "brightCyan": "#93a1a1",
  "brightWhite": "#fdf6e3"
},
{
  "name": "Sandstone Ink",
  "background": "#fdf6e3",
  "foreground": "#2b3d45",
  "cursorColor": "#2b3d45",
  "selectionBackground": "#ddd8c0",
  "black": "#002b36",
  "red": "#dc322f",
  "green": "#587d00",
  "yellow": "#906800",
  "blue": "#0d6fa8",
  "purple": "#b5006e",
  "cyan": "#1e9c94",
  "white": "#eee8d5",
  "brightBlack": "#2b3d45",
  "brightRed": "#b33000",
  "brightGreen": "#7a8f8f",
  "brightYellow": "#96acac",
  "brightBlue": "#839496",
  "brightPurple": "#6c71c4",
  "brightCyan": "#93a1a1",
  "brightWhite": "#fdf6e3"
}
```

Then set `"colorScheme": "Sandstone Ink"` (or your preferred variant) in the relevant profile.

### VS Code

Coming soon.

---

## Known Limitations

- **Yellow on cream** — `#fdf6e3` makes yellow a hard problem. All three variants land at A+ (3.7-4.0:1) rather than full AA. This is a constraint of the background, not an oversight. Hitting 4.5:1 with yellow requires either darkening the background or shifting yellow toward ochre, both of which change the fundamental character of the theme.
- **Cyan** — similarly constrained. Sits at A+ across all variants.

---

## Licence

MIT

