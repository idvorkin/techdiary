So you want to be an iPad Developer Nomad. A person who can do all their development on the iPad. I'm not sure why you'd want to be such a charecter, in fact, I'm not sure why I want to be such a charector, but I do, and here's how I do it. To be a developer nomad, you better already be a command line wiz. If you're not at an expert at the terminal, vim or emacs and tmux - don't even try.

There are three paths - remote development, local development, and hybrid. For all of these you'll need an external keyboard, which I'll also discuss.

<!-- prettier-ignore-start -->
<!-- vim-markdown-toc GFM -->

- [Remote Development - Blink](#remote-development---blink)
    - [ssh super powers - port forwarding and tmux auto-attach.](#ssh-super-powers---port-forwarding-and-tmux-auto-attach)
- [Local Development - iSh, iVim, WorkingCopy, etc](#local-development---ish-ivim-workingcopy-etc)
    - [Run Linux - iSH](#run-linux---ish)
    - [Run Vim - iVIM](#run-vim---ivim)
    - [Run git - Working copy](#run-git---working-copy)
    - [Command line python](#command-line-python)
    - [Run Jupyter](#run-jupyter)
    - [Edit markdown](#edit-markdown)
- [The external keyboard.](#the-external-keyboard)
    - [Caps to Control](#caps-to-control)
    - [Back tick to escape.](#back-tick-to-escape)
- [General iOS Tips](#general-ios-tips)

<!-- vim-markdown-toc -->
<!-- prettier-ignore-end -->

### Remote Development - Blink

This is the easy way, but you're going to need a good low network latency.

First you need a remote box, I use lightsail. For 10\$ a month I've never run out of CPU or disk. Next you need to be able to connect to the box using SSH, and that requires an ssh client. I use [blink](https://blink.sh/) and couldn't be happier. Great product, great support.

#### ssh super powers - port forwarding and tmux auto-attach.

Beacuse ssh doesn't keep persistant sessions, I use tmux with an auto reattach script. If you're not doing this, go learn how it's awesome. You should also know about ssh [port forwarding](https://github.com/idvorkin/techdiary#ssh)

My [dotfiles](https://github.com/idvorkin/settings) should provide some insights on powerful command line tricks. For inspiration, here's what my tmux sessions look like (press [C-B w](https://github.com/idvorkin/Settings/blob/master/shared/.tmux.conf) to get this view)

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

(For folks that are considering [MOSH](https://mosh.org/), MOSH has great promise, but the project hasn't been updated in years, and still doesn't support true color. For my needs ssh+tmux+auto-reconnect is perfect.)

### Local Development - iSh, iVim, WorkingCopy, etc

Remote development is perfect, except of course when you have no and or slow network. At this point you need to get creative. Luckily, there has been lots of improvemnt in this space.

#### Run Linux - iSH

The holy grail. [iSH](https://iSH.app) takes a very impressive approach. And [tbodt](https://github.com/tbodt/) the author of iSH is incredibly cool, I have the utmost respect for his project and his style, and I even have his user name memorized.

iSH Creates an x86 emulated machine (e.g. simulate execution), and run alpine Linux in it. I love this but it has two big gaps. A) Compatibility B) Speed. There are still CPU instructions and system calls that aren't supported so large swaths of applications don't work - E.g. NPM, Rust. B) Because it's emulated it's slow, so I need to use trimmed down versions of all my configurations.

Net; net - with creativity you can get many thing working, it's just slow, sometimes so painfully slow you don't want to do it.

#### Run Vim - iVIM

[iVIM](https://github.com/terrychou/iVim) does a great job being VIM, but you tend not to use VIM in isolation, you need Git and Plugins and often some command line integration. There are workarounds, some of which painful, but I'll describe them here.

- git integration
- bundle integration
- opening files from other apps
- sharing files to other apps
- font management

#### Run git - Working copy

Working Copy - the best git (only?) git editor. It's truely fantastic.

- GitHawk

#### Command line python

#### Run Jupyter

#### Edit markdown

- Editorial - Markdown editor that can interact with Working Copy (seems nicer then Byword)
- Byword - Markdown editor that can interact with Working Copy

### The external keyboard.

You'll Keyboard remapping

#### Caps to Control

Finally, built into iOS 13.4

#### Back tick to escape.

The keyboard I use has backtick where escape should be. In VIM this is super painful iSH and blink have options to flip this. In iVIM you can do a key remap - e.g.

```
    :imap ` <C-[>
    :cmap ` <C-[>
```

- iVIM - VIM clone, slightly unstable but can open files from other apps (:idoc)

### General iOS Tips

You can see my general [iOS tips](notes/ios.md) as well.
