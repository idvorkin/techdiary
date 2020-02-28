I spent a **LOT** of time on my iPhone/iPad - here are some of the tools/tips I use.

<!-- prettier-ignore-start -->
<!-- vim-markdown-toc GFM -->

- [General](#general)
    - [Global Controls (For iPhone X)](#global-controls-for-iphone-x)
    - [Siri (For iPhone X)](#siri-for-iphone-x)
    - [HomeKit](#homekit)
    - [Health Kit](#health-kit)
    - [Photos](#photos)
- [Apps](#apps)
    - [All](#all)
    - [Chrome](#chrome)
    - [Launcher](#launcher)
    - [Workflow](#workflow)
- [Watch](#watch)
- [Augmented Reality Apps](#augmented-reality-apps)
- [Pen](#pen)
    - [Notability](#notability)
    - [Notes Plus](#notes-plus)
    - [OneNote](#onenote)
    - [Adobe Sketch](#adobe-sketch)
    - [Inkflow](#inkflow)
    - [Nebo](#nebo)
    - [Keyboards](#keyboards)
- [Development](#development)
    - [Keyboard remapping](#keyboard-remapping)
        - [Caps to Control](#caps-to-control)
        - [Back tick to escape.](#back-tick-to-escape)
    - [Ssh to another box - Blink](#ssh-to-another-box---blink)
    - [Run Linux on your iOS device](#run-linux-on-your-ios-device)
    - [To be filed](#to-be-filed)

<!-- vim-markdown-toc -->
<!-- prettier-ignore-end -->

## General

### Global Controls (For iPhone X)

- Goto Launcher - Right Ear -> Swipe Right
- Goto Control Panel - Left Ear -> Mid screen
- Screen Capture - Power and Volume Up
- Screen Capture Video - Control Panel Round dot (enable through configuration)
- Siri -> Hold Power
- Hey Siri -> A better way to launch Siri
- Scroll to top of page -> press on time
- Reboot -> Volume up then Volume down, then press side button for 10 seconds.

### Siri (For iPhone X)

tbd

### HomeKit

tbd

### Health Kit

- [QS Access](https://itunes.apple.com/us/app/qs-access/id920297614?mt=8) - Allow you to export your health data in tabular format - pretty nice.
- Sleep cycle - Smart wake up alarm.
- Heart Watch - Crazy level of detail on your heart rate.
- Auto Sleep - Watch based sleep tracking.

### Photos

- Take picture by pressing volume up.
- Hey Siri take a selfie
- App: LightX

## Apps

### All

- Just press record - Keep full voice recording (not just transcription)
- Fantastical - Best Calendar app - period.
- Magic Launcher - Cool idea, app launch from widget menu.
- Dark Sky - Micro weather
- Bear - Writing tool
- LightX - photo editor with magic wand.

### Chrome

I use chrome instead of safari since it synchronizes my passwords and my open tabs. Chrome gestures:

Gestures:

Back/Forward - Swipe Left/Right from page edge
Switch tabs - Swipe Left/Right on address bar.
Refresh Tab - Pull top of page down.
Close Tab - Pull top of page down and to right
New Tab - Pull top of page down and to left

Keyboard: Test if these work
https://productforums.google.com/forum/#!topic/chrome/fiR1lQ0mpbw;context-place=forum/chrome

### Launcher

A launch center which can execute URLs best use case is from a today widget.

### Workflow

Automate common tasks - like send text to person (which can be added as a share extension) and send last screen shot to person. Can also add "shortcuts" to launcher.

## Watch

Here are my favorite watch apps:

Next appointment - Fantastical
Exercise/Heart rate monitor - Heart Watch
Smart Wake up - Auto Wake
Weather - Dark Sky

A great feature on the watch folks don't know about is multiple watch faces. I use one face for off work (photos), one for work (calendar view), and one for sleeping (smart alarm clock view)

## Augmented Reality Apps

- IKEA: Put IKEA furniture in your room.
- Magic Plan: Determine floor plan interactively.
- Light-Space: Paint in AR
- AR Dragon: Play with a toy dragon

## Pen

### Notability

- My recommended writing application.
- Synchronized audio playback and writing
- Nice iCloud syncing
- Google Drive PDF creation
- Excellent Hand Writing Recognition and search.
- Side by side page view

### Notes Plus

I now recommend using Notability, however a few places where Notes Plus still has superior features:

- Prettiest Render
- Smart Gestures (Scratch to erase, deduce shape)

### OneNote

- Best cross platform app
- Hand writing in native, but it's meh compared to the others

### Adobe Sketch

- My favorite drawing app - nice intuitive controls
- Nice ink

### Inkflow

- I haven't actually used it, but apparently it can turn photos into vector graphics (pretty cool)

### Nebo

- Augmented drawing. Cool idea you can draw connected diagrams and move them around, but it feels great for a demo, but doesn’t actually work well yet.

### Keyboards

- Google Keyboard - lets you use a swype like gesture
- Stylus - lets you write by actually writing on the screen (similar to windows ink)

## Development

### Keyboard remapping

#### Caps to Control

Finally, built into iOS 13.4

#### Back tick to escape.

The keyboard I use has backtick where escape should be. In VIM this is super painful iSH and blink have options to flip this. In iVIM you can do a key remap - e.g.

```
    :imap ` <C-[>
    :cmap ` <C-[>
```

### Ssh to another box - Blink

Great SSH client. Because ssh is not persistent, you probably want an ssh session that auto re-attaches to TMUX [tbd].

What about MOSH? MOSH has great promise, but the project hasn't been updated in years, and still doesn't support true color. I use ssh with an auto TMUX reconnect in stead.

### Run Linux on your iOS device

The holy grail. [iSH](https://iSH.app) takes a very impressive approach. And TK The author of iSH is incredibly cool, I have the utmost respect for his project and his style.

iSH Creates an x86 emulated machine (e.g. simulate execution), and run alpine Linux in it. I love this but it has two big gaps. A) Compatibility B) Speed. There are still CPU instructions and system calls that aren't supported so large swaths of applications don't work - E.g. NPM, Rust. B) Because it's emulated it's slow, so I need to use trimmed down versions of all my configurations.

### To be filed

- Working Copy - the best git (only?) git editor
- Editorial - Markdown editor that can interact with Working Copy (seems nicer then Byword)
- Byword - Markdown editor that can interact with Working Copy
- iVIM - VIM clone, slightly unstable but can open files from other apps (:idoc)
