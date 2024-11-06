---
sidebar_position: 1
---

# Installation

## Prerequisites

- Make sure you have installed the latest version of [`Neovim v0.9.0+`](https://github.com/neovim/neovim/releases/latest).
- Have [`git`](https://cli.github.com/), [`make`](https://www.gnu.org/software/make/), [`pip`](https://pypi.org/project/pip/), [`python`](https://www.python.org/), [`npm`](https://npmjs.com/), [`node`](https://nodejs.org/), [`cargo`](https://www.rust-lang.org/tools/install) and [`ripgrep`](https://github.com/BurntSushi/ripgrep) installed on your system.
- [Resolve `EACCES` permissions when installing packages globally](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally) to avoid error when installing packages with npm.
- [`PowerShell 7+`](https://learn.microsoft.com/en-us/powershell/scripting/whats-new/migrating-from-windows-powershell-51-to-powershell-7?view=powershell-7.2) (for Windows).

## Optional Feature Prerequisites

- Install [`lazygit`](https://github.com/jesseduffield/lazygit#installation). This enables `<leader>gg` to launch `lazygit` for integrated and enhanced Git experience while in `lvim`.

## Release

(Neovim 0.9.5)

No alarms and No surprises:

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
<TabItem value="linux/macos" label="Linux/MacOS">

```bash
LV_BRANCH='release-1.4/neovim-0.9' bash <(curl -s https://raw.githubusercontent.com/LunarVim/LunarVim/release-1.4/neovim-0.9/utils/installer/install.sh)
```
To achieve a non-interactive installation, you can supply flags to the installer. For example, to always install dependencies, the `--install-dependencies` flag can be supplied:
```bash
LV_BRANCH='release-1.4/neovim-0.9' bash <(curl -s https://raw.githubusercontent.com/LunarVim/LunarVim/release-1.4/neovim-0.9/utils/installer/install.sh) -s -- --install-dependencies
```
A list of all installation flags can be found by supplying `-h` (or `--help`):
```bash
LV_BRANCH='release-1.4/neovim-0.9' bash <(curl -s https://raw.githubusercontent.com/LunarVim/LunarVim/release-1.4/neovim-0.9/utils/installer/install.sh) -s -- -h
```

</TabItem>
<TabItem value="windows" label="Windows">

```powershell
pwsh -c "`$LV_BRANCH='release-1.4/neovim-0.9'; iwr https://raw.githubusercontent.com/LunarVim/LunarVim/release-1.4/neovim-0.9/utils/installer/install.ps1 -UseBasicParsing | iex"
```

</TabItem>
<TabItem value="docker" label="Try it first in Docker!">

_This is intended just to take a look at the base functionalities, so some interactions may be blocked by the environment._

```bash
docker run -w /tmp -it --rm alpine:edge sh -uelic 'addgroup -S lunaruser && adduser -S lunaruser -G lunaruser --shell /bin/sh && apk add yarn git python3 cargo neovim ripgrep alpine-sdk bash curl --update && LV_BRANCH='release-1.4/neovim-0.9' su -c "bash <(curl -s https://raw.githubusercontent.com/lunarvim/lunarvim/release-1.4/neovim-0.9/utils/installer/install.sh) --no-install-dependencies" lunaruser && su -c /home/lunaruser/.local/bin/lvim lunaruser'
```

</TabItem>
</Tabs>

## Nightly

(Neovim 0.10.0)

All the new features with all the new bugs:

<Tabs>
<TabItem value="linux/macos" label="Linux/MacOS">

```bash
bash <(curl -s https://raw.githubusercontent.com/lunarvim/lunarvim/master/utils/installer/install.sh)
```
To achieve a non-interactive installation, you can supply flags to the installer. For example, to always install dependencies, the `--install-dependencies` flag can be supplied:
```bash
bash <(curl -s https://raw.githubusercontent.com/lunarvim/lunarvim/master/utils/installer/install.sh) -s -- --install-dependencies
```
A list of all installation flags can be found by supplying `-h` (or `--help`):
```bash
bash <(curl -s https://raw.githubusercontent.com/lunarvim/lunarvim/master/utils/installer/install.sh) -s -- -h
```

</TabItem>
<TabItem value="windows" label="Windows">

```powershell
pwsh -c "iwr https://raw.githubusercontent.com/LunarVim/LunarVim/master/utils/installer/install.ps1 -UseBasicParsing | iex"
```

</TabItem>
<TabItem value="docker" label="Try it first in Docker!">

_This is intended just to take a look at the base functionalities, so some interactions may be blocked by the environment._

```bash
docker run -w /root -it --rm alpine:edge sh -uelic 'apk add git neovim ripgrep alpine-sdk bash curl --update && bash <(curl -s https://raw.githubusercontent.com/lunarvim/lunarvim/master/utils/installer/install.sh) --no-install-dependencies && /root/.local/bin/lvim'
```

</TabItem>
</Tabs>

Make sure to check the [troubleshooting](../troubleshooting/README.md) section if you encounter any problem.

<iframe width="560" height="315" src="https://www.youtube.com/embed/sFA9kX-Ud_c" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="1"></iframe>

## Updating LunarVim

- Inside LunarVim `:LvimUpdate`
- From the command-line `lvim +LvimUpdate +q`

### Update the plugins

- Inside LunarVim `:LvimSyncCorePlugins`

## Uninstall

You can remove LunarVim (including the configuration files) using the bundled `uninstall` script

<Tabs>
<TabItem value="linux/macos" label="Linux/MacOs">

```bash
bash ~/.local/share/lunarvim/lvim/utils/installer/uninstall.sh
```

**or**

```bash
bash <(curl -s https://raw.githubusercontent.com/lunarvim/lunarvim/master/utils/installer/uninstall.sh)
```

</TabItem>
<TabItem value="windows" label="Windows">

```powershell
Invoke-WebRequest https://raw.githubusercontent.com/lunarvim/lunarvim/master/utils/installer/uninstall.ps1 -UseBasicParsing | Invoke-Expression
```

</TabItem>
</Tabs>
