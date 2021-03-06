<!--
EncodedREADME - My personal README style.
Yes, there is HTML in Markdown; you don't have to tell me.
This README style is loosely inspired by Akarin's README!
-->

<img src="https://repository-images.githubusercontent.com/282035636/d9c52600-6092-11eb-8077-b8c0eedfa2c4" width="200px" align="right">
<div align="center">

# MatrixChecks
### The highly customizable, organized, and optimized checks configuration for [Matrix Anticheat](https://www.mc-market.org/resources/13999), a powerful, modern, and lightweight anticheat for Minecraft 1.8 and higher.
<br/>
</div>

<table align="center">
<tr>
<td>

**Make sure to use files compatible with your Matrix version!**  
<sub>
Sometimes Matrix Premium updates faster than Free; there will be a directory if so.  
Legacy releases compatible with older versions of Matrix have their own branches.
</sub>

[![Matrix Anticheat](https://img.shields.io/badge/Plugin-Matrix%20Anticheat-%237009ac?style=flat-square)](https://www.mc-market.org/resources/13999) ![Commits since release](https://img.shields.io/github/commits-since/Encode42/MatrixChecks/latest/main?label=Commits%20since%20release&style=flat-square)  
[![Checks Support](https://img.shields.io/discord/707330384328654869?color=7289DA&label=Checks%20Support&style=flat-square)](https://discord.gg/rjSkFyj) [![Matrix Support](https://img.shields.io/discord/392904793758367745?color=7289DA&label=Matrix%20Support&style=flat-square)](https://discord.gg/rGhYma6)  
[![Sponsored By TropicSolutions](https://img.shields.io/badge/Sponsored%20By-TropicSolutions-ef9224?style=flat-square)](https://www.tropicsolutions.net/=EN) [![More Information Below](https://img.shields.io/badge/More%20Information%20Below-ef9224?style=flat-square)](https://github.com/Encode42/MatrixChecks#%EF%B8%8F-project-sponsor)
</td>
<td>

#### Features
- Works on free & premium Matrix.
- Tons of customization.
- Improved violation & kick messages.
- Lower amount of false positives.
- Stricter checks. *(Faster detection)*
- Multiple file types to suit your needs.
</td>
</tr>
</table>

⚠ **REQUIRED INSTALLATION NOTE:**  
You **must** install [`language.yml`](https://raw.githubusercontent.com/Encode42/MatrixChecks/main/language.yml) to use placeholders!  
Otherwise, many messages will be unreadable! Every message  
contains placeholders that require the language file.

⚠ **GENERAL NOTE:**  
`config.yml` and `language.yml` **do not** include any checks!  
Install [`checks.yml`](https://raw.githubusercontent.com/Encode42/MatrixChecks/main/checks.yml) to utilize the main detection changes.

## 🔧 Setup
### Server Usage
1. Download [checks.yml](https://raw.githubusercontent.com/Encode42/MatrixChecks/main/checks.yml) and [language.yml](https://raw.githubusercontent.com/Encode42/MatrixChecks/main/language.yml).  
  <sub>For specific Matrix versions, head to the [releases page](https://github.com/Encode42/MatrixChecks/releases).</sub>
2. Rename Matrix's original `checks.yml` and `language.yml` to something else.
3. Upload/move the new files to your Matrix plugin folder. (`/plugins/Matrix/`)
4. If you downloaded any optional files, rename them to `checks.yml`/`language.yml`.
5. Run `/matrix reload` or restart the server!

Alternatively, you can just run `/matrix dlcfg OBCHXARALB` in-game  
to download the latest stable build of MatrixChecks. (This ID changes!)  
The downside is that all comments are removed and the file size is reduced.

### Cloud Usage
1. Download [config.yml](https://raw.githubusercontent.com/Encode42/MatrixChecks/main/config.yml) and [language.yml](https://raw.githubusercontent.com/Encode42/MatrixChecks/main/language.yml).  
2. Rename Matrix's original `config.yml` and `language.yml` to something else.
3. Change `cloud_config.enable: false` to `true` in `config.yml`.
4. Run `/matrix reload` or restart the server! The checks will now update on every reboot/reload.  
<sub>For specific Matrix versions, replace `main` in the link with the compatible checks branch.</sub>

## ❔ FAQ
These checks may not work perfectly with your server.  
Plugins, software, and performance can all affect how well these checks and the anticheat, in general, will work.  
**This is not a drag-and-drop solution!** Some values may need to be changed to work best with your setup.

Matrix Anticheat, like most, isn't a perfect anticheat. It itself has bugs that we cannot fix.  
These checks aim to mitigate those issues and improve what works well, but there's only so much we can do.  
Tested and configured for survival and minigame servers. Tweak the checks for your own server!

### 1. Checks file types
#### checks.yml
The main checks file. Includes all of the advertised features.  
Conditional commands, optimized checks, increased detection speed, etc.

#### language.yml
The main language file. This file must be installed on every Matrix instance.  
It contains all of the global placeholders used in `checks.yml`.

#### config.yml
An optional file that only changes a few things from the original config.  
Includes organization, minor tweaks, and a pre-set cloud config for MatrixChecks.

#### /optional/kickless.language.yml
Same as `language.yml` but with the kick command disabled.  
This is helpful for debugging or modifying checks without getting kicked.

#### /optional/unknown.language.yml
Same as `language.yml` but with different kick messages based on confusion.  
All kick messages are replaced with a generic message and a number for staff.  
This allows staff to know why a player was kicked without letting the player knowing which hacks to disable.

#### /optional/error.language.yml
Same as `language.yml` but with different kick messages based on confusion.  
All kick messages are replaced with existing and made-up error messages.
This confuses hackers since they have no idea what they were kicked for.

#### /cloud
The exact same as the files above, but minified. These are much smaller in file size but are nearly impossible to read.  
Because of the small file sizes, these can be automatically downloaded and updated very quickly on server startup.  
These are optimized for Matrix cloud usage with `config.yml`. For instructions, read [Cloud Usage](https://github.com/Encode42/MatrixChecks#cloud-usage).

#### /.github, license.md, readme.md
These are files that are only important for and used in this GitHub repository.  
You can completely ignore these files as they have nothing of importance for the end-user.

### 2. Suggested changes
These are just suggestions, don't change them if you don't need to.  
Only use these if you're having issues with the listed checks!

Root Check | Path                               | Default | Suggestion       | Reason
---------- | ---------------------------------- | ------- | ---------------- | -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
`click`    | `max_cps`                          | `18`    | `16` - `24`      | The highest possible CPS achieved by humans is 24. Lag may affect the accuracy of this value.
`hitbox`   | `max_reach`                        | `3.18`   | `3.2` - `3.3`   | Increase if there are many false-positives with this check. This value should never be less than 3.1!
`block`    | `fastplace.max_place_per_second`   | `13`    | `10` - `18`      | Increase if there are many false-positives when placing blocks, decrease if there are many bypasses.
`scaffold` | `...delay.min_delay`               | `8`     | `5` - `9`        | Decrease if there are many false-positives when pillaring, increase if there are many bypasses.
`delay`    | `check_inventory_action`           | `-1`    | `4` - `5`        | Enable this check for minigame servers with chest mechanics such as survival games, skywars, etc.
&nbsp;     | `...` = relative path              | &nbsp;  | `X - X` = range  | &nbsp;

### 3. How do I report a change or false positive?
**First:**  
Make sure this isn't an issue with Matrix itself. Test with the [default Matrix config files](https://github.com/jiangdashao/Matrix-Issues). If the issue persists, it's most likely an issue with Matrix. You can report the issue to us, but not everything can be fixed with a checks file tweak. Head over to [Matrix's support Discord](https://discord.gg/wjheaRj) and ask about the issue, or report the issue at their [issue tracker](https://github.com/jiangdashao/Matrix-Issues/issues).  
- [(Matrix) Discord](https://discord.gg/wjheaRj)  
- [(Matrix) Issues](https://github.com/jiangdashao/Matrix-Issues/issues)

**Then:**  
Report the issue in the [MatrixChecks support Discord](https://discord.gg/rjSkFyj) or make a report at the [issue page](https://github.com/Encode42/MatrixChecks/issues) with the right template. If you describe what you want to be changed/fixed thoroughly, the chances are that it'll be taken care of quickly. If you already know what the issue is or how to fix it, feel free to make a [pull request](https://github.com/Encode42/MatrixChecks/pulls) containing the change and why you made it.  
- [Discord](https://discord.gg/rjSkFyj)
- [Issues](https://github.com/Encode42/MatrixChecks/issues)  
- [Pull Requests](https://github.com/Encode42/MatrixChecks/pulls)

### 4. There are weird things in every message!
Do the "weird things" look like something along the lines of "`%gp_o_pr%`"? If so, you have not installed `language.yml`.  
This file is required to replace those placeholders with what they're meant to be. [Installation](https://github.com/Encode42/MatrixChecks#server-usage)

### 5. Can I modify the files in MatrixChecks?
Yes! I encourage you to do so. Since all servers are different, you most likely will have to modify the files anyway.  
You can also distribute it all you want or use it on a large network; just don't remove copyright notices as that's against the license.

### 6. How can I contribute?
Contributions are very welcome! If you created a new optional file or made tweaks for different minigames, feel free to contact me or make a pull request.  
I don't want to start any competition with this project! Having everything in one central repository makes it much easier for the end-user to find what they want.

## 🖥️ Project Sponsor
<div align="center">
<a href="https://www.tropicsolutions.net/=EN"><img src="https://cdn.discordapp.com/attachments/365455168583499779/791342416224714752/darkModeEN.png"></a>
<h3>

This project hosts a test server sponsored by [TropicSolutions](https://www.tropicsolutions.net/=EN).
</h3>
<h4>

IP: `matrix.encode42.dev` │ Versions 1.8 - 1.16.4
</h4>
