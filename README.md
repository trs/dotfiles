# dotfiles

## Installation

```bash
# Settings
DF_PATH="$HOME/dotfiles"
DF_RC="$HOME/.zshrc"
DF_VIM="$HOME/.vimrc"

# Clone repository.
git clone git@github.com:trs/dotfiles.git "$DF_PATH"

# Source `.shellrc`.
echo '
export SHELLRC_DIR='"$DF_PATH"'
[ -f "$SHELLRC_DIR/.shellrc" ] && . "$SHELLRC_DIR/.shellrc"
' >> "$DF_RC"

# Source `.vimrc`
echo '
:source $SHELLRC_DIR/.vimrc'
' >> "$DF_VIM"

# Include `git/gitconfig`.
DF_GITCONF="$HOME/.gitconfig"
[ ! -f "$DF_GITCONF" ] && touch "$DF_GITCONF"
echo '
[include]
  path = '"$DF_PATH"'/git/gitconfig
' >> "$DF_GITCONF"
```

## Aliases

Machine specific aliases can be added to a `~/.aliases` file.
