# Igor's Technical Diary

I love technical journeys, but I often lose track of why I started, what my priorities are, and where I've been. Explorers of old solved these problems by keeping a journal, so I'll try the same.

<!-- TOC GFM -->

- [Journeys](#journeys)
    - [To be started](#to-be-started)
        - [Rule the world](#rule-the-world)
    - [In progress](#in-progress)
        - [Machine Learning for Igors](#machine-learning-for-igors)
        - [Deploy a private web site](#deploy-a-private-web-site)
        - [Notes on all things security](#notes-on-all-things-security)
        - [Visual Vocabulary](#visual-vocabulary)
        - [Windows Virtual Desktop](#windows-virtual-desktop)
        - [Alexa Skill](#alexa-skill)
        - [ManageMe](#manageme)
    - [Blocked](#blocked)
        - [Redshift from Linqpad](#redshift-from-linqpad)
        - [Debug clr using windbg](#debug-clr-using-windbg)
    - [Too early to start](#too-early-to-start)
    - [Completed](#completed)
        - [VLC Player Tips](#vlc-player-tips)
        - [Pandas Tips](#pandas-tips)
        - [iOS Usage](#ios-usage)
        - [Mosh](#mosh)
        - [USB Tech](#usb-tech)
        - [Ring Video Downloader](#ring-video-downloader)
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
        - [jq](#jq)
    - [Cool shell tools](#cool-shell-tools)
    - [Natural Language Processing](#natural-language-processing)
    - [Github](#github)
    - [Random 1-liners](#random-1-liners)
    - [App Launchers](#app-launchers)
    - [Chrome extensions](#chrome-extensions)
    - [Linters and formatters](#linters-and-formatters)

<!-- /TOC -->

## Journeys

### To be started

#### Rule the world

### In progress

#### [Machine Learning for Igors](notes/machine-learning.md)

#### [Deploy a private web site](notes/private_web_site.md)

#### [Notes on all things security](notes/better-security-design.md)

#### [Visual Vocabulary](notes/visual-vocabulary.md)

#### [Windows Virtual Desktop](notes/virtual-desktops.md)

#### [Alexa Skill](notes/alexa-skill.md)

#### [ManageMe](https://github.com/idvorkin/manage-me)

### Blocked

#### [Redshift from Linqpad](notes/linqpad_from_redshift.md)

    Linqpad is awesome, but it'll be a while till I get back to an MS shop.

#### [Debug clr using windbg](notes/windbg.md)

    I'm too old to pound on assembly language. Although I'm still proud of [this](http://ig2600.blogspot.com/2012/12/run-time-costs-of-small-operations-in-c.html)

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
- [Requests](http://docs.python-requests.org/en/master/) Http requests for humans
- [Requests-HTML](https://github.com/kennethreitz/requests-html) Web Parsing for humans
- [Scapy](https://scrapy.org/) Web crawling for humans.
- [Records](https://github.com/kennethreitz/records) Raw SQL for humans
- [Delegator](https://github.com/kennethreitz/delegator.py) Sub process for humans
- Pylinkvalidator - Crawl a web site for errors (great for web testing)

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

#### jq

jq is the javascript equivelant of regexp
I'm very enemared with it!

By default it colorizes:

    cat x.json | jq

It has funny escaping syntax - so I'll list out some recipes. Notice the specific of dots open brackets and quote types. They matter.
Select every object in the array and string interpolat out object elements of name defaultHostName and appServicePlanId

    cat x.json | jq '.[] | "\(.defaultHostName) \(.appServicePlanId) "'

### Cool shell tools

Decent blog posts:

    https://remysharp.com/2018/08/23/cli-improved

- Tig - Command Line git gui/gitk
- Mosh - A better ssh
- fasd - An awesome command line completion tool.
- w3m - Text based web browser
- fzf - Fuzzy file inder
- Rg - RipGrep (like ag)
- [linuxbrew](http://linuxbrew.sh/) - Brew for linux
- Ngrok - Pipe ports to the internet web site (great for local host development on ios)
- [Bat](https://github.com/sharkdp/bat) - cat but with paging/git intgration.
- Pretty ping - Graphical Ping
- hTop - Nicer Top
- [fd](https://github.com/sharkdp/fd) - Better find/recurse.

### Natural Language Processing

- Rant - a cool c# human [language generator](http://berkin.me/rant/)
- Rhymebrain -
- Tranquil

### Github

- Serve HTML files directly from github: https://rawgit.com/idvorkin/linqpadsnippets/master/js/DetectBackButton.html

- Keyboard shortcuts: https://help.github.com/articles/using-keyboard-shortcuts/

### Random 1-liners

Clean up dead MOSH instances

    kill $(ps --no-headers --sort=start_time -C mosh-server -o pid | head -n -1)

zsh path append

    path+="/my/new/path"

### App Launchers

- Alfred on OSX
- WoX on Windows + (switcheroo to switch windows) [win - app name]

### Chrome extensions

- Hibernate unused tabs [The great suspender](https://chrome.google.com/webstore/detail/the-great-suspender/klbibkeccnjlkjkiokjodocebajanakg?hl=en)
- Close unused tabs [OneTab](https://chrome.google.com/webstore/detail/onetab/chphlpgkkbolifaimnlloiipkdnihall?hl=en)
- Vim based web [Vimium](https://chrome.google.com/webstore/detail/vimium/dbepggeogbaibhgnhhndojpepiihcmeb?hl=en)
- Vim in any text box [Wasavi](https://chrome.google.com/webstore/detail/wasavi/dgogifpkoilgiofhhhodbodcfgomelhe)
- Speed up youtube playback via keyboard shortcut [YouTube playback speed control](https://chrome.google.com/webstore/detail/youtube-playback-speed-co/hdannnflhlmdablckfkjpleikpphncik)

### Linters and formatters

You know what sucks less then coding standards? Arguing about coding standards. Nothing pains me more then arguing about formatting (and other minutia). As such I love having lint failures being build breaks and including formatting on save. Even better when you have [opinionated](https://stackoverflow.com/questions/802050/what-is-opinionated-software) formatters that don't have options. Sure standards suck, but they suck much less then arguing.

- Front End Stuff - [Prettier](https://prettier.io)
- Python - [Black](https://github.com/ambv/black)
