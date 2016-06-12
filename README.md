# Computer Setup
To make sure your computer is ready for day 1 of class we will need to download a few programs and install a few tools and verify that they are working.

## Programs Needed (Go download these now)
 - [Chrome](https://google.com/chrome)
 - [Slack](https://itunes.apple.com/us/app/slack/id803453959?mt=12)
 - [Atom](http://atom.io/)
 - [iTerm2](https://www.iterm2.com/downloads.html)
 - [Sip](https://itunes.apple.com/us/app/sip/id507257563?mt=12)
 - [Dash](https://itunes.apple.com/us/app/dash-3-api-docs-snippets./id449589707?mt=12)
 
## Tools Needed (Will be installed below)
  - Git
  - RVM
  - Homebrew
  - Ruby
  - Postgresql
  - ZSH
  - tree

## Step by Step Guide
 0. Turn off "Smart Quotes"
   - Go to System Preferences
   - Go to Keyboard
   - Go to the Text tab
   - Make sure the checkbox labeled "Use smart quotes and dashes" is **not** checked.
  
 1. Install The **XCode Developer Tools**
   - To install the dev tools, open your terminal and type `xcode-select --install` and then hit enter.
   - It will say you do not have the developer tools and prompt you to download them. Click "Install".
   - _This probably take some time_
   - Verify the install worked by typing:
     -`xcode-select -p` and pressing enter. You should see `/Library/Developer/CommandLineTools`.
     -`gcc --version` and pressing enter. You should see `Configured with: --prefix=/Library/Developer/CommandLineTools/usr --with-gxx-include-dir=/usr/include/c++/4.2.1` plus a few more lines.

 2. Install **Homebrew**
   - To install homebrew, copy and paste the following command into your terminal and then hit enter.
   - `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
   - Verify the install worked by typing:
     - `brew -v` and pressing enter. You should see `Homebrew 0.9.X (blah blah)`.
     - `brew doctor` and press enter. It will say a lot. Have your instructor (me) come look at it before moving on.
     
 3. Install **git**
   - To install git, run `brew install git` and hit enter.
   - To verify it installed correctly, type `git --version` and you should see `git version 2.x.x` (x is some number)
    
 4. Setup **git**
   - Type `git config --global color.ui true` into your terminal and hit enter.
   - Type `git config --global user.name "YOUR REAL NAME GOES HERE"` into your terminal and hit enter. You won't see anything afterwards, thats good.
   - Type `git config --global user.email "YOUR PROFESSIONAL EMAIL GOES HERE"` and hit enter. Using whatever email you used to sign up for Github.com with.
   - To verify the setup worked. Type `git config -l` and you should see your name and email.
 
 5. Installing an updated version of **Ruby** using **RVM** the **R**uby **V**ersion **M**anager
   - _(Don't follow this step if you have rbenv installed: If you don't know what that is, you're fine.)_
   - Type `\curl -L https://get.rvm.io | bash -s stable` into your terminal and hit enter.
   - Once the previous command is finished. Quit Iterm and reopen it.
   - Type `rvm | head -n 1` and hit enter. Have your instructor (me) come look at the output to verify it is working.
   - Type `source ~/.profile` to load the rvm settings. 
   - Type `rvm use ruby-2.3 --install --default` into your terminal and hit enter. This is the part that installs the new ruby version. It will take some time.
   - Once it has completed. Restart your terminal once more and type `ruby -v` and check the version. It should be `2.3.0`.
 
 6. Installing **OhMyZsh** ("oh-my-zeesh" or "oh-my-Z-shell")
   - To install [OhMyZsh](http://ohmyz.sh/) type `sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"` into your terminal and hit enter.
   - After it is finished. Restart your terminal. Your prompt should look slightly different now.
  
 6. Setting up our dotfiles
   - To set up our 'dotfiles' we are going to need to be able to open text documents from our editor. Lets make sure we can do that, by opening up Atom and going to the "Atom" menu at the top and clicking "Install Shell Commmands". This allows you to open files from the terminal by saying `atom NAME_OF_FILE`.
   - First we need to make some changes to our `.zshrc` file. Its a big file, but we only need to make a few minor tweeks.
   - Find the line in the file that says `ZSH_THEME`, its towards the top. Replace it with this line: `ZSH_THEME="avit"`
   - At the very bottom of the file, add the following lines. This allows RVM to work with out new fancy terminal.
   - `export PATH=~/bin:$PATH # Add local bin directory`
   - `export PATH="$HOME/.rvm/bin:$PATH" # Add RVM to PATH for scripting`
   - `[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm" # Load RVM into a shell session *as a function*`
   - After that save and close the `.zshrc` file. To confirm it worked correctly, type `source ~/.zshrc` to reload the file. Your prompt should change.
   - Now we need to open a new file, type: `atom .gemrc` and add this single line `gem: --no-rdoc --no-ri`.
   - Save and Quit Atom
   
 7. Installing **Postgresql**
   - The final thing we will install today is [Postgresql](http://www.postgresql.org/), it is the database we will be using with Rails. Postgres, like most databases, will run in the background on your computer. This will save you the hassle of having to start and stop it every time you work on a new project.
   - Install Postgresql with `brew install postgresql` and wait for it to finish.
   - Afterwards you'll see a ton of information printed out for you. What is important is that we run the two commands that tell the computer to start Postgre whenever the computer is turned on and that we turn it on now.
   - Type `ln -sfv /usr/local/opt/postgresql/*plist ~/Library/LaunchAgents` and hit enter.
   - Type `launchctl load ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist` and hit enter.
   - If you got no errors, you should be set!


