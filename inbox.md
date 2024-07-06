# Inbox

## Programas

- [VisiPics](http://www.visipics.info/index.php?title=Download): Para eliminar imágenes duplicadas (o parecidas).

- [Windows Update Blocker](https://www.sordum.org/9470/windows-update-blocker-v1-7/)

## Tools

- Regex for deleting block comments in Java: `/\*\*[\s\S\n]*?\*/`.

- Regex for lines ending witouth a finald dot: `^[^.]*[^.]$`.

- Regex for two or more spaces between words: ` {2,}`.

- Regex por comas without ONLY a blank space: `,[^\s]`.

- Regex for comments without the beginning space: `[^\s]\\\\`

`[^\s-]\(`

- Search for spaces in:

    - `for(`.
    - `while(`
    - `switch(`
    - `if(`.
    - `}else`
    - `){`.

## Useful commands

- Convert PNG to JPG: `magick mogrify -format jpg <PNG file>`.

‘’
“”

- Login error: `faillock --user <user> --reset`.

- Find files except in a directory: `find . -name <dir> -type d -prune -o -type f -name <file pattern> -print`.

- Create symbolic links (PowerShell): `New-Item -ItemType SymbolicLink -Path <target> -Value <source>`.

- Show disk usage in order: `du -h --max-depth=5 / 2>/dev/null | sort -h`.

## Plex

- Start service: `sudo systemctl start plexmediaserver.service`.

- Actual running config file: `/etc/systemd/system/plexmediaserver.service.d/override.conf`.

- Edit service config: `sudo systemctl edit plexmediaserver.service`.

`export DISPLAY=127.0.0.1:0`

## Web petitions with `curl`

- `curl -X POST -H "Content-Type: application/json" -d @petition.json https://api.example.com/upload`

    > `-H` is to specify a header.

## Linux applications that I use

- `neovim`.

- `discord`.

- `discord-compose`.

- `bat`.

- `lsd`.

---

## Folders to check

- `D:\education`.

- `D:\education\books`.

- `D:\education\short_and_interesting_PDF`.

- `D:\education\University\semesters`.

- `D:\music`.

- `D:\VFX_resources`.

## Summer meetings message

Hi, this message is to remaind the suggestion I made about reading the following material in your vacation:

- [Eloquent JavaScript](https://eloquentjavascript.net).

- [The Linux Command Line](https://www.linuxcommand.org/tlcl.php).

I have these books pending, so I plan to review them in short meetings with my students (you are one of them), I would like to ask you if you will have availability for it. If the answer is "yes", would you agree to my adding you to a WhatApp group to plan the meetings?

> If you are not available for the meeting, I recommend that you consult these resources. They will be very useful to you in the future (at least they have been to me).

## Summer meetings

### Eloquent JavaScript topics

In total there are 21 chapters of the book (22 including the introduction), considering that our vacation ends on August 12, we have 6 (starting from this week) weeks to read the book, that means we should read 4 chapters per week.

#### Part 1: Language

01. Values, types, and operators.
02. Program structure.
03. Functions.
04. Data structures: objects and arrays.
05. Higher-order functions:
06. The secret life of objects.
07. Project: A Robot.
08. Bugs and errors.
09. Regular expressions.
10. Modules.
11. Asynchronous programming.
12. Project: A Programming Language.

#### Part 2: Browser

1. JavaScript and the browser.
2. The Document Object Model (DOM).
3. Handling events.
4. Project: A Platform Game.
5. Drawing on canvas.
6. HTTP and forms
7. Project: A Pixel Art Editor

#### Node.js (Node)

1. Node.js.
2. Project: Skill-Sharing Website.

The chapters __underline__ chapters are pending and the chapters in ~~strike-through~~ are those that have been read.

## The Linux Command Line

1. What is the Shell?
2. Navigation.
3. Exploring the system.
4. Manipulating files and directories.
5. Working with commands.
6. Redirection.
7. Seeing the world as the Shell sees it.
8. Advanced keyboard tricks.
9. Permissions.
10. Processes.
11. The environment.
12. A gentle introduction to vi.
13. Customizing the prompt.
14. Package management.
15. Storage media.
16. Networking.
17. Searching for files.
18. Archiving and backup.
19. Regular expressions.
20. Text processing.
21. Formatting output.
22. Printing.
23. Compiling programs.
24. Writing your first script.
25. Starting a project.
26. Top-Down design.
27. Flow Control: Branching with if.
28. Reading Keyboard Input.
29. Flow Control: Looping with while / until.
30. Troubleshooting.
31. Flow Control: Branching with case.
32. Positional Parameters.
33. Flow Control: Looping with for.
34. Strings and Numbers.
35. Arrays.
36. Exotica.
