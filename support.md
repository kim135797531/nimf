---
layout: page
title: Support
---

If you have any problems or requests while you are using Nimf, please contact
[issues](https://github.com/cogniti/nimf/issues).

## How to build deb package

First of all, install `devscripts`, `build-essential`.

```
username:~$ sudo apt install devscripts build-essential
```

After installing `devscripts`, `build-essential` perform the following commands.

```
username:~$ cd
username:~$ mkdir tmp-build
username:~$ cd tmp-build
username:~/tmp-build$ wget https://github.com/cogniti/nimf/archive/2016.09.26.tar.gz
username:~/tmp-build$ tar zxf 2016.09.26.tar.gz
username:~/tmp-build$ cd nimf-2016.09.26
username:~/tmp-build/nimf-2016.09.26$ dpkg-checkbuilddeps
```

You may see something like:

> dpkg-checkbuilddeps: Unmet build dependencies: some-package1 some-package2 ...

Install all missing dependencies and perform the following commands.

```
username:~/tmp-build/nimf-2016.09.26$ debuild
username:~/tmp-build/nimf-2016.09.26$ cd ..
username:~/tmp-build$ ls
2016.09.26.tar.gz              nimf_2016.09.26_amd64.deb
nimf-2016.09.26                nimf_2016.09.26.dsc
nimf_2016.09.26_amd64.build    nimf_2016.09.26.tar.xz
nimf_2016.09.26_amd64.changes  nimf-dev_2016.09.26_amd64.deb
```

As above mentioned, make the package yourself. Otherwise, request your Linux
distribution to package Nimf.

### Not Nimf bugs but your application bugs

Report bugs to your application project. **Do not request me to fix your
application bugs**.
