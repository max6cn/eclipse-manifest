# meteor-repo

## Build Instructions
0. Change open file limit

```
sudo sysctl -w kern.maxfiles=409600
sudo sysctl -w kern.maxfilesperproc=180000
ulimit -S -n 180000
```

1. Install Repo:

```
 

# Make sure you have a bin/ directory in your home directory and that it is included in your path:

mkdir ~/bin
PATH=~/bin:$PATH
# Download the Repo tool and ensure that it is executable:

curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
chmod a+x ~/bin/repo
```
2. clone git repos from eclipse.org

```
mkdir name-of-project
cd name-of-project
repo init -u https://github.com/max6cn/meteor-repo/ -b R4_7_1 --depth=1
repo sync -j2
```
3. start build
```
cd platform
 mvn clean verify -DskipTests=true -Dnative=cocoa.macosx.x86_64

```
