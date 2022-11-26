# Hey! I'm Filing Here

One line description of this code.

Creating a snap shot of a file system.

## Building

Explain briefly how to build your program.

A lot of the functions are given to us we simply have to write the correct information for each part of the file system. We build it up piece by piece, starting with the superblock, then
to the group descriptor block, then to the block bitmap and inode bitmap, and finishing it off with creating the inode table, directory entries and hello file. At each part of the process I first
went to the guidebook and saw what each value meant. We simply had to plug in constant values to areas.

## Running

Show how to compile, mount, and example output of `ls -ain` your mounted
filesystem.

make # compile the executable
./ext2-create # run the executable to create cs111 -base.img
dumpe2fs cs111 -base.img # dumps the filesystem information to help debug
fsck.ext2 cs111 -base.img # this will check that your filesystem is correct
mkdir mnt # create a directory to mnt your filesystem to
sudo mount -o loop cs111 -base.img mnt # mount your filesystem , loop lets you use a file

Output of 'ls -ain'

total 7

2 drwxr-xr-x 3 0 0 1024 Nov 26 15:03 .

934 drwxr-xr-x 3 1000 1000 4096 Nov 26 15:05 ..

13 lrw-r--r-- 1 1000 1000 11 Nov 26 15:03 hello -> hello-world

12 -rw-r--r-- 1 1000 1000 12 Nov 26 15:03 hello-world

11 drwxr-xr-x 2 0 0 1024 Nov 26 15:03 lost+found

## Cleaning up

Explain briefly how to unmount the filesystem, remove the mount directory, and
clean up all binary files.

make clean # clean up binary files
sudo umount mnt # unmount the filesystem when you're done
rmdir mnt # delete the directory used for mounting when you're done
