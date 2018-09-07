# Text 101 - Text files

This course is all about editing text files. Before you start working with a text editor. Let's first focus, briefly, on the files part.

## Files

For now, let's make things super simple by saying this; there are two types of file: human-readable files and machine-readable files.

### Human readable files
Human readable (or text) files are files that, when opened with a text editor, return human readable text like the text you are reading now.

These are the type of files you can open with a tool like `vim` or `notepad`. You can also use them with programs such as `cat`.

### Machine readable files
Machine readable (or binary) files are files that, when opened with the right program, return instructions a computer can read and humans can't.

While it's still possible to show the file contents with `cat` or load a file in an editor like `vim`, the output will be an unreadable mess of seemingly random characters.

### Keep it simple, for now

Don't worry too much about it: simply remember that everything is either a text file or binary. *You* read the text files, your *computer* reads the binary files. That's it.

## Extensions

You might be used to working with files that have file extensios. Windows is an operating system that requires it's files to have file extensions.

On Linux and MacOS, it's still very much recommended that you make clever use of file extensions, however, they are not for the machine. They are there to make your life and your programs' life easier.

### For humans
By making use of file extensions, you, and the people you work with, have a much easier time finding out what a file might do.

A simple example would be the `.txt` extension.

Linux and MacOS do not require this extension to be there, so if we have a file `hello-world` containing a single line of text that says `hello world!` and use `cat` on it:
```bash
$ cat hello-world
hello world!
```

The main reason to add the extension would be clarity:
```bash
$ cat hello-world.txt
hello world!
```

Imagine an absolute beginner reading the previous example on a website or in a book: by adding the `.txt` extension, the purpose of `cat` gets clearer straight away.

By using the extensions, it also much easier to do something like this:
```bash
$ ls
hello-world.txt
hello-world.py
hello-world.htm
hello-world.css
hello-world.md
```

You can make up your own extensions if you feel the need to do this. However, because of practical reasons it's much easier to go with the agreed upon extensions.

Not only will this ensure that other programmers wil be able to understand your files much easier, it also helps out your programs.

### For programs

A lot of programs simply use the file extension to see what type of file they are operating on. Obvious use cases are `.jpg`, your graphical file manager knows to open image files in an image previewing program. Another example would be text editors/IDEs; they might change their behaviour depending on the type of file that is presented to them.

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
