## Tools Setup

Commands written under install steps (`xcode-select`…, `curl`…, etc…) should be copied and pasted into your terminal.

1. Install [iTerm 2](http://www.iterm2.com/#/section/home)
2. Install the [Xcode Command Line Tools](https://developer.apple.com/library/ios/technotes/tn2339/_index.html)
  * `xcode-select --install`
3. Install [Oh My Zsh](https://github.com/robbyrussell/oh-my-zsh)
	* `curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh`
4. Install [Homebrew](http://brew.sh/)
  * `ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
5. Install [Node.js](http://nodejs.org/)
  * `brew install node`

## Text Editor Setup
1. Install [Sublime Text 3](http://www.sublimetext.com/3)
2. Install [Package Control for Sublime Text 3](https://packagecontrol.io/installation)
3. Install the following Sublime Text packages (`⌘ + ⇧ + P` -> Install)
  * SCSS
  * BracketHighlighter
  * Color Highlighter
  * EditorConfig
  * Emmet
  * GitGutter
  * MarkdownEditing 
4. Enable Sublime Text 3 to be [opened from the command line](https://www.sublimetext.com/docs/3/osx_command_line.html)
  * `ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" ~/bin/subl`

## Terminal Enhancements
1. Install the fonts from `Fonts`
2. Open iTerm 2's Preferences and go to Profiles
	* Under Colors, click `Load Presets… -> Import…`and choose `Snugug.itermcolors`
	* Under Text, change `Regular Font` and `Non-ASCII Font` to `Source Code Pro for Powerline`. I recommend `Light 14pt` font
3. Copy `Terminal-Enhancements/snugug.zsh-theme` to `~/.oh-my-zsh/themes`.
  * From your terminal, `open ~/.oh-my-zsh/themes` Copy file into there.
4. Open `~/.zshrc`, make `ZSH_THEME="snugug"`, save, and restart your terminal
  * From your terminal, `subl ~/.zshrc`