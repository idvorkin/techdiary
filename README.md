# Igor's Technical Diary

I love technical journeys, but I often lose track of why I started, what my priorities are, and where I've been. Explorers of old solved these problems by keeping a journal, so I'll try the same.

<!-- TOC -->

- [Igor's Technical Diary](#igors-technical-diary)
    - [Journeys](#journeys)
        - [To be started](#to-be-started)
            - [Rule the world](#rule-the-world)
        - [In progress](#in-progress)
            - [[Redshift from Linqpad](notes/linqpad_from_redshift.md)](#redshift-from-linqpadnoteslinqpad_from_redshiftmd)
            - [[Deploy a private web site](notes/private_web_site.md)](#deploy-a-private-web-sitenotesprivate_web_sitemd)
            - [[Debug clr using windbg](notes/windbg.md)](#debug-clr-using-windbgnoteswindbgmd)
            - [[Notes on all things security](notes/better-security-design.md)](#notes-on-all-things-securitynotesbetter-security-designmd)
            - [[Visual Vocabulary](notes/visual-vocabulary.md)](#visual-vocabularynotesvisual-vocabularymd)
        - [Blocked](#blocked)
        - [Too early to start](#too-early-to-start)
        - [Completed](#completed)
            - [[VLC Player Tips](notes/vlc_player.md)](#vlc-player-tipsnotesvlc_playermd)
            - [[iOS Usage](notes/ios.md)](#ios-usagenotesiosmd)
            - [[Mosh](notes/mosh.md)](#moshnotesmoshmd)
            - [[USB Tech](notes/usbtech.md)](#usb-technotesusbtechmd)
            - [[Ring Video Downloader](notes/ring-video-download.md)](#ring-video-downloadernotesring-video-downloadmd)
    - [Awesome Lists](#awesome-lists)
        - [Markdown](#markdown)
        - [VIM](#vim)
        - [C Sharp](#c-sharp)
        - [Java](#java)
        - [Python](#python)
        - [Typescript](#typescript)
        - [Apple](#apple)
        - [Home Automation](#home-automation)
        - [Powershell](#powershell)
        - [Text manipulation tools](#text-manipulation-tools)
        - [Cool shell tools](#cool-shell-tools)
        - [Natural Language Processing](#natural-language-processing)
        - [Github](#github)
        - [Random 1-liners](#random-1-liners)

<!-- /TOC -->

## Journeys

### To be started

#### Rule the world

### In progress

#### [Redshift from Linqpad](notes/linqpad_from_redshift.md)
#### [Deploy a private web site](notes/private_web_site.md)
#### [Debug clr using windbg](notes/windbg.md)
#### [Notes on all things security](notes/better-security-design.md)
#### [Visual Vocabulary](notes/visual-vocabulary.md)
#### [ManageMe](notes/manage-me.md)

### Blocked

### Too early to start

_The bleeding edge can be fun, but you burn lots of time dealing with sharp edges. Here's my list of things I want to get into once they stabilize._

### Completed

_Nothing is really completed, but you need to stop somewhere._

#### [VLC Player Tips](notes/vlc_player.md)
#### [Pandas Tips](notes/pandas-tutorial.md)
#### [iOS Usage](notes/ios.md)
#### [Mosh](notes/mosh.md)
#### [USB Tech](notes/usbtech.md)
#### [Ring Video Downloader](notes/ring-video-download.md)

## Awesome Lists

### Markdown

- Typora
- Visual Studio Code

### VIM

- Denite
- Fugitive

### C Sharp

### Java

- Lambok

### Python

- Hug: Python API generator
- Httpie: wget replacement
- Pendulum: The best datetime library (better then arrow).
- PipEnv - Finally sane dependency management for python!
- [Datalore](https://datalore.io/) - Jetbrain's version of Jupyter
- [Requests] (http://docs.python-requests.org/en/master/) Http requests for humans
- [Requests-HTML] (https://github.com/kennethreitz/requests-html) Web Parsing for humans
- [Scapy] (https://scrapy.org/) Web crawling for humans.
- [Records] (https://github.com/kennethreitz/records) Raw SQL for humans
- [Delegator] (https://github.com/kennethreitz/delegator.py) Sub process for humans
-

### Typescript

- [Quick Type](https://quicktype.io/?l=cs&r=json2csharp) Create classes from json 

### Apple

- Copy files **without** itunes - [CopyTrans Manager](https://www.copytrans.net/copytransmanager/)

### Home Automation

- Bridge from HomeKit to Wink - [Homebridge-wink3](https://github.com/sibartlett/homebridge-wink3)

### Powershell

- Vim keybindings (built in psreadline)
- Jump to arbitrary directory based on frequency (z) 

### Text manipulation tools

- XPath and HtmlAgilityPack
- Regexp + VIM
- Beautiful soup

### Cool shell tools

- Tig - Command Line git gui/gitk
- Mosh - A better ssh
- fasd - An awesome command line completion tool.
- w3m -  Text based web browser
- fzf - Fuzzy file inder
- Rg - RipGrep (like ag) 

### Natural Language Processing

- Rant - a cool c# human [language generator](http://berkin.me/rant/)
- Rhymebrain - 
- Tranquil

### Github

- Serve HTML files directly from github: https://rawgit.com/idvorkin/linqpadsnippets/master/js/DetectBackButton.html

### Random 1-liners

Clean up dead MOSH instances

    kill $(ps --no-headers --sort=start_time -C mosh-server -o pid | head -n -1)

zsh path append

    path+="/my/new/path"
