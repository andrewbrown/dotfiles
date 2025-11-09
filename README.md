## Setting Up A New Machine

```
# Install Homebrew using instructions at https://brew.sh
brew install chezmoi
brew install 1password
# Open 1Password, get signed in
# Go to Settings | Developer
#   - Click "Set up the SSH Agent", click "Use Key Names", click "Edit Automatically"
#   - Under Advanced, select "Ask approval for each new <application>", "<for 24 hours>"
#   - Check "Integrate with 1Password CLI"
chezmoi init git@github.com:andrewbrown/dotfiles.git
chezmoi cd
brew bundle
```

## Restoring Preferences For Apps Once Installed

* Bartender 6 - copy prefs from `~/.dotfiles/com.surteesstudios.Bartender.plist` to `~/Library/Preferences`
* iStat Menus - restore settings from `~/.dotfiles/iStat Menus Settings.ismp7`
* iTerm2 - point to prefs in `~/.dotfiles/com.googlecode.iterm2.plist`, import profiles from `~/.dotfiles/iterm2.profiles.json`
* Path Finder - copy prefs from `~/.dotfiles/com.cocoatech.PathFinder.plist` to `~/Library/Preferences`
* Rectangle Pro - use option to sync preferences from iCloud
* The Clock - use option to restore preferences from iCloud

## Updating The List Of Apps To Install

```
chezmoi cd
brew bundle dump --file=./brewfile
git add .
git commit 
git push 
```

## Apps Not Installed Through Brew

* Homebrew
* Ledger Live
* Logi Options+
* Opal Composer (only install on computers with an Opal camera)
* Postgres.app
* ProtonVPN
* Scrypted

## TODO

* Set up miniconda
* Add more preexisting dotfiles from Mac Studio, as I discover a need for them on the laptop