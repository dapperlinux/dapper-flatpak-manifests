# dapper-flatpak-manifests

## About
Dapper Flatpak Manifests contains the manifests for all applications used in Dapper Linux.
The majority of these applications are taken from other sources, and are forked to mainly increase their access controls to reduce the directories each application can access. You can see where the manifests are taken from [here](sources)

# Building
You can build flatpak packages for any manifest in this repo. It's all very straightforward and follows the flatpak man pages.

Add the flathub remote:
```
$ sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

Install the gnome Sdk
```
$ sudo flatpak install flathub org.gnome.Platform 3.28
$ sudo flatpak install flathub org.gnome.Sdk 3.28
```

Build an application, for example Dapper Hardened Browser:
```
$ flatpak-builder com.dapperlinux.Dapper-Hardened-Browser com.dapperlinux.Dapper-Hardened-Browser.json
$ flatpak build-export repo com.dapperlinux.Dapper-Hardened-Browser
```

Then you can test the application with
```
$ flatpak remote-add --no-gpg-verify testrepo repo
$ flatpak install testrepo com.dapperlinux.Dapper-Hardened-Browser
```

Or if you want to use gpg, find your keyid, and then export with:
```
$ gpg2 -k
$ flatpak build-export --gpg-sign=key-id repo com.dapperlinux.Dapper-Hardened-Browser
```

Or export it to a gpg signed repository of your choosing, just add a gpg key parameter to the build-export command.

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
