---
layout: page
title: Home Network Setup
description: Details of how to set up a Ubiquiti & Synology home network.
img: assets/img/ds920.png
#redirect: https://unsplash.com
importance: 3
category: documentation
---

## Password Management
### iCloud Keychain
Due to us living in an Apple ecosystem, iCloud keychain is the ideal method for storage/retrieval for any accounts accessed via web UI. iCloud Keychain can generate complex passwords that are neatly separated by dashes for easier typing. 

iCloud Keychain can be accessed in `System Preferences (MacOS)/Settings (iOS) > Passwords`. 

### Bitwarden
The one glaring flaw with iCloud Keychain is that it requires a web URL to save a password. Due to this limitation, Bitwarden is used for tracking credentials on non-web accounts.

Bitwarden is locally encrypted and cloud synced and secured with 2-factor authentication. The app is available on the [App Store](https://apps.apple.com/us/app/bitwarden/id1352778147?mt=12). 

Bitwarden is also used for storing secure notes related to the network configuration and specific entries will be referenced throughout this document rather than publically documenting that information.

## Synology 
### Web Account
- Set up or reset primary Synology.com account with Safari generated password. Copy password to Bitwarden. 
- Enable 2-Factor Authentication 
- Download [Synology Secure Sign In app](https://apps.apple.com/pl/app/synology-secure-signin/id1513105891)
- Configure DDNS for personal URL. Details are stored in [Bitwarden](https://vault.bitwarden.com/#/vault?type=2&itemId=b878546a-6e4f-42b1-8e9a-af29018a7052).


### RT2600ac
`192.168.1.1` ([Web UI](http://192.168.1.1:8000/webman/index.cgi))
- Create router admin account with Safari generated password. 
- Disabled UPNP
- Enable Firewall and set all to Deny 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/router_deny.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

- Add Port forwarding for DS920 OpenVPN 1194, DS920 DSM (HTTPS) 5001
- Identify stray WiFi clients and block them from DCHP list. 
- **TODO:** [Research if VLANs](https://www.reddit.com/r/HomeNetworking/comments/byw9mt/comment/eqndvi6/?utm_source=share&utm_medium=web2x&context=3) are appropriate for my use case. 


### DS920

|Setting|Value|
| ----------- | ----------- |
| IP Address | [192.168.1.20](http://192.168.1.20:5000/#/signin)| 
| Device Name | `DS920`       |
| Volume Name   | `Volume 1`        |
| Capacity | `20TB`|

- Configure admin account with Safari generated password and store in Bitwarden. 
- Disable the default admin account. 


### DS212

|Setting|Value|
| ----------- | ----------- |
| IP Address | [192.168.1.25](http://192.168.1.25:5000/#/signin)| 
| Device Name | `DS212`       |
| Volume Name   | `Volume 1`        |
| Capacity | `2.7TB`|


## UniFi
### UDM Pro 

### Switch Pro 24 PoE



## IDrive
- Download 

## OpenVPN
- [Instruction video](https://www.youtube.com/watch?v=qbfa-YVUfls)
- Download Synlogy VPN Server package
- From the VPN Server package, enable OpenVPN Server 
- Set privileges for newly created admin account to allow OpenVPN access
- Configure port forwardig on RT2600ac for UDP port 1194 to 192.168.20
- Configure [Synology DDNS](https://kb.synology.com/en-us/DSM/help/DSM/AdminCenter/connection_ddns?version=6)
- Export config files and edit to create Full and Split configs
- Install passepartout client and load config. 


## iCloud 


Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, *bled* for your project, and then... you reveal its glory in the next row of images.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>


The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}
```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
```
{% endraw %}
