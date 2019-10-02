# GDB docker container

The goal of this container is to wrap an up-to-date version of gdb so that it can be used on older distributions using remote debugging.

## Build

    $ docker build --tag=haggaie/gdb - < Dockerfile

## Run

    $ docker run -it -v $(pwd):$(pwd) --workdir $(pwd) haggaie/gdb

## Remote kernel debugging

See https://www.kernel.org/doc/Documentation/dev-tools/gdb-kernel-debugging.rst

    (gdb) add-auto-load-safe-path .
    (gdb) file vmlinux
    (gdb) target remote 172.17.0.1:1234
