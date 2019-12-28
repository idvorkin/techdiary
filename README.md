# Igor's Technical Diary
## Projects

### To be started

### Not worth completing

- [Redshift from Linqpad](notes/linqpad_from_redshift.md)

  Linqpad is awesome, but it'll be a while till I get back to an MS shop.

- [Debug CLR using windbg](notes/windbg.md)

  I'm too old to pound on assembly language. Although I'm still proud of [this](http://ig2600.blogspot.com/2012/12/run-time-costs-of-small-operations-in-c.html)

### Too early to start

_The bleeding edge can be fun, but you burn lots of time dealing with sharp edges. Here's my list of things I want to get into once they stabilize._

## Awesome Lists

### Markdown
### VIM
### C Sharp

### Java
### Python
### Typescript

- [Quick Type](https://quicktype.io/?l=cs&r=json2csharp) Create classes from JSON

### Apple

- Copy files **without** iTunes - [CopyTrans Manager](https://www.copytrans.net/copytransmanager/)

### Home Automation

- Bridge from HomeKit to Wink - [Homebridge-wink3](https://github.com/sibartlett/homebridge-wink3)

### Powershell
<!-- vim-markdown-toc GFM -->

- [Text manipulation tools](#text-manipulation-tools)
    - [jq](#jq)
- [Cool shell tools](#cool-shell-tools)
- [Natural Language Processing](#natural-language-processing)
- [Azure One Liners](#azure-one-liners)
    - [Deploy webapp via git checkin](#deploy-webapp-via-git-checkin)
- [git](#git)
- [GitHub](#github)
- [SSH](#ssh)
- [TMUX](#tmux)
- [Random 1-liners](#random-1-liners)
- [App Launchers](#app-launchers)
- [Chrome extensions](#chrome-extensions)
- [Web tools (http)](#web-tools-http)
- [Video Manipulation Tools](#video-manipulation-tools)
- [Linters and formatters](#linters-and-formatters)
- [Switching between Unix and DOS file ending](#switching-between-unix-and-dos-file-ending)
- [Spelling](#spelling)
- [PlantUML](#plantuml)
    - [PlantUML Tools](#plantuml-tools)
    - [PlantUML in Markdown](#plantuml-in-markdown)
    - [Quirks:](#quirks)

<!-- vim-markdown-toc -->
### Text manipulation tools

- XPath and HtmlAgilityPack
- Regexp + VIM
- Beautiful soup

#### jq

jq is the JavaScript equivalent of regexp
I'm very enamored with it!

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

- Tig - TUI git like git GUI/gitk (Try tig status)
- Mosh - A better ssh
- w3m - Text based web browser
- fzf - Fuzzy file finder (Try C-R and C-T)
- Rg - RipGrep (like ag)
- [linuxbrew](http://linuxbrew.sh/) - Brew for Linux
- Ngrok - Pipe ports to the internet web site (great for local host development on iOS)
- [Bat](https://github.com/sharkdp/bat) - cat but with paging/git integration.
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

1. Create the git credentials to deploy which gives a new git repository.
2. Add a git remote
3. Push to the git remote

### git

npx add-gitignore - update gitignore files

### GitHub

- Serve HTML files directly from GitHub: https://rawgit.com/idvorkin/linqpadsnippets/master/js/DetectBackButton.html

- Keyboard shortcuts: https://help.github.com/articles/using-keyboard-shortcuts/

### SSH

Exit the ssh session (very helpful when stuck in a nested tmux session.

    <enter> ~ .

Connect on 8889 will get redirected to 8888 on the remote_host.

    # Connections on 4444 will get redirected to 8888 on the remote_host.
    ssh -N -L localhost:8888:localhost:4444 remote_user@remote_host

Use a tool to auto re-connect (MOSH should do this, but it's been flaky for me of late)

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
- C-A x - kill-pane

Tmux command line

Re-attach to current session

    tmux attach

Force resize to current terminal size while reattaching

    tmux attach -d

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

### Video Manipulation Tools

Decent cross plat video editors.

- [OpenShot](https://www.openshot.org/) - Video editor with good splicing.
- [Lossless cutting](https://github.com/mifi/lossless-cut) - A tool to make lossless cuts.

ffmpeg recipes:

Convert video formats

    ffmpeg -i in.mov -qscale 0 -out.mp4

Trimming

https://superuser.com/questions/138331/using-ffmpeg-to-cut-up-video As other people mentioned, putting -ss before (much faster) or after (more accurate) the -i makes a big difference. The section "Fast And Accurate Seeking" on the ffmpeg seek page tells you how to get both, and I have used it, and it makes a big difference. Basically you put -ss before AND after the -i, just make sure to leave enough time before where you want to start cutting to have another key frame. Example: If you want to make a 1-minute clip, from 9min0sec to 10min 0sec in Video.mp4, you could do it both quickly and accurately using:

    ffmpeg -ss 00:08:00 -i Video.mp4 -ss 00:01:00 -t 00:01:00 -c copy VideoClip.mp4

The first -ss seeks fast to (approximately) 8min0sec, and then the second -ss seeks accurately to 9min0sec, and the -t 00:01:00 takes out a 1min0sec clip. -c copy doesn't re-transcode so faster, but has problems since needs key frames.

    ffmpeg -ss 00:08:00 -i $infile -ss 00:01:00 -t 00:01:00 -c copy $outfile

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

Sometimes your repository gets screwed up and needs to be fixed. In that case, erase all files, and re checkout.

    #!/bin/sh
    # remove local tree
    git ls-files -z | xargs -0 rm
    # checkout with proper crlf
    git checkout .

Also, can set a single file in vim by settings `set ff=unix`

### Spelling

Command line spelling. Ispell has nicer word highlighting, but aspell is supposed to have better spelling correction.

aspell
ispell

(Bragging - I fixed aspell highlighting in WSL)
https://github.com/GNUAspell/aspell/issues/590
https://github.com/Homebrew/homebrew-core/pull/48163

### PlantUML

#### PlantUML Tools

- [PlantText](https://www.planttext.com/) Interactive editor with vi-keybindings, but needs a manual refresh
- [LiveUML](https://liveuml.com/) - Interactive editor with auto-refresh
- VS Code has a great plugin for PlantUML
- Vim has a PlantUML preview in ASCII

#### PlantUML in Markdown

You can't directly render PlantUML in Markdown, but you can render images, and get PlantUML to load content from file. E.g:

http://www.plantuml.com/plantuml/proxy?idx=0&format=svg&src=**URL_with_uml_file**&cache_buster=**increment_to_avoid_caching**

Store your PlantUML file somewhere - e.g.

[https://raw.github.com/idvorkin/techdiary/master/sample_diagrams.puml](https://raw.githubusercontent.com/idvorkin/techdiary/master/sample_diagrams.puml)

Then render it like an image e.g.

    ![UML rendered](http://www.plantuml.com/plantuml/proxy?idx=0&format=svg&src=https://raw.githubusercontent.com/idvorkin/techdiary/master/sample_diagrams.puml&c=1)

![UML rendered](http://www.plantuml.com/plantuml/proxy?idx=0&format=svg&c=4&src=https://raw.githubusercontent.com/idvorkin/techdiary/master/sample_diagrams.puml)

#### Quirks:

- GitHub caches, so increment the c parameter
- PlantUML doesn't support https (really??) so the PlantUML server URL needs to be **http** (not https).
- The image URL uses http, and VS Code preview doesn't allow loading things over http by default, so click that 'insecure content' button to allow rendering in unsafe mode (ugh)
