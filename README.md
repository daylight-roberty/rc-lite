# rc-lite
Super lightweight zsh plugin manager to use in locked down or root user environments

My goal was to maximise terminal usability while keeping a minimal footprint

It doesn't rely on a package manager so it will work in TrueNAS

It is modular so you can add your own features or remove any of mine
## Features
* Scrollable pop-up command history with fuzzy find (Ctrl+R)
* Scrollable pop-up file tree with fuzzy find (Ctrl+T)
* File tree command completion via ** + tab
* Syntax highighting
* Autosuggestions from command history (right arrow to accept)
* Configurable fancy prompt builder
* Random password generator (type 'randompass')
## Installation
You'll need zsh, curl and git as prerequisites
1. Clone the repo into ~/.zsh
2. Change your default shell to zsh
3. Source the ~/.zsh/rc file
4. Set zsh as your default shell
This should do it:
```zsh
cd ~
git clone https://github.com/daylight-roberty/rc-lite.git
mv ~/rc-lite ~/.zsh
echo "source ~/.zsh/rc" >> ~/.zshrc
chsh -s $(which zsh)
eval $(which zsh)
```
## How it works
The ~/.zsh/rc file in turn sources every file in ~/.zsh/__modules
It also contains a standardised logging function for the downstream modules for consistency
Plugin modules each check if their respective plugins are installed. If not, they are downloaded from github
You can change the version/architecture/checksum for plugin downloads via module variables
Plugins are enabled once confirmed installed
