# Text 103 - Emacs
## Description
> Emacs is a family of text editors that are characterized by their extensibility. The manual for the most widely used variant, GNU Emacs, describes it as "the extensible, customizable, self-documenting, real-time display editor" -Wikipedia

Read the entire [Wikipedia article](https://en.wikipedia.org/wiki/emacs) to learn all about the Church of Emacs, the editor wars and much more.

Simply put, Emacs is a text editor that comes with a lot of features and is extremely hackable.

The recommended text editor is Spacemacs, a 'configuration' (the developer calls it an 'Emacs distribution') for Emacs that changes and adds a lot of functionality and features (including Vim-like text editing) with a single git clone command.

Since Spacemacs is basically an Emacs configuration, most of Emacs' terminology still applies to Spacemacs, this article tries to cover all basic Emacs terminology one needs to use Spacemacs.

## Installation
MacOS user's should use Homebrew to install Emacs. First install Homebrew. Then run:
```
brew tap d12frosted/emacs-plus
brew install emacs-plus
brew linkapps emacs-plus
```
On Debian based Linux distros (like Ubuntu) run:
```
apt install emacs
```

## Configuration
Unless you want to use 'vanilla' Emacs, the only configuration you should be doing to Emacs is downloading Spacemacs.

> Note: running Emacs before downloading Spacemacs might create an Emacs folder that will prevent Spacemacs from being downloaded, so it's adviced not to run 'vanilla' Emacs if you do not yet fully grasp what you are doing.

## Usage
### Reading keyboard combinations
Emacs allows you to everything by pressing button combinations. Most documentation will describe these key combinations like this:
```
C-x C-c
```
or
```
M-!
```
Where the first 'C' in `C-x` stands for 'control' (as in, the keyboard button) and `x` stands simply for the 'x-button'. So, `C-c` stands for 'Control' *and* 'c'. `C-C` would stand for 'Control' *and* 'C' (so the 'shift' and 'c-button').

`M` stands for 'meta' which is 'alt'.

When you use Spacemacs, you will often see keyboard commands like:
```
SPC !
```
Where `SPC` stands for 'space' as in spacebar, `!` simply describes '!' as in 'shift' and '1' (on qwerty).

> Note: You do not have to hold 'space', like you have to hold down 'control' with the above commands. Notice how C-x means hold down 'control' and press 'x' and how SPC f f means press 'SPC', press 'f', press 'f' again. The dash (`-`) makes quite the difference.

### Terminology
If you have never worked with Emacs or Vim before and/or are new to the world of Unix, you will notice that some things have slightly different names than what you might be used to.

#### Frames and Windows
When describing what is happening on your screen, it's most likely that you would describe, say an open window of your webbrowser (that is currently visible on your screen), as a 'browser window'. The same probably goes for a file manager; a 'file manager window'. Because Emacs is so old, the phrasing is different, Emacs does not call an open Emacs 'window' a 'window', but rather a 'frame'. You should get used to this, because 'window' means something different in Emacs terminology.

Emacs can split it's screen into several spaces, these sperate spaces are refered to as 'windows', windows can have several sizes and functions and enable you to see different files or even different places in the same file at the same time.

#### Buffers and files
You are probably used to 'opening a document' with your text editor (or in general). In Emacs we can open so called 'buffers', a buffer can be displayed in a window. So a simple example of a buffer could be the contents of a text document. By having a buffer open, it means that you can display it's contents in Emacs, having a lot of open buffers comes basically down to the same things as having a bunch of files open in any other text editor.

It's noteworthy that a buffer can contain the contents of a file; a file can be loaded to a buffer, so you can work on the contents of this file. Changes can then be written back from the buffer to the actual file. However, it's also possible to have a buffer open that is not linked to a file; you could still write it's contents to a file, or simply choose to discard whatever the buffer is holding.

#### Cheat sheet

Frame = Emacs application window, you can have more than one of these if you want to.  
Window = Area to display buffer contents in, you can have several windows.  
Buffer = Basically the emacs word for 'open file'; as in, Emacs loads files into buffers, but saves buffers to files.

See the section on Spacemacs to get a more complete description of Spacemacs.

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
