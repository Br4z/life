# Inbox

## Programas

- [VisiPics](http://www.visipics.info/index.php?title=Download): para eliminar imagenes duplicadas (o parecidas).

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

## Useful commands

- Convert PNG to JPG: `magick mogrify -format jpg <PNG file>`.

- Login error: `faillock --user <user> --reset`.

- Find files except in a directory: `find . -name <dir> -type d -prune -o -type f -name <file pattern> -print`.

- Create symbolic links (PowerShell): `New-Item -ItemType SymbolicLink -Path <target> -Value <source>`.

- Show disk usage in order: `du -h --max-depth=5 / 2>/dev/null | sort -h`.

- Compile and run Scala programs.

    ```POWERSHELL
    scalac -d out $(Get-ChildItem -Filter "*.scala" -Recurse)
    scala -classpath .\out\ .\Main.scala
    ```

- Compile C++ programs: `find . -name "*.cpp" -type f -print0 | xargs -0 g++`.

- Paint image in white: `convert input.png -fill white -colorize 100% output.png`.

## Plex

- Start service: `sudo systemctl start plexmediaserver.service`.

- Actual running config file: `/etc/systemd/system/plexmediaserver.service.d/override.conf`.

- Edit service config: `sudo systemctl edit plexmediaserver.service`.

## Folders to check

- `D:\education`.

- `D:\education\books`.

- `D:\education\short_and_interesting_PDF`.

- `D:\education\University\semesters`.

- `D:\music`.

- `D:\VFX_resources`.

---

```
‘’
“”
```
