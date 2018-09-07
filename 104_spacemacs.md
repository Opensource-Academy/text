# Text 104 - Spacemacs
## Description
> A community-driven Emacs distribution -the [Spacemacs homepage](http://spacemacs.org/)

If you are looking for a text editor, Spacemacs is the recommended editor.

The Spacemacs homepage states "The best editor is neither Emacs nor Vim, it's Emacs and Vim!". This document aims to kickstart beginners, Vim veterans and Emacs experts.

Spacemacs can be used with Vim style text editing, this is the recommended mode (so called 'evil mode').

## Installation
On a machine that has git and Emacs 24.4 or higher on it, simply run the following command in a terminal:
```
git clone https://github.com/syl20bnr/spacemacs ~/.emacs.d
```
Otherwise, follow this [readme](https://github.com/syl20bnr/spacemacs) on installing both Emacs and downloading Spacemacs. Simply scroll down the page and follow the instructions for your operating system.

## Configuration
Spacemacs should be configured from it's so called 'dotfile', you can open the configuration file in Spacemacs with
```
SPC f e d
```

## Usage

### First run

Once Emacs was installed and Spacemacs was downloaded, when you first start Emacs, you should be greeted by the Spacemacs setup screen. The thing Spacemacs will do is ask you about your favourite editing style; it's
heavily recommended to go with the Vim or 'Evil' style (press `RET` to confirm your choice).

Press `RET` two more times to answer 'yes' to the next two questions to prepare Spacemacs to properly set itself up. Once you answered all questions Spacemacs will download a bunch of packages to finish installation, this only happens once after installation.

When Spacemacs is done, (it should state 'Spacemacs is ready'), you should restart Spacemacs, you can use the following command:
```
SPC q r
```

### States

When set up to use evil, Spacemacs behaves very much like Vim. It has a so called 'normal state', which has Vim style editing commands and has the leader key (see below) to perform actions or run commands. By pressing 'i'
while in 'normal state' Spacemacs will switch to 'insert state', in this state you can enter text like with a regular text editor. By pressing 'escape' (from now on refered to as ESC) you can switch back to 'normal state'.

### The leader key

Spacemacs is called spacemacs for a reason; it's heavily reliant on it's so called 'leader key', which, by default, is 'spacebar', or as it will be refered to from now on: `SPC`. Most actions that are not directly Vim commands can be launched by pressing a combination of keys that start of with `SPC`, usualy followed by 2 more key presses. For example, `SPC-q-q` exits Spacemacs.  
Press `ESC` to abort entering a command.
> Keep an eye on the bottom left of the Spacemacs frame to see what command is being entered and what output (if any) is returned.

### Helm

One of Spacemacs' most helpfull features is Helm, Helm is the overlay that shows up when you press `SPC`. Helm shows all keys that can be pressed after `SPC` was pressed. Because of this, you don't have to remember all keybindings. Because of the way Spacemacs was designed it's usualy not very hard to find what you want to do, once you get used to Unix/Emacs terminology, most key combination will come natural to you. Spacemacs also aims to be mnemonic with it's keybindings, that means that keys are set up in such a way that they are easy to remember, for example, to Save a File, press `SPC f s`. `SPC` to let Spacemacs know a command is coming, `f` for the file sub options and `s` to execute the save command.

### Window and buffer management

Windows and buffers can be fully managed through Helm, `SPC W [key]` for windows, `SPC B [key]` for buffers. Notice how a 'double entry' (e.g. `SPC w w` or `SPC b b`) has a 'common' feature under it; double presses are bound to features you might want to access really quickly, like switching between 2 active windows with `w` or showing the list of open buffers (and recent files) with `b`.

### Layers and packages

By pressing `SPC f e d` Spacemacs will display it's configuration file, however, some configuration will be automatically offered to you, for example, when opening a file.py or file.go Spacemacs will offer to download and activate the packages for Python and Go respectively. A collection of packages related to a certain task is called a 'layer'. For example, the Python layer comes with syntax checking and smart autocompletion (and much, much more).

From the configuration file you can activate even more packages, features that can be enabled include support for git, spell-checking, auto-completion, etc.

### SPC SPC

By pressing `SPC` twice, Spacemacs will go into a special command mode that enables you to run all possible commands your Spacemacs supports. This feature is very usefull for finding an option you expect Spacemacs to have, but you cannot find from Helm (not all Spacemacs commands are bound to key combinations).

#### Eshell

A noteworthy command to run from `SPC SPC` is `eshell`. Eshell is a terminal emulator inside of Spacemacs.

### SPC !

Pressing `SPC !` let's you enter bash commands!

### SPC h

`SPC h` opens the help tab, you can use `SPC h T` to start the `evil-tutor`, this is a text file designed for users that are new to Vim, talking them through how Vim style editing works.

### Finally

This document does not aim to describe every Spacemacs feature. Rather, it should serve as a starting point for getting used to working with Spacemacs. Starting out with Evil without any previous Vim experience can be slightly disheartening, however, by pulling through for a few days the benefits of Vim style editing should soon become apparent. Spacemacs is also designed to be quite starter friendly, exploring all the features through Helm can be a lot of fun and very rewarding.

```
   Copyright 2018 Opensource Academy

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```
