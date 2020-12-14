# Droste

This branch uses `generic/centos7`. It's the only CentOS 7 version I got working so far.

`centos/7`, which would be my preferred box, fails because the kernel headers needed are no longer in the repo, so building the guest additions bugs out. Might be fixed by the time you read this.  [See the issue on bugs.centos.org](https://bugs.centos.org/view.php?id=17867) 

