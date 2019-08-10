# Igor's Technical Diary

- Major Research Areas and Musing
  - [Cloud first applications](notes/cloud-first-applications.md)
  - [Machine Learning](notes/machine-learning.md)
  - [Security](notes/better-security-design.md)
- Minor Tips
  - [VLC Player](notes/vlc_player.md)
  - [Pandas](notes/pandas-tutorial.md)
  - [iOS Usage](notes/ios.md)
  - [Mosh](notes/mosh.md)
  - [USB Tech](notes/usbtech.md)
  - [Visual Vocabulary](notes/visual-vocabulary.md)
- Complete Projects
  - [Ring Video Downloader](notes/ring-video-download.md)
  - [Extract message history on OSX](notes/dump_imessage_history.md)
- In Progress Projects
    -  [Deploy a private web site](notes/private_web_site.md)
    -  [Windows Virtual Desktop](notes/virtual-desktops.md)
    -  [Alexa Skill](notes/alexa-skill.md)
    -  [ManageMe](https://github.com/idvorkin/manage-me)

<!-- prettier-ignore-start -->
<!-- vim-markdown-toc GFM -->

    - [Projects](#projects)
        - [To be started](#to-be-started)
        - [Not worth completing](#not-worth-completing)
        - [Too early to start](#too-early-to-start)
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
        - [Azure One Liners](#azure-one-liners)
            - [Deploy webapp via git checkin](#deploy-webapp-via-git-checkin)
        - [git](#git)
        - [Github](#github)
        - [SSH](#ssh)
        - [TMUX](#tmux)
        - [Random 1-liners](#random-1-liners)
        - [App Launchers](#app-launchers)
        - [Chrome extensions](#chrome-extensions)
        - [Web tools (http)](#web-tools-http)
        - [Video Editor](#video-editor)
- [The first -ss seeks fast to (approximately) 8min0sec, and then the second -ss seeks accurately to 9min0sec, and the -t 00:01:00 takes out a 1min0sec clip.](#the-first--ss-seeks-fast-to-approximately-8min0sec-and-then-the-second--ss-seeks-accurately-to-9min0sec-and-the--t-000100-takes-out-a-1min0sec-clip)
- [-c copy doesn't re-transcode so faster, but has problems since needs keyframes.](#-c-copy-doesnt-re-transcode-so-faster-but-has-problems-since-needs-keyframes)
- [ffmpeg -ss 00:08:00 -i $infile -ss 00:01:00 -t 00:01:00 -c copy $outfile](#ffmpeg--ss-000800--i-infile--ss-000100--t-000100--c-copy-outfile)
        - [Linters and formatters](#linters-and-formatters)
        - [Switching between Unix and DOS file ending](#switching-between-unix-and-dos-file-ending)

<!-- vim-markdown-toc -->
<!-- prettier-ignore-end -->

## Projects

### To be started


### Not worth completing

- [Redshift from Linqpad](notes/linqpad_from_redshift.md)

  Linqpad is awesome, but it'll be a while till I get back to an MS shop.

- [Debug clr using windbg](notes/windbg.md)

  I'm too old to pound on assembly language. Although I'm still proud of [this](http://ig2600.blogspot.com/2012/12/run-time-costs-of-small-operations-in-c.html)

### Too early to start

_The bleeding edge can be fun, but you burn lots of time dealing with sharp edges. Here's my list of things I want to get into once they stabilize._

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
Select every object in the array and string interpolates out object elements of name defaultHostName and appServicePlanId

    cat x.json | jq '.[] | "\(.defaultHostName) \(.appServicePlanId) "'

Read the Algolia key from my secretBox

    cat ~/gits/igor2/secretBox.json | jq '.AlgoliaKey'

List AWS lightsail properties

    saws> aws lightsail get-instances  | jq '.instances[] | .name, .state.name, .publicIpAddress'
    "Amazon_Linux-1GB-Oregon-1"
    "running"
    "54.190.183.299"

### Cool shell tools

Decent blog posts:

    https://remysharp.com/2018/08/23/cli-improved

- Tig - TUI git like git gui/gitk (Try tig status)
- Mosh - A better ssh
- w3m - Text based web browser
- fzf - Fuzzy file inder (Try C-R and C-T)
- Rg - RipGrep (like ag)
- [linuxbrew](http://linuxbrew.sh/) - Brew for linux
- Ngrok - Pipe ports to the internet web site (great for local host development on ios)
- [Bat](https://github.com/sharkdp/bat) - cat but with paging/git intgration.
- Pretty ping - Graphical Ping
- glances - Prettier Top
- iftop - Network based top based on network connection
- nethogs - Network based top based on process
- [fd](https://github.com/sharkdp/fd) - Better find/recurse.

### Natural Language Processing

- Rant - a cool c# human [language generator](http://berkin.me/rant/)
- Rhymebrain -
- Tranquil
- [Sentiment Analysis](notes/sentiment_analysis.md)

### Azure One Liners

#### Deploy webapp via git checkin

https://docs.microsoft.com/en-us/azure/app-service/deploy-local-git

1. Create the git credentials to deploy which gives a new git repro.
2. Add a git remote
3. Push to the git remote

### git

npx add-gitignore - update gitignore files

### Github

- Serve HTML files directly from github: https://rawgit.com/idvorkin/linqpadsnippets/master/js/DetectBackButton.html

- Keyboard shortcuts: https://help.github.com/articles/using-keyboard-shortcuts/

### SSH

Exit the ssh session (very helpful when stuck in a nested tmux session.

    <enter> ~ .

Connect on 8889 will get redirected to 8888 on the remote_host.

    # Connections on 4444 will get redirected to 8888 on the remote_host.
    ssh -N -L localhost:8888:localhost:4444 remote_user@remote_host

Use a tool to auto re-connect (MOSH should do this, but it's been flakey for me of late)

    autossh -M 0 server

### TMUX

This is so hard for me to remember:

Install tmuxp to re-create sessions.
Look at my config to see how to setup vi mode
Look at tmux plugin manager

https://gist.github.com/MohamedAlaa/2961058

- C-A w - See all windows and sessions.
- C-A \$ - rename session
- C-A , - rename windows
- C-A % - split left right
- C-A " - split top bottom
- C-A q - show pane #
- C-A <arrow> navigate panes
- C-A ? - list shortcuts (then search using / )
- C-A swap-window -t -1 -- Move window to the left
- C-A swap-window -t 0 -- Move window to the front

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
- Speed up YouTube playback via keyboard shortcut [YouTube playback speed control](https://chrome.google.com/webstore/detail/youtube-playback-speed-co/hdannnflhlmdablckfkjpleikpphncik)
- Fail to load dinosaur - Not an extension but you can play a little game with the dinosaur by pressing <space> on the chrome dinosaur

### Web tools (http)

httpie is like wget and curl, but easier to use.

Here's an example of sending content to a web hook which would send a message to chime. Notice -pHBhb prints request response, and Content is a JSON field.

    http -pHBhb POST https://hooks.chime.aws/incomingwebhooks/botaddress -- Content=We love PMs

### Video Editor

Decent cross plat video editors.

OpenShot - Video editor with good splicing.
[Lossless cutting](https://github.com/mifi/lossless-cut) - A tool to make lossless cuts.

ffmpeg recipes:

Convert video formats

    ffmpeg -i in.mov -qscale 0 -out.mp4

Trimming


    https://superuser.com/questions/138331/using-ffmpeg-to-cut-up-video As
    other people mentioned, putting -ss before (much faster) or after (more
    accurate) the -i makes a big difference. The section "Fast And Accurate
    Seeking" on the ffmpeg seek page tells you how to get both, and I have used
    it, and it makes a big difference. Basically you put -ss before AND after
    the -i, just make sure to leave enough time before where you want to start
    cutting to have another key frame. Example: If you want to make a 1-minute
    clip, from 9min0sec to 10min 0sec in Video.mp4, you could do it both
    quickly and accurately using:

    ffmpeg -ss 00:08:00 -i Video.mp4 -ss 00:01:00 -t 00:01:00 -c copy VideoClip.mp4


#The first -ss seeks fast to (approximately) 8min0sec, and then the second -ss seeks accurately to 9min0sec, and the -t 00:01:00 takes out a 1min0sec clip.
# -c copy doesn't re-transcode so faster, but has problems since needs keyframes.
#    ffmpeg -ss 00:08:00 -i $infile -ss 00:01:00 -t 00:01:00 -c copy $outfile

### Linters and formatters

You know what sucks less then coding standards? Arguing about coding standards. Nothing pains me more then arguing about formatting (and other minutia). As such I love having lint failures being build breaks and including formatting on save. Even better when you have [opinionated](https://stackoverflow.com/questions/802050/what-is-opinionated-software) formatters that don't have options. Sure standards suck, but they suck much less then arguing.

- Front End Stuff - [Prettier](https://prettier.io)
- Python - [Black](https://github.com/ambv/black)

### Switching between Unix and DOS file ending

(https://stackoverflow.com/questions/2466959/git-removing-carriage-returns-from-source-controlled-files)
On windows, when you switch between windows and WSL, you can get your line endings messed up in git.

To have git honor settings in the existing files set:

In: `~.gitconfig` set:

    core.autocrlf=input
    core.safecrlf=false

Sometimes your repo gets screwed up and needs to be fixed. In that case, erase all files, and recheckout.

    #!/bin/sh
    # remove local tree
    git ls-files -z | xargs -0 rm
    # checkout with proper crlf
    git checkout .

Also, can set a single file in vim by settings `set ff=unix`
