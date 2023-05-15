Updated 15 MAY 2023: Adding a little more info for those looking to get this working using cygwin version 3.4.6
> For convenience of others in the same situation, I have zipped the files I used. All credits and licenses of their original authors apply. No changes were made to any of the files.
***
Starting this repo to keep notes about how I got rsync working on Windows.

My next planned step is to create a fully-automated script which will help anyone to run this on their machine (rather than distributing binaries, which I don't want to do).

### How to get RSync on Windows (:

- install cygwin (enable rsync package)
- grab those files from `c:\cygwin\bin`
  - cygcrypto-1.1.dll (new dependency)
  - cygiconv-2.dll
  - cyglz4-1.dll (new dependency)
  - cygwin1.dll
  - cygxxhash-0.dll (new dependency)
  - cygz.dll (new dependency)
  - cygzstd-1.dll (new dependency)
  - rsync.exe
  - (you can double check the list of required dlls using [dependency walker](http://www.dependencywalker.com))
- uninstall cygwin

### How to use

Here's an example call from a Mac OS X machine:

```
rsync -qrlP --delete local-folder user@windows-server-ip:/cygdrive/c/target-folder --rsync-path=c:/tools/rsync.exe
```

Here's another example call from a Windows machine itself:
> Dry run of syncing user John's pictures to a backup folder on an external drive connected and mounted in windows
```
rsync -avnc /cygdrive/c/Users/John/Pictures/ /cygdrive/d/backup/John/Pictures/
```
