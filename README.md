# Crimson for Omarchy

A dark-red Omarchy theme. Near-black wine-tinted surfaces, a crimson accent
used where it matters — focused borders, active bar elements, selections —
and warm, highly legible text.

![Crimson preview](preview.png)

## Palette

| Role | Color | Hex |
|---|---|---|
| Primary background | Near black | `#0B0A0C` |
| Recessed | Black | `#080708` / `#050404` |
| Raised surface | Dark wine | `#21171C` |
| Accent / Red | Crimson | `#E63950` |
| Intense red | Bright crimson | `#FF5C74` |
| Deep wine | Wine | `#761C30` (borders) |
| Selection | Dark wine | `#4A1E2A` |
| Primary text | Warm white | `#F2E8EB` |
| Secondary text | Muted rose | `#B7A2A9` |
| Muted | Grey rose | `#8A757D` |

Full ANSI set (all ≥ 4.5:1 vs background except brown, which is decorative):

- `red #E63950`, `yellow #D9A45B`, `orange #D97352`, `green #8FC38A`
- `cyan #6EC2C4`, `blue #7AA5D6`, `magenta #C48AC9`, `brown #A67C64`
- Bright variants are 20%+ toward white and visibly distinct.

Contrast (measured): foreground/background **16.5:1**, secondary **8.2:1**,
accent/background **4.8:1**, selection pairing **14.5:1**.

Window borders use a crimson gradient:

```toml
hyprland_active_border = "rgba(E63950ee) rgba(761C30ee) 45deg"
hyprland_inactive_border = "rgba(4a1e2aaa)"
```

## Wallpapers

Three original 2560×1440 wallpapers, generated for this theme, in
`backgrounds/` (cycle with `Super + Ctrl + Space`), plus the brand
`omarchy.png` (pixel wordmark in crimson, as in official themes):

| Wallpaper | Description |
|---|---|
| ![Crimson Minimal](backgrounds/001-crimson-minimal.png) `001-crimson-minimal.png` | Near-black, thin crimson horizon line, ring + dot motif |
| ![Crimson Night](backgrounds/002-crimson-night.jpg) `002-crimson-night.jpg` | Nocturnal gradient, crimson moon with glow, ridge line, stars |
| ![Crimson Abstract](backgrounds/003-crimson-abstract.jpg) `003-crimson-abstract.jpg` | Diagonal wine bands, soft glows, bezier lines |
| ![Omarchy brand](backgrounds/omarchy.png) `omarchy.png` | Official pixel wordmark tinted crimson on near-black (3840×2160) |

All files are under ~150 KB. No third-party images, no redistribution issues.

## Compatibility

- Omarchy **4.x** (tested on `4.0.4-1` and `4.0.5-1`). Requires the
  `colors.toml` theme system with `mode`, template expansion and
  `hypr_gradient` support.
- Everything is derived from `colors.toml` through Omarchy's built-in
  templates: Hyprland borders, shell (bar, menus, launcher, notifications,
  OSD, lock), Alacritty/Foot/Ghostty/Kitty, btop, Chromium, Neovim (aether),
  Helix, VS Code theme, Obsidian, Claude/Pi/Hermes/T3Code, keyboard RGB.
- The repo ships **no** `.lua`, terminal configs or `vscode.json`, since
  those are dropped for git-installed themes and regenerated locally.
  The theme looks correct from `colors.toml` alone.
- Icons: `Yaru-red`. Keyboard backlight: crimson `e63950`.

## Installation

```bash
omarchy theme install https://github.com/PedroAugustoOK/omarchy-crimson-theme.git
```

This clones to `~/.config/omarchy/themes/crimson` and applies it immediately.
(Menu path: `Install > Style > Theme`.)

## Activation

```bash
omarchy theme list       # confirm `crimson` is listed
omarchy theme set crimson
omarchy theme current    # should print `Crimson`
omarchy theme bg next    # cycle the three wallpapers
```

Preview the palette without applying:

```bash
omarchy dev theme-preview crimson
```

## Update and removal

```bash
omarchy theme update          # pull latest for all git-installed themes
omarchy theme refresh         # re-apply the current theme after an Omarchy upgrade
omarchy theme remove crimson  # delete the local clone
```

After `omarchy update` brings new Omarchy versions, run
`omarchy theme refresh` once so your staged configs are generated with the
current templates.

To restore your previous theme: `omarchy theme set "<name>"`
(see `omarchy theme list`).

## Optional extras (machine-local, not part of the theme)

- **Plymouth boot screen** — apply Crimson to the boot/login screen:

  ```bash
  omarchy-plymouth-set-by-theme crimson   # uses unlock.png + palette (asks for sudo)
  omarchy plymouth preview '#0B0A0C' '#F2E8EB' ~/.config/omarchy/themes/crimson/unlock.png /tmp/crimson-boot.png
  ```

  The preview command leaves an `imv` window open showing the render — close
  it to finish. Reset with `omarchy plymouth reset` or pick another theme's
  boot screen under `Style > Unlock`.
- **OWE wallpaper engine** (`omarchy pkg add owe`) can play animated
  backgrounds/intros from themes. Crimson ships static wallpapers only;
  see `RESEARCH.md §11` for the intro-vs-OWE status.

## Repository structure

```text
omarchy-crimson-theme/
├── colors.toml          # the palette — the only required file
├── backgrounds/         # 3 original wallpapers + brand omarchy.png
├── icons.theme          # Yaru-red
├── keyboard.rgb         # e63950
├── preview.png          # 1800×1012 theme-picker thumbnail
├── unlock.png           # transparent lock-screen art
├── preview-unlock.png   # 1920×1080 lock preview (Style > Unlock)
├── README.md
├── RESEARCH.md          # how Omarchy theming was verified
├── LICENSE
└── .gitignore
```

## Credits and license

- Theme, palette and all wallpapers: original work for this repository,
  generated programmatically with ImageMagick. No third-party assets.
- Palette: MIT (see `LICENSE`; covers `colors.toml` and config files).
- Wallpapers/previews: same MIT license (original works, no attribution
  required).
- Built for [Omarchy](https://omarchy.org) (`basecamp/omarchy`).
  Icon set names belong to Yaru; font rendering in previews uses system fonts.
