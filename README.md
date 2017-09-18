# meteor-repo

## Build Instructions
0. Change open file limit

```
sudo sysctl -w kern.maxfiles=409600
sudo sysctl -w kern.maxfilesperproc=180000
ulimit -S -n 180000
```

1. Get Repo
2. clone git repos from eclipse.org

```
repo init -u https://github.com/max6cn/meteor-repo/ -b R4_7_1 --depth=1
```
3. start build
```
 mvn clean verify -DskipTests=true -Dnative=cocoa.macosx.x86_64

```
