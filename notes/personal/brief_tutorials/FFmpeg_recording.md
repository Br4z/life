# FFmpeg recording

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
