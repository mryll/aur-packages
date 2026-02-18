# AUR Packages

PKGBUILDs for my AUR packages. Source of truth for packaging metadata; synced to AUR git repos.

## Packages

| Package | Description | Upstream |
|---|---|---|
| [waybar-claude-usage](https://aur.archlinux.org/packages/waybar-claude-usage) | Waybar widget for Claude AI usage | [source](https://github.com/mryll/waybar-claude-usage) |
| [waybar-codex-usage](https://aur.archlinux.org/packages/waybar-codex-usage) | Waybar widget for OpenAI Codex usage | [source](https://github.com/mryll/waybar-codex-usage) |
| [waybar-logitech-battery](https://aur.archlinux.org/packages/waybar-logitech-battery) | Waybar widgets for Logitech battery monitoring | [source](https://github.com/mryll/waybar-logitech-battery) |

## Workflow

```bash
# Edit PKGBUILD
vim waybar-claude-usage/PKGBUILD

# Regenerate .SRCINFO
cd waybar-claude-usage && makepkg --printsrcinfo > .SRCINFO && cd ..

# Commit
git add -A && git commit -m "waybar-claude-usage: bump to vX.Y.Z"

# Push to AUR
cd /tmp && git clone ssh://aur@aur.archlinux.org/waybar-claude-usage.git aur-tmp
cp waybar-claude-usage/{PKGBUILD,.SRCINFO} /tmp/aur-tmp/
cd /tmp/aur-tmp && git add -A && git commit -m "bump to vX.Y.Z" && git push
rm -rf /tmp/aur-tmp
```
