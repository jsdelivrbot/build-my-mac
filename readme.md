# 🔧 Welcome to My Mac-Maker 💻

This is, yet another, dev environment start-up script. My goal
here was to break down the particular items being installed into
individual modules. Each module is then sourced in with a single line in
the main *install.sh* script. That makes it real easy to remove anything
you do not want without worry of breaking other parts of this build.
Likewise, if there is anything you think is missing that you want to
add, the structure makes personal customization of this script really
straight forward.

<hr>

## Project Ogranization

The *install.sh* script is what will be run upon executing the start-up command listed below.
This script will get Brew up and running on your machine 🍻.
Durring the Brew install process the Brewfile will be ran which installs a number of binarys, libraries and applications.
It is recommended that you look over this file and the supporting *brew-casks* and *brew-mas* files to customize the setup to your liking.
Do note that Xcode is one of the items added in the `mas` bundle and can take quite a while to install ⏰.

After the Brew process is finished the *install.sh* script will begin to source the individual system modules/libraries to be installed.
If you do not wish to have a particular module or library installed on your machine simply delete or comment out the line in the *install.sh* script where it is sourced in.

All modules are organized together in the **run** 📂.
In each of their respective directories lives a *setup* script, which is what is sourced in the main *install.sh* script.
Some of the individual modules have additional dotfiles or supporting scripts files.
These may be files that will be symlinked into *your* **HOME** 📂,
or are provided as alternative options or further modularization for organizational purposes.
For example in the *zsh* module both *antigen* (my personal preference) and *oh-my-zsh* are included.

<hr>

## Install Instructions

The following command will pull down this repo onto your machine, creating a `~/projects/dotfiles/` directory structure.

```sh
curl -L https://api.github.com/repos/mrjadaml/mac-maker/tarball --create-dirs -o ~/projects/dotfiles.tar.gz &&
tar -zxvf ~/projects/dotfiles.tar.gz -C ~/projects/ &&
mv Mrjadaml* dotfiles
```

Once the project is copied down I suggest you peek through it and make any modifications to suit your personal preferences.

There is an optional Brew mas setup for Apple Store apps that you will be prompted about durring installation.
Please have your email and password for the Apple Store ready.

### Just run the script already!

Be sure you are in the *dotfiles* directory.

```
cd ~/projects/dotfiles
```

Then run the following command into your terminal:

```
source install.sh
```
Once the main install is finished, open up the `.vimrc` file and type in `:PluginInstall` to install all Vundle packages.

<hr>

## The Manifest 📕

#### Javascript

- [node] - A JavaScript runtime built on Chrome's V8 JavaScript engine.
- [nvm] - Node Version Manager: Simple bash script to manage multiple versions of node.

[node]: https://nodejs.org/en/
[nvm]: https://github.com/creationix/nvm

#### Python

- [Python 3] - An interpreted, object-oriented, high-level programming language.
- [Pyenv] - Simple Python version management.
- [Virtualenvwrapper] - Wrappers for creating virtual environments and isolating dependencies.

[Python 3]: https://www.python.org/download/releases/3.0/
[Pyenv]: https://github.com/yyuu/pyenv
[Virturalenvwrapper]: https://virtualenvwrapper.readthedocs.io/en/latest/

#### Ruby

- [Ruby] - A dynamic, open source programming language with a focus on simplicity and productivity -- MINASWAN
- [rvm] - Ruby Version Manager: Simple script to mange multiple versions of Ruby.

[Ruby]: https://www.ruby-lang.org/en/
[rvm]: https://rvm.io/

#### Homebrew

- [Homebrew] - Homebrew installs the stuff you need that Apple didn’t.
- [ctags] - Indexes language objects in source files so your text editor can quickly reference them.
- [git] - Open source version control system | update.
- [git-secrets] - Prevents you from committing secrets and creds into git repositories.
- [heroku-toolbelt] - A Heroku CLI.
- [httpie] - Command line HTTP client with an intuitive UI, JSON support, syntax highlighting.
- [imagemagick] - Create, edit, compose, or convert bitmap images.
- [mas] - Mac App Store command line interface.
- [openssl] - Open source toolkit for Transport Layer Security (TLS) and Secure Sockets Layer (SSL) protocols.
- [phantomjs] - Headless web browser scriptable with a JavaScript API.
- [postgresql] - An open source relational database management system (DBMS).
- [reattach-to-user-namespace] - Path to enable access to OSX pasteboard for programs run under tmux.
- [redis] - Open source in-memory data structure store, used as a database, cache and message broker.
- [tmux] - A terminal multiplexer.
- [vim] - Highly configurable text editor built in with most UNIX systems | update.
- [wget] - A non-interactive CLI for retrieving files using HTTP, HTTPS and FTP.

