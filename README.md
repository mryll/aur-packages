# AUR Packages

PKGBUILDs for my AUR packages. Source of truth for packaging metadata; synced to AUR git repos.

## Packages

| Package | Description | Upstream |
|---|---|---|
| [claudebar](https://aur.archlinux.org/packages/claudebar) | Waybar widget for Claude AI usage | [source](https://github.com/mryll/claudebar) |
| [codexbar](https://aur.archlinux.org/packages/codexbar) | Waybar widget for OpenAI Codex usage | [source](https://github.com/mryll/codexbar) |
| [logibar](https://aur.archlinux.org/packages/logibar) | Waybar widgets for Logitech battery monitoring | [source](https://github.com/mryll/logibar) |
| [meteobar](https://aur.archlinux.org/packages/meteobar) | Weather widget for Waybar using Open-Meteo | [source](https://github.com/mryll/meteobar) |
| [meteobar-bin](https://aur.archlinux.org/packages/meteobar-bin) | Weather widget for Waybar (prebuilt binary) | [source](https://github.com/mryll/meteobar) |

## Workflow

```bash
# Edit PKGBUILD
vim claudebar/PKGBUILD

# Regenerate .SRCINFO
cd claudebar && makepkg --printsrcinfo > .SRCINFO && cd ..

# Commit
git add -A && git commit -m "claudebar: bump to vX.Y.Z"

# Push to AUR
cd /tmp && git clone ssh://aur@aur.archlinux.org/claudebar.git aur-tmp
cp claudebar/{PKGBUILD,.SRCINFO} /tmp/aur-tmp/
cd /tmp/aur-tmp && git add -A && git commit -m "bump to vX.Y.Z" && git push
rm -rf /tmp/aur-tmp
```
