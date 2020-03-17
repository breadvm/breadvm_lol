www.breadvm.com

- **OS**

Ubuntu 16.04 desktop 64bit

- **Install**

setup git

> ```shell
> sudo apt-get install git 
> git config –global user.email “test@test.com” 
> git config –global user.name “test”
> ```

- **Setup Software Environment**

[Google document](https://source.android.com/source/initializing.html)

```
sudo add-apt-repository ppa:openjdk-r/ppa 
sudo apt-get update
sudo apt-get install openjdk-7-jdk 
sudo update-alternative --config java
sudo update-alternative --config javac
sudo apt-get install libx11-dev:i386 libreadline6-dev:i386 libgl1-mesa-dev g++-multilib 
sudo apt-get install -y git flex bison gperf build-essential libncurses5-dev:i386 
sudo apt-get install tofrodos python-markdown libxml2-utils xsltproc zlib1g-dev:i386 
sudo apt-get install dpkg-dev libsdl1.2-dev libesd0-dev
sudo apt-get install git-core gnupg flex bison gperf build-essential  
sudo apt-get install zip curl zlib1g-dev gcc-multilib g++-multilib 
sudo apt-get install libc6-dev-i386 
sudo apt-get install lib32ncurses5-dev x11proto-core-dev libx11-dev 
sudo apt-get install libgl1-mesa-dev libxml2-utils xsltproc unzip m4
sudo apt-get install lib32z-dev ccache
```


- **Download Source**

repo       [ustc mirror](https://lug.ustc.edu.cn/wiki/mirrors/help/aosp)

 ```shell
mkdir ~/bin
PATH=~/bin:$PATH
curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
chmod a+x ~/bin/repo
 ```
```
mkdir source
cd source
```

```
repo init -u git@github.com:breadvm/breadvm_lol.git
```

or mirror

```
repo init -u git@gitee.com:android-emu/breadvm_lol.git
```
```
repo sync --no-tags --no-clone-bundle --current-branch
```

- **Fix**

```shell
cd source
cp /usr/bin/ld.gold prebuilts/gcc/linux-x86/host/x86_64-linux-glibc2.11-4.8/x86_64-linux/bin/ld
```

- **Build**

```shell
cd source
source build/envsetup.sh
lunch android_x86-eng
make
```





