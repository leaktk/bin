# Bin

Small binary files that shouldn't really change after being uploaded

## Warning

This is meant to be used internally by LeakTK. It may go away in the future.

## Naming Format

Files should be under the bin folder and following the naming convention:

```
{name}-{version}-{os}-{arch}
```

where

```
name := (The package name)
version := (The semvar version)
os := {linux,darwin}
arch := {arm64,x86_64}
```

## CHECKSUM

Always update the CHECKSUMS file after adding new files

```sh
sha256sum bin/* > CHECKSUMS
```

## Git & Binary Files

I hear you say:

**Git can not diff binary files.**

These files represent snapshots of finished artifacts. They shouldn't be
changing or needing to be diffed.

**You shouldn't store large files in git!**

Thankfully these are fairly small files and this repo shouldn't be used for
files larger than about half of GitHub's recommended limit.

**It makes the clone take longer.**

Generally this repo isn't meant to be cloned. The blobs are pulled over HTTP
through GitHub.

**The blobs will be in the history even if you remove them!**

They can be filtered out. The history is not meant to be sacred in this repo
and folks shouldn't be cloning it.