[Homebrew]: http://brew.sh/
[ctags]: http://ctags.sourceforge.net/
[git]: https://git-scm.com/
[git-secrets]: https://github.com/awslabs/git-secrets
[heroku-toolbelt]: https://devcenter.heroku.com/articles/heroku-cli
[httpie]: https://httpie.org/
[imagemagick]: https://www.imagemagick.org/script/index.php
[mas]: https://github.com/mas-cli/mas
[openssl]: https://www.openssl.org/
[phantomjs]: http://phantomjs.org/
[postgresql]: https://www.postgresql.org/
[reattach-to-user-namespace]: https://github.com/ChrisJohnsen/tmux-MacOSX-pasteboard
[redis]: https://redis.io/
[tmux]: https://tmux.github.io/
[vim]: http://www.vim.org/
[wget]: https://www.gnu.org/software/wget/

#### Shell

- [antigen] - A plugin manager for zsh, inspired by oh-my-zsh and vundle.
- [bash] - Built-in shell | update.
- [oh-my-zsh] - Community-driven framework for managing your zsh configuration.
- [zsh] - An interactive UNIX shell.

[antigen]: https://github.com/zsh-users/antigen
[bash]: https://www.gnu.org/software/bash/
[oh-my-zsh]: https://github.com/robbyrussell/oh-my-zsh
[zsh]: http://www.zsh.org/

#### Apps - Homebrew Cask

- [Atom] - GitHub's open source text editor
- [Alfred] - Mac Spotlight replacement with more custom and productive actions to control your Mac.
- [CloudApp] - Sharable screen capture tool with terminal integration.
- [Dash] - Offline access to 150+ API documentation sets plus script manager.
- [Dropbox] - Cloud storage.
- [Firefox] - Mozilla's web browser.
- [Google chrome] - Google's web browser.
- [Google chrome canary] - Google's web browser with beta features.
- [iterm2] - A terminal emulator and replacement for Mac's default Terminal app.
- [Slack] - A messaging app (corporate IRC 👔).

[Atom]: https://atom.io/
[Alfred]: https://www.alfredapp.com/
[CloudApp]: https://www.getcloudapp.com/
[Dash]: https://kapeli.com/dash
[Dropbox]: https://www.dropbox.com/
[Firefox]: https://www.mozilla.org/en-US/firefox/products/
[Google chrome]: https://www.google.com/chrome/
[Google chrome canary]: https://www.google.com/chrome/browser/canary.html
[iterm2]: https://www.iterm2.com/
[Slack]: https://slack.com/

#### App Store - Homebrew Mas

- [Evernote] - Note manager app.
- [Memory Clean] - Memory manager for your toolbar.
- [Monodraw] - Powerful ASCII art editor designed for the Mac.
- [Moom] - Window manager.
- [Pixelmator] - Photo editor.
- [Pocket] - Article saver/offline reader.
- [Sip] - Color picker.
- [SnappyApp] - Screen capture tool that leaves cropped capture ontop of all windows.
- [Xcode] - Integrated dev environment with tools for developing for macOS, iOS, WatchOS and tvOS.

[Evernote]: https://evernote.com/
[Memory Clean]: https://itunes.apple.com/us/app/memory-clean-monitor-free/id451444120?mt=12
[Monodraw]: https://monodraw.helftone.com/
[Moom]: https://manytricks.com/moom/
[Pixelmator]: http://www.pixelmator.com/mac/
[Pocket]: https://getpocket.com/
[Sip]: http://sipapp.io/
[SnappyApp]: http://snappy-app.com/
[Xcode]: https://developer.apple.com/xcode/

<hr>

#### Quick Reformating Guide. 💾

Obviously, back up all the files you don't want to have blown away before going through this process.

- Restart your computer and hold down `⌘ + r`.
- Once you see the white  logo and a progress bar you can let go of `⌘ + r`
- The "macOS Utilities" menu will pop up. Select the "Disk Utility" option from the list.
- From the sidebar labeled "Internal" click on sub hardive icon labled "Macintosh HD"
- From the row of icons at the top, click "Erase"
- A popup menu will appear with a field for the "Name" and "Format".
  Just leave the defaults and click the "Erase" button in the bottom right.
- Once it goes through its speel, click "Done"
- Close the Disk Utility window to get back to the "macOS Utilities" window.
- Now choose the option in the list labled "Reinstall macOS" and click "Continue"
- From here it will guide you through the steps to a fresh install.
