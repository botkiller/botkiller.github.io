---
layout: page
title: Macbook Setup
description: Configure a new Macbook for general use.
img: assets/img/m1-max.webp
importance: 1
category: documentation
---

### First Time Setup
Before doing anything else, update the MacOS operating system to the latest version. 
-  > System Preferences > Software Update

### System Preferences
#### Login Options
`System Preferences > Users & Groups > Login Options`
- Enable "Show fast user switching menu as **[Icon]**"

#### Trackpad 
`System Preferences > Trackpad`
- Increase speed to just below the maximum.

#### Keyboard
`System Preferences > Keyboard > Text`
- Disable "Correct spelling automatically"
- Disable "Capitalize words automatically" 
- Disable "Add period with double-space"
- Disable "Use smart quotes and dashes"
<div class="row justify-content-sm-center">
    <div class="col-sm-4 mt-1 mt-md-0">
        {% include figure.html path="assets/img/syspref_keyboard_text.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

#### Dock & Menu Bar
`System Preferences > Dock & Menu Bar`
- Size: **Small**
- Magnification: **Min**
- Position on Screen: **Left**
- Minimize window using: **Scale Effect**
- Uncheck "Show recent applications in Dock"
<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/syspref_dock.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


#### iCloud Drive
`System Preferences > AppleID > iCloud > iCloud Drive > Options...` 
- Sign in to iCloud
    - Select "Desktop & Documents Folders"
<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/syspref_icloud.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

#### Sharing
`System Preferences > Sharing`
- Change computer name to `MBP`
- Run the following to update the system name in Terminal:
```zsh
run "sudo scutil --set HostName MBP"
```
- New Terminal prompt should read `cj@MBP`

#### Notifications
`System Preferences > Notifications`
- **Disable all other notifications except for the following**:
    * App Store
    * Calendar
    * Facetime
    * Find My 
    * Home
    * iTerm
    * Messages
    * Notes
    * Reminders
    * Safari
    * Screen Time
    * Wallet

#### Mission Control
`System Preferences > Mission Control`
- Disable "Automatically rearrange Spaces based on most recent use"
- Disable "When switching to an application, switch to a Space with open windows for the application"


### Dock
Remove the following default apps from the Dock:
    * Launchpad
    * Mail
    * Maps
    * Photos
    * Facetime
    * Contacts
    * Reminders
    * TV
    * Podcasts
    * News
    * App Store

### Finder
- `Finder > View`
    - Select Show Path Bar
    - Select Show Status Bar
- `Finder > Preferences`
    - New Finder Windows Show: **Macintosh HD**
    - `> Advanced` 
        - Disabled "Show warning before changing an extension" 
        - Enable "Show all filename extensions" 
- `Finder > Go > Connect to Server`
    - DS920: `192.168.1.20`
    - DS212: `192.168.1.25` 
- From within iCloud Drive add `_Projects`, `_Films`, and `_Code` to the Finder sidebar.

### Terminal
- Install Homebrew
    ```zsh
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/cj/.zprofile
    eval "$(/opt/homebrew/bin/brew shellenv)"
    ```
- Download and install the following fonts:
    - [MesloLGS NF Regular.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
    - [MesloLGS NF Bold.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
    - [MesloLGS NF Bold Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)
    - [MesloLGS NF Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
- Install iTerm2
    ```zsh
    brew cask install iterm2
    ```
- `iTerm2 > Preferences`
    - `Appearance > General`
        - Theme: **Compact**
    - `General > Closing`
        - Uncheck "Confirm quit iTerm2"
    - `Profiles`
        - Create a new Profile and set it as default.
        - `Window`
            - Transparency: **22**
            - Blur: **20**
            - Columns: **150**
        - `Text`
            - Font: **MesloLGS NF**

- Install ohmyzsh:
    ```zsh
        sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
        exec zsh
    ```




### Third Party Apps
#### UnnaturalScrollWheels
- Install UnnaturalScrollWheels
    ```zsh
    brew install --cask unnaturalscrollwheels
    ```

#### Alfred
- Install Alfred
    - Download and mount the [Alfred Disk Image](https://cachefly.alfredapp.com/Alfred_5.0.2_2073.dmg)
    - Drag Alfred.app into the Applications folder.
- Swap Spotlight keyboard shortcut for Alfred:
    - `System Preferences > Keyboard > Shortcuts > Spotlight`
        - Uncheck "Show spotlight search"
    - `Alfred > Preferences > General`
        - Set the Alfred Hotkey as CMD+SpaceBar
- Clean up Alfred's appearance:
    - `Alfred Preferences > Appearance > Options`
        - Select "Hide hat on Alfred window"
        - Select "Hide menu bar icon" 

### App Store
- [Amphetamine](https://apps.apple.com/us/app/amphetamine/id937984704?mt=12)
- [Screens 4](https://apps.apple.com/us/app/screens-4/id1224268771?mt=12)
- [GoodNotes 5](https://apps.apple.com/us/app/goodnotes-5/id1444383602) 
- [DaisyDisk](https://apps.apple.com/us/app/daisydisk/id411643860?mt=12)
- [Magnet](https://apps.apple.com/us/app/magnet/id441258766?mt=12)




<div class="row justify-content-sm-center">
    <div class="col-sm-9 mt-3 mt-md-0">
        {% include figure.html path="assets/img/syspref_dock.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-3 mt-3 mt-md-0">
        {% include figure.html path="assets/img/finder_sidebar.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>



