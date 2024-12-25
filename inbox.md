# Inbox

## Programas

- [VisiPics](http://www.visipics.info/index.php?title=Download): Para eliminar imagenes duplicadas (o parecidas).

- [Windows Update Blocker](https://www.sordum.org/9470/windows-update-blocker-v1-7/)

## Tools

- Regex for deleting block comments in Java: `/\*\*[\s\S\n]*?\*/`.

- Regex for lines ending witouth a finald dot: `[^\.$:\]?]$`.

- Regex for comments without the beginning space: `[^\s]\\\\`

- Search for spaces in:

    - `for(`.
    - `while(`
    - `switch(`
    - `if(`.
    - `}else`
    - `){`.

    ```
    (for\()|(while\()|(switch\()|(if\()|(\}else)|(\)\{)
    ```

## Regex for checking notes

```
([^\.:\]?]$)|(^(?! ).* {2,})|(\{[^\s])|([^\s]\})
```

```
(\d[^ )\d.$])|
```

## Useful commands

- Convert PNG to JPG: `magick mogrify -format jpg <PNG file>`.

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

## Folders to check

- `D:\education`.

- `D:\education\books`.

- `D:\education\short_and_interesting_PDF`.

- `D:\education\University\semesters`.

- `D:\music`.

- `D:\VFX_resources`.

## Summer meetings

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

```
find . -name "*.cpp" -type f -print0 | xargs -0 g++

convert input.png -fill white -colorize 100% output.png

‘’
“”

scalac -d out $(Get-ChildItem -Filter "*.scala" -Recurse)
scala -classpath .\out\ .\Main.scala
```
