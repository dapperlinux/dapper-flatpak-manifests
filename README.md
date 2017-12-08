# dapper-flatpak-manifests

## About
Dapper Flatpak Manifests contains the manifests for all applications used in Dapper Linux.
The majority of these applications are taken from other sources, and are forked to mainly increase their access controls to reduce the directories each application can access. You can see where the manifests are taken from [here](sources)

# Building
You can build flatpak packages for any manifest in this repo. It's all very straightforward and follows the flatpak man pages.

# Running
The repo is already added to Dapper Linux, so if you are using that as your distro, you are in luck.
If you are interested in using these apps yourself, then you can add the repo and download the apps yourself.

Adding the repo:
```
$ flatpak remote-add --if-not-exists dapperlinux --from https://download.dapperlinux.com/dapperlinux.flatpakrepo
```

Installing apps:
```
$ flatpack install dapperlinux com.dapperlinux.Dapper-Hardened-Browser
$ flatpack install dapperlinux org.mozilla.Firefox
$ flatpack install dapperlinux org.gnome.Evolution
$ flatpack install dapperlinux org.gnome.Music
```
