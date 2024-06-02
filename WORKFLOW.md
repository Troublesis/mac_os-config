# My Workflow

## MacOS System Settings

### Trackpad

> Trackpad Speed - max Fast
> Lookup & data detectors - Tap with Three Fingers
> Tap to click - on

#### More Gestures

> Notification Center - off

### Keyboard

### Use trackpad for dragging


## Install [Homebrew](https://brew.sh)

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

`brew install zsh && sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`

`brew install arc`

`brew install bitwarden`

`brew install git`

`brew install raycast`

`brew install cleanshot`

`brew install mas`

`brew install stow`

## ARC Hotkey

> `New Tab - ALT + SPACE`

> `View Library - remove`

## [MacOS CLI Setup](https://github.com/Troublesis/mac_os-config/blob/main/bin/install_defaults)

```
printf "%s\n" "System - Reveal IP address, hostname, OS version, etc. when clicking login window clock."
sudo defaults write /Library/Preferences/com.apple.loginwindow AdminHostInfo HostName

printf "%s\n" "System - Disable launching of previously open applications upon reboot."
defaults write -g ApplePersistence -bool no

printf "%s\n" "System - Expand save panel by default."
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool true

printf "%s\n" "System - Disable 'Are you sure you want to open this application?' dialog."
defaults write com.apple.LaunchServices LSQuarantine -bool false

printf "%s\n" "System - Disable auto-correct."
defaults write NSGlobalDomain NSAutomaticSpellingCorrectionEnabled -bool false

printf "%s\n" "System - Disable smart quotes (not useful when writing code)."
defaults write NSGlobalDomain NSAutomaticQuoteSubstitutionEnabled -bool false

printf "%s\n" "System - Disable smart dashes (not useful when writing code)."
defaults write NSGlobalDomain NSAutomaticDashSubstitutionEnabled -bool false

printf "%s\n" "System - Require password immediately after sleep or screen saver begins."
defaults write com.apple.screensaver askForPassword -int 1
defaults write com.apple.screensaver askForPasswordDelay -int 0

printf "%s\n" "System - Avoid creating .DS_Store files on network volumes."
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true

printf "%s\n" "System - Automatically restart if system freezes."
systemsetup -setrestartfreeze on

printf "%s\n" "System - Disable software updates."
sudo softwareupdate --schedule off

printf "%s\n" "Keyboard - Automatically illuminate built-in MacBook keyboard in low light."
defaults write com.apple.BezelServices kDim -bool true

printf "%s\n" "Keyboard - Turn off keyboard illumination when computer is not used for 5 minutes."
defaults write com.apple.BezelServices kDimTime -int 300

printf "%s\n" "Keyboard - Enable keyboard access for all controls."
defaults write NSGlobalDomain AppleKeyboardUIMode -int 3

printf "%s\n" "Keyboard - Disable press-and-hold for keys in favor of key repeat."
defaults write NSGlobalDomain ApplePressAndHoldEnabled -bool false

printf "%s\n" "Trackpad - Map bottom right corner to right-click."
defaults write com.apple.driver.AppleBluetoothMultitouch.trackpad TrackpadCornerSecondaryClick -int 2
defaults write com.apple.driver.AppleBluetoothMultitouch.trackpad TrackpadRightClick -bool true
defaults -currentHost write NSGlobalDomain com.apple.trackpad.trackpadCornerClickBehavior -int 1
defaults -currentHost write NSGlobalDomain com.apple.trackpad.enableSecondaryClick -bool true

printf "%s\n" "Trackpad - Enable tap to click for current user and the login screen."
defaults write com.apple.driver.AppleBluetoothMultitouch.trackpad Clicking -bool true
defaults -currentHost write NSGlobalDomain com.apple.mouse.tapBehavior -int 1
defaults write NSGlobalDomain com.apple.mouse.tapBehavior -int 1

printf "%s\n" "Trackpad - Follow keyboard focus while zoomed in."
defaults write com.apple.universalaccess closeViewZoomFollowsFocus -bool true

defaults write com.apple.systemuiserver menuExtras -array \
  "/System/Library/CoreServices/Menu Extras/Bluetooth.menu" \
  "/System/Library/CoreServices/Menu Extras/AirPort.menu"

printf "%s\n" "Dock - Remove all default app icons."
defaults write com.apple.dock persistent-apps -array

printf "%s\n" "Dock - Automatically hide and show."
defaults write com.apple.dock autohide -bool true

printf "%s\n" "Dock - Remove the auto-hiding delay."
defaults write com.apple.Dock autohide-delay -float 0

printf "%s\n" "Dock - Don’t show Dashboard as a Space."
defaults write com.apple.dock "dashboard-in-overlay" -bool true

printf "%s\n" "iCloud - Save to disk by default."
defaults write NSGlobalDomain NSDocumentSaveNewDocumentsToCloud -bool false

printf "%s\n" "Finder - Show the $HOME/Library folder."
chflags nohidden $HOME/Library

printf "%s\n" "Finder - Show hidden files."
defaults write com.apple.finder AppleShowAllFiles -bool true

printf "%s\n" "Finder - Show filename extensions."
defaults write NSGlobalDomain AppleShowAllExtensions -bool true

printf "%s\n" "Finder - Disable the warning when changing a file extension."
defaults write com.apple.finder FXEnableExtensionChangeWarning -bool false

printf "%s\n" "Finder - Show path bar."
defaults write com.apple.finder ShowPathbar -bool true

printf "%s\n" "Finder - Show status bar."
defaults write com.apple.finder ShowStatusBar -bool true

printf "%s\n" "Finder - Display full POSIX path as window title."
defaults write com.apple.finder _FXShowPosixPathInTitle -bool true

printf "%s\n" "Finder - Use list view in all Finder windows."
defaults write com.apple.finder FXPreferredViewStyle -string "Nlsv"

printf "%s\n" "Finder - Allow quitting via COMMAND+Q -- Doing so will also hide desktop icons."
defaults write com.apple.finder QuitMenuItem -bool true

printf "%s\n" "Finder - Disable the warning before emptying the Trash."
defaults write com.apple.finder WarnOnEmptyTrash -bool false

printf "%s\n" "Finder - Allow text selection in Quick Look."
defaults write com.apple.finder QLEnableTextSelection -bool true

printf "%s\n" "Safari - Set home page to 'about:blank' for faster loading."
defaults write com.apple.Safari HomePage -string "about:blank"

printf "%s\n" "Safari - Hide bookmarks bar."
defaults write com.apple.Safari ShowFavoritesBar -bool false

printf "%s\n" "Safari - Use Contains instead of Starts With in search banners."
defaults write com.apple.Safari FindOnPageMatchesWordStartsOnly -bool false

printf "%s\n" "Safari - Enable debug menu."
defaults write com.apple.Safari IncludeInternalDebugMenu -bool true

printf "%s\n" "Safari - Enable the Develop menu and the Web Inspector."
defaults write com.apple.Safari IncludeDevelopMenu -bool true
defaults write com.apple.Safari WebKitDeveloperExtrasEnabledPreferenceKey -bool true
defaults write com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2DeveloperExtrasEnabled -bool true

printf "%s\n" "Safari - Add a context menu item for showing the Web Inspector in web views."
defaults write NSGlobalDomain WebKitDeveloperExtras -bool true

printf "%s\n" "Safari - Disable sending search queries to Apple.."
defaults write com.apple.Safari UniversalSearchEnabled -bool false

printf "%s\n" "Mail - Copy email addresses as 'foo@example.com' instead of 'Foo Bar <foo@example.com>'."
defaults write com.apple.mail AddressesIncludeNameOnPasteboard -bool false

printf "%s\n" "Mail - Disable send animation."
defaults write com.apple.mail DisableSendAnimations -bool true

printf "%s\n" "Mail - Disable reply animation."
defaults write com.apple.mail DisableReplyAnimations -bool true

printf "%s\n" "Mail - Enable COMMAND+ENTER to send mail."
defaults write com.apple.mail NSUserKeyEquivalents -dict-add "Send" -string "@\\U21a9"

printf "%s\n" "Address Book - Enable debug menu."
defaults write com.apple.addressbook ABShowDebugMenu -bool true

printf "%s\n" "iCal - Enable debug menu."
defaults write com.apple.iCal IncludeDebugMenu -bool true

printf "%s\n" "TextEdit - Use plain text mode for new documents."
defaults write com.apple.TextEdit RichText -int 0

printf "%s\n" "TextEdit - Open and save files as UTF-8 encoding."
defaults write com.apple.TextEdit PlainTextEncoding -int 4
defaults write com.apple.TextEdit PlainTextEncodingForWrite -int 4

printf "%s\n" "Disk Utility - Enable debug menu."
defaults write com.apple.DiskUtility DUDebugMenuEnabled -bool true
defaults write com.apple.DiskUtility advanced-image-options -bool true

printf "%s\n" "Time Machine - Prevent prompting to use new hard drives as backup volume."
defaults write com.apple.TimeMachine DoNotOfferNewDisksForBackup -bool true

printf "%s\n" "Printer - Expand print panel by default."
defaults write NSGlobalDomain PMPrintingExpandedStateForPrint -bool true

printf "%s\n" "Printer - Automatically quit printer app once the print jobs complete."
defaults write com.apple.print.PrintingPrefs "Quit When Finished" -bool true

printf "%s\n" "Game Center - Disable Game Center."
defaults write com.apple.gamed Disabled -bool true

printf "%s\n" "App Store - Enable the WebKit Developer Tools in the Mac App Store."
defaults write com.apple.appstore WebKitDeveloperExtras -bool true

printf "%s\n" "App Store - Enable Debug Menu in the Mac App Store."
defaults write com.apple.appstore ShowDebugMenu -bool true
```

