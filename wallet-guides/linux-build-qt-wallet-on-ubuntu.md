# Linux: Build QT wallet on Ubuntu

Here is quick guide to build the DeepOnion wallet on Ubuntu 16.04.

**Step 1**: Ensure git is installed.

Code:

```text
sudo apt-get install git
```

**Step 2:** Clone the repo

Code:

```text
git clone https://github.com/deeponion/deeponion.git (GitHub - deeponion/deeponion)
cd deeponion
```

**Step 3:** Install all the required packages

{% hint style="info" %}
Read doc/readme-qt.rst - Note not all packages are list so use the below list
{% endhint %}

Code:

```text
 sudo apt-get install qt5-default qt5-qmake qtbase5-dev-tools qttools5-dev-tools build-essential libboost-dev libboost-system-dev libboost-filesystem-dev libboost-program-options-dev libboost-thread-dev libssl-dev libdb++-dev libevent-dev libqrencode-dev
```

**Step 4:** Build leveldb

Code:

```text
cd src/leveldb
chmod +x build_detect_platform
make libleveldb.a libmemenv.a
cd ../..
```

**Step 5:** Build the QT wallet

Code:

```text
qmake
make
```

**Step 6:** RUN!

Code:

```text
./DeepOnion-qt
```

**Video:** [https://www.youtube.com/watch?v=ltt4p-Jy2Ok](https://www.youtube.com/watch?v=ltt4p-Jy2Ok)

