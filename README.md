# A trivial Linux kernel module to execute WBINVD on demand (`cat /proc/wbinvd`)
[![Build Status](https://travis-ci.org/batmac/wbinvd.svg?branch=master)](https://travis-ci.org/batmac/wbinvd)


WBINVD (Write Back and INValidate Cache) is a (ring 0 only) x86 instruction to asynchronously purge the cache (with write-back)

more info about WBINVD: http://www.felixcloutier.com/x86/WBINVD.html
```
make && make test
```

one can use dkms to create a .deb, for instance:
```
make install-bdep
apt-get install dkms
cp -a <repo_dir> /usr/src/wbinvd-1.0
dkms add wbinvd/1.0
make deb # or dkms mkdeb wbinvd/1.0 --source-only
```
