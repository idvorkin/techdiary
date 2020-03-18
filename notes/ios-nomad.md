# iOS Software engineer nomad howto

_Please add comments [here](https://hackmd.io/Z_2EucqOQnaoHq2KxRwlEw)_

So you want to be an iPad Developer Nomad. A person who can do all their development on the iPad. I'm not sure why you'd want to be such a character, in fact, I'm not sure why I want to be such a character, but I do, and here's how I do it. To be a developer nomad, you better already be a command line wiz. If you're not at an expert at the terminal, vim or Emacs and TMUX - don't even try.

There are three paths - remote development, local development, and hybrid. For all of these you'll need an external keyboard, which I'll also discuss.

<!-- prettier-ignore-start -->
<!-- vim-markdown-toc GFM -->

- [Remote Development - Blink](#remote-development---blink)
    - [ssh super powers - port forwarding and TMUX auto-attach.](#ssh-super-powers---port-forwarding-and-tmux-auto-attach)
- [Local Development - iSh, iVIM, Working Copy, etc](#local-development---ish-ivim-working-copy-etc)
    - [Run Linux - iSH](#run-linux---ish)
    - [Run git - Working copy](#run-git---working-copy)
    - [Run Vim - iVIM](#run-vim---ivim)
    - [Run python - Pythonista](#run-python---pythonista)
    - [Run Jupyter - Carnets](#run-jupyter---carnets)
    - [Edit markdown](#edit-markdown)
- [Hybrid development - Consistency](#hybrid-development---consistency)
- [The external keyboard.](#the-external-keyboard)
    - [The keyboard I use](#the-keyboard-i-use)
    - [The iPad stand I use](#the-ipad-stand-i-use)
    - [Caps to Control](#caps-to-control)
    - [Back tick to escape.](#back-tick-to-escape)
    - [Carrying bags](#carrying-bags)
- [Related links](#related-links)

<!-- vim-markdown-toc -->
<!-- prettier-ignore-end -->

### Remote Development - Blink

This is the easy way, but you're going to need a good low latency network.

First you need a remote box, I use lightsail. For 10\$ a month I've never run out of CPU or disk. Next you need to be able to connect to the box using SSH, and that requires an ssh client. I use [blink](https://blink.sh/) and couldn't be happier. Great product, great support.

#### ssh super powers - port forwarding and TMUX auto-attach.

Because ssh doesn't keep persistent sessions, I use TMUX with an auto reattach script. If you're not doing this, go learn how it's awesome. You should also know about ssh [port forwarding](https://github.com/idvorkin/techdiary#ssh)

My [dot files](https://github.com/idvorkin/settings) should provide some insights on powerful command line tricks. For inspiration, here's what my TMUX sessions look like (press [C-B w](https://github.com/idvorkin/Settings/blob/master/shared/.tmux.conf) to get this view)

```
(0)   - main: 6 windows (attached)
(1)   ├>   0: vim* (1 panes) "ip-172-26-8-55"
(2)   ├>   1: zsh- (1 panes) "ip-172-26-8-55"
(3)   ├>   2: glances (1 panes) "ip-172-26-8-55"
(4)   ├> + 3: ntop (2 panes)
(5)   ├>   7: zsh (1 panes) "ip-172-26-8-55"
(6)   - servers: 3 windows
(7)   ├> 0: jekyll blog* (1 panes) "ip-172-26-8-55"
(8)   ├> 1: techdiary grip- (1 panes) "ip-172-26-8-55"
(9)   └> 2: jupyter serve (1 panes) "ip-172-26-8-55"

```

(For folks that are considering [MOSH](https://mosh.org/), MOSH has great promise, but the project hasn't been updated in years, and still doesn't support true color. For my needs ssh+TMUX+auto-reconnect is perfect.)

### Local Development - iSh, iVIM, Working Copy, etc

Remote development is perfect, except of course when you have no and or slow network. At this point you need to get creative. Luckily, there has been lots of improvement in this space.

#### Run Linux - iSH

The holy grail. [iSH](https://iSH.app) takes a very impressive approach. And [tbodt](https://github.com/tbodt/) the author of iSH is incredibly cool, I have the utmost respect for his project and his style, and I even have his user name memorized.

iSH Creates an x86 emulated machine (e.g. simulate execution), and run alpine Linux in it. I love this but it has two big gaps. A) Compatibility B) Speed. There are still CPU instructions and system calls that aren't supported so large swaths of applications don't work - E.g. NPM, Rust. B) Because it's emulated it's slow, so I need to use trimmed down versions of all my configurations.

When your software can run iSH, and is fast enough, you're done. However because of the compatibility and speed concerns, you'll often need other solutions to augment iSH. Here are the ones I use

#### Run git - Working copy

Working Copy - the best git client for iOS, it's truly fantastic. So many features you should read the documentation as carefully as you would for TMUX.

Even though it's graphical it can be automated because it exposes iOS APIs via URL that other tools (like VIM) can execute. Super cool.

Example callbacks I use are:

Pull All Repos:

    working-copy://x-callback-url/pull?key=secret&repo=%2A

A cousin to Working Copy is Git Hawk this tool allows you to monitor your GitHub messages.

#### Run Vim - iVIM

[iVIM](https://github.com/terrychou/iVim) does a great job being VIM, but you tend not to use VIM in isolation, you need Git and Plugins and often some command line integration. There are workarounds, some of which painful, but I'll describe them here.

- git integration

This is a bizarre, but surprisingly effective technique. While iVIM can't run git, Working Copy can create a directory it has access to in another app (like iVIM), and execute git commands on it.

The approach here is you setup git repositories into iVIM (working copy calls these TK), then you set the remote of the synced directory to be the git target you want (e.g. github.com/idvorkin/settings). Then every time you want to use git commands, you flip to working copy, and it just works. Given how hacky this sound it works amazingly well.

- bundle/plugin integration

This is painful as most plugin managers execute git behind the covers. To get this to work you need to copy your bundle directory into iVIM using the iOS Files app. For some reason, when I try this it fails.

An alternative I'm planning on trying is git TK

Now because iVIM doesn't support git you need to use Working Copy, and so far that has worked well.

- opening files from other apps

This works decently, you the :idocu command to get the iOS File Picker and then choose files from other apps.

- sharing files to other apps

This works very well, use the share to and you're done.

- font management

While not apple UI friendly it's supported use the :ifont command, e.g.:

    :ifont 0 4

#### Run python - Pythonista

#### Run Jupyter - Carnets

#### Edit markdown

- Editorial - Markdown editor that can interact with Working Copy (seems nicer then Byword)
- Byword - Markdown editor that can interact with Working Copy
- MWeb - Markdown editor that can interact with Working Copy

### Hybrid development - Consistency

What is hybrid development? It's remote development when you've got the network and local development when you don't. This model is similar to having to work on multiple machines at the same time.

The main complexity with hybrid development is keeping everything in sync. To do this I keep everything in git, and then run a cron job that's pushing and pulling continuously. My cron job approach is:

https://github.com/idvorkin/Settings/blob/master/shared/cron_git_sync.sh

The two gaps here are merge conflicts (which I handle manually), and not syncing on my iPad, which is tricky because I haven't found a way to do a periodic timer to arbitray command execution yet (TK: Holler if you have a good way to do this)

### The external keyboard.

#### The keyboard I use

I'm a huge fan of ergo keyboards. iClever makes a [cheap folding ergo Bluetooth keyboard](https://www.amazon.com/dp/B01JA6HG88/) that support up to 3 devices. I prefer this to all my laptop keyboards.

#### The iPad stand I use

Getting a good stand is hard and I'm constantly iterating.

For places I use my iPad a lot at home I use this [ergo monitor arm equivalent](https://www.amazon.com/gp/product/B074PFVVBH/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1). It lets you position your relatively heavy iPad into any position or orientation.

For remote use, I want something that is light and fits in my bag. I've tried slews of stands and I dislike all of them. I'm currently using the [moko folding](https://www.amazon.com/gp/product/B017TU2WGS/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) , which I'm not thrilled with, but best I've found.

#### Caps to Control

Finally, built into iOS 13.4

#### Back tick to escape.

The keyboard I use has backtick where escape should be. In VIM this is super painful iSH and blink have options to flip this. In iVIM you can do a key remap - e.g.

```
    :imap ` <C-[>
    :cmap ` <C-[>
```

#### Carrying bags

Slightly off topic, but if you made it this far, you probably care about small bags as well.

It's taken me several tries, but [I've concluded](/notes/irl.md#work-bag) I like the smallest bag possible. I use a 13" macbook pro laptop and an iPad Pro 10" and this is the perfect bag for me:

https://www.amazon.com/gp/product/B07WNPPF72

There's also the horizontal version - which is slightly bigger but also nice:

https://www.amazon.com/gp/product/B07H4QYC2D/

### Related links

- My general [iOS tips](notes/ios.md).
- [Automating iOS](https://www.macstories.net/stories/automating-ios-how-pythonista-changed-my-workflow/)
- [x-callback-urls for OmniFocus](https://inside.omnifocus.com/url-schemes)
