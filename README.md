# Programmable Networks 2024

Welcome to the repository of the Programmable Networks course!
Here you will find the weekly exercises and instructions on how to run these exercises in a virtual environment.

<!-- TOC depthTo:3 -->

- [How to start?](#how-to-start)
    - [Download VM image](#download-vm-image)
    - [Remote Development](#remote-development)
    - [VM Contents](#vm-contents)
- [Exercises](#exercises)
    - [Week 1](#week-1)

<!-- /TOC -->

## How to start?

This year we will use the virtual environment prepared by the Networked Systems Group at ETHZ. The tool is called p4-utils: https://github.com/nsg-ethz/p4-utils/tree/master

### Download VM image

Disk images for both Hyper-V and VirtualBox have been prepared. They can be downloaded via scp in the university domain. After downloading and uncompressing the selected disk image, you should create a new VM with this image attached.

Using Hyper-V:
```
scp stud2024@10.82.2.10:p4utils_hyperv.zip
``` 

Using 
```
scp stud2024@10.82.2.10:p4utils_vbox.zip
``` 

Username and passwork are both p4 in the VM.

### Setup the network in the VM if needed

Use NATed networks in the hypervisor software and setup a forwarding rule for port 22 (e.g., 2222 on host to 22 on guest). 

```
sudo dhclient enp0s3
```

To access your VM, you will use SSH.

Once you have installed an SSH client, use the following command to connect yourself to your
VM:

```
ssh -p 2222 p4@localhost
```

### Remote Development

We need to be able to open and edit remote files in our local code editor to have a smooth development cycle. We explain how to achieve this for Visual Studio Code as an example:

1) Download Visual Studio Code.
2) Access VS Code; in the left-side dock enter `Extensions` menu.
3) Install `Remote - SSH` extension.
4) Add `"remote.SSH.showLoginTerminal": true` to the args.json file in the settings folder of VSCode
5) Your "Remote Directory" should appear in the Explorer.
6) Go to Extensions menu again and install `P4 Language Extension` in your remote machine for highlights and syntax check.

For VS Code, you can find further information [here](https://code.visualstudio.com/docs/remote/ssh).

If you are already familiar with remote development, feel free to continue with your favorite code editor/setup.

## Exercises

In this section, we provide links to the weekly exercises.

To get the exercises ready in your VM, clone this repository in the `p4` user home directory, as illustrated below:

```
cd /home/p4/
git clone https://github.com/slaki/prognets2024.git
```

Update the local repository to get new tasks and solutions.
Remember to pull this repository before every exercise session:

```
cd /home/p4/prognets2024
git pull
```

### Week 1

- [Introduction to P4](./01-P4_Introduction) Source: https://gitlab.ethz.ch/nsg/public/adv-net-2022-exercises/-/tree/main
- [Layer 2 Switch](./02-L2_Switching) Source: https://gitlab.ethz.ch/nsg/public/adv-net-2022-exercises/-/tree/main