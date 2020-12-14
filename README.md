# Droste

What is Droste?

### In short.

Droste is a project that:

1. Launches a VM using Vagrant and Virtualbox
2. Uses the Ansible provisioner to install Ansible, Git, Vagrant and Virtualbox on the VM
3. Clones this project onto the VM
4. Executes `vagrant up`. Goto 1.

Ergo, each VM spawns a VM, which spawns a VM, which spawns a VM...

### A little more detail.

Read the fine source ;)

But, some of the trickery is in rewriting the Vagrantfile for each level. After all, less and less memory is available as the stack of VMs deepens.

Also, a file is written to the caller VM, which uses a cronjob to write it to its caller. So at the top level, you will see how many levels of Droste have been achieved.

### Why?

Why on earth would anyone want to do this? I don't know, why not? Do you know the film 'Inception'? I hated it.

### Where is the code then, and how do I run this contraption?

You need to check out a branch. At this time, centos7 is the only one that is available.

You need Git (obviously, you're on github.com), Ansible, VirtualBox and Vagrant installed. I've had success on Ubuntu 18.04 using:
* VirtualBox 6.1.1
* Ansible 2.9.6
* Vagrant 2.2.14

Other versions and OSes might work, who knows, YMMV.

The Vagrantfile has settings for initial memory allocations. Memory is automatically adjusted on deeper levels, so you can change it to whatever you want. Use of a single CPU is enforced, using multiple CPUs messes up the nested virtualization.

### Does this perform?

Are you kidding me? It gives your CPU a workout though.

### What is this 'Droste' thing?

Ah. If wonder about this, you are most likely not Dutch.

Droste is a Dutch chocolate factory. The brand is known for its packaging, which displays a nurse carrying a serving tray with a cup of hot chocolate and a box with the same image. For more information, see this [wikipedia page on Droste](https://en.wikipedia.org/wiki/Droste_effect).
