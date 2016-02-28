# Computer Setup
To make sure your computer is ready for day 1 of class we will need to download a few programs and install a few tools and verify that they are working.

## Programs Needed
 - Chrome
 - Slack 
 - Atom
 - iTerm2
 - Sip
 
## Tools Needed
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
   - Type `git config --global user.name "YOUR REAL NAME GOES HERE"` into your terminal and hit enter. You won't see anything afterwards, thats good.
   - Type `git config --global user.email "YOUR PROFESSIONAL EMAIL GOES HERE"` and hit enter. Using whatever email you used to sign up for Github.com with.
   - To verify the setup worked. Type `git config -l` and you should see your name and email.
 5. Installing an updated version of **Ruby** using **RVM** the **R**uby **V**ersion **M**anager
   - _(Don't follow this step if you have rbenv installed: If you don't know what that is, you're fine.)_
   - Type `\curl -L https://get.rvm.io | bash -s stable` into your terminal and hit enter.
   - Once the previous command is finished. Quit Iterm and reopen it.
   - Type `rvm | head -n 1` and hit enter. Have your instructor (me) come look at the output to verify it is working.
   - Type `rvm use ruby-2.3.0 --install --default` into your terminal and hit enter. This is the part that installs the new ruby version. It will take some time.
   - Once it has completed. Restart your terminal once more and type `ruby -v` and check the version. It should be `2.3.0`.
 6. Setting up our dotfiles
   - .zshrc
   - .vimrc
   - .rvmrc
   - .gitrc
   - .irbrc
   - .pryrc
