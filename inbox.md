# Inbox

## Programas

- [VisiPics](http://www.visipics.info/index.php?title=Download): Para eliminar imágenes duplicadas (o parecidas).
- [Windows Update Blocker](https://www.sordum.org/9470/windows-update-blocker-v1-7/)

## ICM profile

Luego de conseguir el ICM hacemos lo siguiente:

1. Nombrar el perfil descargado con un nombre significativo (puedo sugerir un formato `Monitor brand - Monitor model`).

2. Instalar el perfil descargado (clic derecho e instalar).

3. Ir a "Administración de color".

4. En dispositivo seleccionar tu monitor y activar la casilla de "Usar mi configuración para este dispositivo".

    1. Da clic en agregar y selecciona el perfil instalado.

    2. Cuando aparezca en la lista, selecciónalo y haz clic en usar como perfil predeterminado.

        1. Vete al apartado de opciones avanzadas y activa la calibración de Windows.

            > En el apartado de "Cambiar los valores predeterminados del sistema..." se te desplegará un menú idéntico, en el que ya podrás marcar la casilla.

5. Cierra el menú y los cambios ya estarán aplicados.

> Si quieres estar seguro en el apartado Sistema >> Pantalla en configuración encontrarás el perfil de color que actualmente usas.

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

## Recording with FFmpeg

- List devices: `ffmpeg -list_devices true -f dshow -i dummy`.

- Desktop.

    - Recording: `ffmpeg -f gdigrab -framerate 30 -i desktop -f dshow -i audio="<mic name>" -c:v <codec name>  -qp 0 <output file name with extension>`.

        - AMD.

            - Available codecs.

                - "h264_amf".

                - "hevc_amf".

        - Nvidia.

            - Available codecs.

                - "h264_nvenc".

                - "nvenc_hevc.

    For a basic recording, just omit the `-c` and `-qp` flag (`ffmpeg -f gdigrab -framerate 30 -i desktop -f dshow -i audio="<mic name>" output_test.mp4`).

    > For more information, see the [documentation](https://trac.ffmpeg.org/wiki/Capture/Desktop#Windows).

- Webcam.

    - List device options: `ffmpeg -list_options true -f dshow -i video=<webcam camera>`.

    - Recording: `ffmpeg -f dshow -video_size <resolution> -framerate <framerate> -i video="<webcam camera>":audio="<webcam mic" <output file name with extension>`.

    > For more information, see the [documentation](https://trac.ffmpeg.org/wiki/Capture/Webcam#Windows).

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

```BASH
for file in *.md; do
    mv -- "$file" "${file%.txt}_pending.md"
done
```

## Folders to check

- `D:\education`.

- `D:\education\books`.

- `D:\education\short_and_interesting_PDF`.

- `D:\education\University\semesters`.

- `D:\music`.

- `D:\VFX_resources`.
