# Inbox

## Programas

- [VisiPics](http://www.visipics.info/index.php?title=Download): Para eliminar imágenes duplicadas (o parecidas).

- [Windows Update Blocker](https://www.sordum.org/9470/windows-update-blocker-v1-7/)

## Tools

- Regex for deleting block comments in Java: `/\*\*[\s\S\n]*?\*/`.

- Regex for lines ending witouth a finald dot: `^[^.]*[^.]$`.

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

## Notes assets naming style

```
[<type of note>]_<number of note>_<number of image>-<name of the image>
```

- Type of note.

    - $1$: a class note.

    - $2$: a workshop note.

## Summer meetings

### Meeting highlights

### 06/07/2024

1. Use Markdown to make your notes.

    Read the following articles to learn more about it:

    - [Getting Started](https://www.markdownguide.org/getting-started)

    - [Basic syntax](https://www.markdownguide.org/basic-syntax)

    > I recommend that you use the Visual Studio Code editor.

2. The book has some exercises at the end of the chapters, so I recommend that you install [Node](https://nodejs.org/en/download/prebuilt-installer) (runtime environment for JavaScript) your computer locally.

    > Sorry, I forgot to tell the most important part of the meeting.

3. Remember to post your doubts in the text channel of the Book.

4. Next meeting is to review the week's chapters and technical questions about Markdown and Node.

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
