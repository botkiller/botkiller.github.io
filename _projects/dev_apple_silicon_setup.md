---
layout: page
title: Apple Silicon Dev Setup
description: Development environment configuration steps for M1 Max. 
img: assets/img/apple_vscode.png
importance: 2
category: documentation
---

Much of this article assumes you have completed the [Basic Macbook Setup](../macbook_setup) steps.

### VSCode
VSCode is the central IDE for Python and SQL Server development, as well as our best text editor for virtually any size or format of flat file. 

- Install VSCode
    ```zsh
    brew install --cask visual-studio-code
    ```
- Configure VSCode
    - Enable settings sync with Microsoft account. 
    - Set flat file defaults:
        - Create new, empty files to use for defaults: 
        ```zsh
        nano ~/Desktop/default.py
        nano ~/Desktop/default.csv
        nano ~/Desktop/default.py
        ```
        - For each, go to `Finder > Get Info > Open With > Change All`
            - Set to `Visual Studio Code.app`
    - From Command Pallete (⌘+⇧+P):
        - `Extensions: Install Extensions`
            - Jupyter
            - Predawn Theme Kit
            - Ayu (for file icons)
            - Python
            - SQL Server (mssql)
            - SQL Database Projects
            - Pylance
            - Markdown Preview
        - `Shell Command: Install 'code' command in PATH`
            - Install: Shell (Enables "code" PATH in Terminal)
        
- Download [.NET SDK for macOS ARM64](https://dotnet.microsoft.com/en-us/download/dotnet/6.0)
    - May also need to run this to ensure the `dotnet` command works in Terminal:
    ```zsh
    sudo ln -s /usr/local/share/dotnet/dotnet /usr/local/bin/
    ```

### Git
- Install Git
    ```zsh
    brew install git
    ```
    - Confirm `which get` returns `usr/local/bin/git'
- Configure `~/.gitconfig` 
    Note that the email address used will determine which account is publishing changes from your dev computer.
    ```zsh
    git config --global user.email "<EMAIL_ADDRESS>"
    ```

### Python
- Install Python 3 (Should prompt to download XCode tools)
    ```zsh
    python3 --version
    ```
- Update Terminal for Python commands:
    ```zsh
    nano ~/.zshrc
    ```
    ```.zshrc
    alias python='python3'
    alias py='python3'
    alias pip='pip3'
    ```
- Update pip
    ```zsh
    pip install --upgrade pip
    ```
- Libraries
    - pyodbc
    ```zsh
    brew install unixodbc
    pip install pyodbc
    ```

### Ruby
- Install Ruby
    ```zsh
    brew install chruby ruby-install
    ```
- Confirm versions for Xcode and Apple Command Line Tools:
    ```zsh
    brew config 
    ```
    - If either version starts with `14` then run the following command. If they don't, check [here](https://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/).
        ```zsh
        ruby-install ruby -- --enable-shared
        ```

#### Jekyll
- Install Jekyll
    ```zsh
    gem install jekyll
    ```
- When bundling, verify `Gemfile.lock` contains the correct PLATFORMS. Add missing platforms like so: 
    ```zsh
    bundle lock --add-platform x86_64-linux
    bundle lock --add-platform arm64-darwin-19
    ```


### App Store 
- [Xcode](https://apps.apple.com/us/app/xcode/id497799835?mt=12)