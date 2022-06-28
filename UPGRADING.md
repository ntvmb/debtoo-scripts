# Upgrading debtoo-scripts from v1.1.7 to v1.2.0
This is a guide on how to upgrade debtoo-scripts from v1.1.7 v1.2.0. If you're an existing Debtoo user, you'll need to know that Debtoo has undergone several changes which include multiple branches. Therefore, debtoo-scripts v1.1.7 will not allow you to upgrade to v1.2.0 automatically.
### os-release file
First and foremost, you need to get a new os-release file for optimal support. These are hosted on my website, but are not linked to within the website.
Since previous versions of Debtoo were based exclusively on Devuan Ceres, you'll want the unstable os-release file. It can be downloaded [here.](https://ntvmb.github.io/pub/debtoo/os-release_unstable)
With root priviliges or via sudo, save the file as `/usr/lib/os-release`. You can do so with this command (again, as root or via sudo):
```tex
wget -O /usr/lib/os-release https://ntvmb.github.io/pub/debtoo/os-release_unstable
```
### The upgrade
Now that you have 'installed' your new os-release file, it's time to upgrade.
Download the latest release:
```tex
wget  -O debtoo-scripts.tar.gz https://github.com/ntvmb/debtoo-scripts/archive/refs/tags/v1.2.0.tar.gz
```
Untar it:
```tex
tar xvf debtoo-scripts.tar.gz
```
Change to the release directory created during extraction:
```tex
cd debtoo-scripts-v1.2.0
```
Second to last, as root or via sudo, copy the scripts to `/bin`:
```tex
cp -v apt-source-install /bin
cp -v debtoo-install /bin ; # optional
cp -v debtoo-dist-upgrade /bin
cp -v update-debtoo /bin
```
Lastly, still as root or via sudo, mark the scripts as executable...
```tex
chmod 755 /bin/*
```
...and you will have completed the upgrade.
