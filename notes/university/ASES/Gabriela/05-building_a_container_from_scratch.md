---
reviewed_on: "2024-10-04"
---

# Building a container from scratch

1. Download Linux system files: `wget https://github.com/ericchiang/containers-from-scratch/releases/download/v0.1.0/rootfs.tar.gz`.

    - `wget` is command-line utility to download files from the web.

2. Create a PID namespace for the shell (isolate the process inside the container).

    ```BASH
    sudo unshare -p -f --mount-proc=$PWD/rootfs/proc \
        chroot rootfs /bin/bash
    ```

    - `unshare`: run a program with some namespaces unshared from the parent.

        - `-p`: unshare the PID namespace.

        - `-f`: fork before executing the command.

        - `--mount-proc`: mount the proc filesystem at the specified location.

    - `chroot`: change the root directory.

3. Share a PID namespace with the shell.

    ```BASH
    sudo nsenter --pid=/proc/<host bash PID>/ns/pid \
        unshare -f --mount-proc=$PWD/rootfs/proc \
        chroot rootfs /bin/bash
    ```

    - `nsenter`: run a program with the namespaces of other processes.

        - `--pid`: enter the PID namespace of the specified process.

4. Share file between the host and the container.

    1. `sudo mkdir readonlyfiles`.

    2. `sudo mkdir -p rootfs/var/readonlyfiles`.

    3. `sudo mount --bind -o ro $PWD/readonlyfiles $PWD/rootfs/var/readonlyfiles`.

        - `mount`: mount filesystem.

            - `--bind`: remount a subtree somewhere else (so that its contents are available in both places).

            - `-o`: use the specified mount options.

        > `sudo umount $PWD/rootfs/var/readonlyfiles`.

5. Limit the resources designated for the container.

    1. `sudo su`.

    2. `mkdir -p /sys/fs/cgroup/demo`.

    3. `echo "100000000" > /sys/fs/cgroup/demo/memory.max`.

    4. `echo "0" > /sys/fs/cgroup/demo/memory.swap.max`.

    5. `echo <container bash PID> > /sys/fs/cgroup/demo/cgroup.procs`.

    To delete this cgroup you can run the command `sudo rmdir /sys/fs/cgroup/demo`.
