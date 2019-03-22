# Sync Backup Tool :

## A Convenient Tool of Rsync

A tool for backup files by setting variable, a wrapper of [Rsync](https://rsync.samba.org/)
Author: [Wancat](https://github.com/lancatlin)

## Feature

You can use Rsync without typing the same path again and again. Set the remote path in a file, then you can  `push` or `pull`  a file without remote path.

## Install

This program only requires `rsync` and `bash` . Please make sure you have installed them before using.

Download the `sync-backup` file,  execute `chmod +x sync-backup`  , and put it into `~/.local/bin` or anywhere in $PATH.

## Usage:
`sync-backup METHOD FILE OPTION`

METHOD=`{push|pull}`

OPTION is the options of rsync. See man rsync. It only supports one parameter now. If option is not defined, it will use `-avhP` by default.

You have to set the `$SYNC_FILE` in ~/.syncpath or .syncpath. The file in current directory will be used by default. 

example: 

```shell
# .syncpath
SYNC_PATH="foo:/home/user/Documents/"
```

```shell
$ sync-backup push something # rsync -avhP something foo:/home/user/Documents/something
$ sync-backup pull something # rsync -avhP foo:/home/user/Documents/something something 
$ sync-backup push something --dry-run # rsync --dry-run something foo:/home/user/Documents/something
```

