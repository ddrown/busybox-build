## To download build environment:

    docker pull ddrown/busybox-build

## To build busybox binaries:

    OUTPUTDIR=~/target
    mkdir $OUTPUTDIR
    docker run -v $OUTPUTDIR:/target ddrown/busybox-build

This will create 4 binaries in $OUTPUTDIR: busybox-x86-pie, busybox-x86-nopie,
busybox-arm-pie, and busybox-arm-nopie.  See the file "tests.txt" for the
output of running "echo ok" with each of these binaries on various Android
versions and architectures.

## To build a modified busybox:

    OUTPUTDIR=~/target
    mkdir $OUTPUTDIR
    docker run -i -t -v $OUTPUTDIR:/target ddrown/busybox-build /home/admin/shell
    [make modifications]
    /home/admin/build