## [Install App Store App](https://github.com/Troublesis/mac_os-config/blob/main/bin/install_app_store)

### [Amphetamine](https://apps.apple.com/us/app/amphetamine/id937984704)
mas install 937984704

### Keynote
mas install 409183694

### Numbers
mas install 409203825

### Pages
mas install 409201541

---

## [Dotfile Setup](https://github.com/Troublesis/dotfile)

`ssh-keygen -t ed25519 -C "bamboo5320@gmail.com"`

`cat ~/.ssh/id_ed25519.pub`

> [Create new github ssh key](https://github.com/settings/keys)

`git clone git@github.com:Troublesis/dotfile.git ~/.config`

---

## Restore Raycast

## Stow

`stow . || stow --adopt .`

## Install pyenv fzf and zoxide

`brew install pyenv fzf zoxide`

## Alacritty

`brew install --cask font-meslo-lg-nerd-font`

`brew install --cask alacritty`

## tmux

`brew install tmux`

`git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm`

> `ctrl + b` `shift + I`

## Neovim

`brew install neovim`

## reload ./zshrc file

`vi ~/.zshrc`

> cp reload .zshrc file

`source ~/.zshrc`

## Sublime Text

`brew install sublime-text`

`cd ~/Library/Application \Support/Sublime \Text`

`git init && git remote set-url origin https://github.com/Troublesis/sublime.git`

`git remote -v`

`git pull origin main`

> ??? `git branch --set-upstream-to=origin/main main`

## Chrome Extention

[Notion Web Clipper](https://chromewebstore.google.com/detail/ldmmifpegigmeammaeckplhnjbbpccmm)

[Notion Web Clipper]https://chromewebstore.google.com/detail/notion-web-clipper/knheggckgoiihginacbkhaalnibhilkk

[Menu Fish](https://chromewebstore.google.com/detail/menu-fish/ocdigobahepkapkegppnioklpjgbppok)

[JSON Formatter](https://chromewebstore.google.com/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa)

[Absolute Enable Right Click & Copy](https://chromewebstore.google.com/detail/absolute-enable-right-cli/jdocbkpgdakpekjlhemmfcncgdjeiika)

[Tampermonkey](https://chromewebstore.google.com/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo)
