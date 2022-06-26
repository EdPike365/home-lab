# EdPike365 Home Lab

Documenting my home lab journey.

- I've been a heavy duty web app dev for years and a modest DevOps engineer. I picked up IT/Ops skills when I had to becuase the IT staff were not able to fulfill my app's needs. After a while, you realize that if the infrastructure doesn't work, your app might as well not work (and might be blamed).
- My mid range goal is to become more of a "power DevOps engineer" with hybrid/multi Cloud Engineer characteristics.
- My longer term goal is to become a hybrid/multi Cloud Architect.
- I started earning AWS Certs, without much production experience, and it did not feel like deep learning. 
- I decided to get various CNCF certs up to CKAD then loop back to vendor specific certs. The CNCF certs would be more generic, with fewer marketing terms obscuring what I was learning. Kubernetes is also obviously the current best choice for hybrid/multi cloud engineering.
- A Home Lab seemed like the best bet in the early days to minimize my cloud bills. So here we go...

## Technologies: 

- ProxMox, VirtualBox
- ContainerD, DockerD
- K8s, K3s, Rancher
- Prometheus, Grafana
- Ansible, Terraform, Vagrant, Packer
- Pi Hole, local DNS

### Beginning State, June 2022:

- I have 1Gb fiber to my house. Router is vanilla from the vendor.
- Various PC towers and laptops. 1 PixelBook Go.
- 1 unused Raspberry Pi 3 B+ (used to experiment with Bluetooth from my phone years ago)

### Step 0: 

- Added dual boot with Ubuntu 22 Desktop on all active windows machines using VenToy. Also enabled WSL 2 for convenience. From here out, I and my kids will be using Windows 11 only for gaming. They (twins) are entering engineering college and I want them to have some cred but also be able to game on their laptops.
- Enabled Linux on PixelBook, set up for remote dev with installed VSCode.

### Step 1: 

Recommissioned old inactive game tower to ProxMox to host a small K8s Cluster which will host a Jenkins cluster. Its old so I don't want to upgrade anything. Its a ASRock Z77 Extreme 6, LGA 1155. I considered getting a Xeon for the 1155 socket but even that would be on the wrong side of the technology curb. I'll be looking at a Xeon 2011 R setup (current sweet spot) in the near future. I'll buy some old ECC mem as well.
    - CPU: I5. 4 cores x 1 thread = 4 CPUs. 64 bit. Can be overprovisioned.
    - RAM: 16 GB. RAM *can* be overprovisioned but its hinky.
    - 1 NIC
    - SSD 1: 500 GB
    - SSD 2: 1TB
    - HDD 1 and 2: 1TB, were mirrored.

## ProxMox

- QEMU (Quick Emulator) over KVM (Kernel-based Virtual Machine) using VirtIO
- Min host controller specs:
- Installed controller on 500 GB SSD. Can also store ISOs there.
- Added 1TB SSD for use by VMs.
- Did not use ZFS because only 16 GB RAM and ZFS wants 8GB min, so using EXT4. 
- Uploaded Ubuntu 22 live server base ISO.
- [ProxMox VM Settings](https://pve.proxmox.com/wiki/Qemu/KVM_Virtual_Machines#qm_virtual_machines_settings)
- [How to add storage to Proxmox (HDD ext4)](https://nubcakes.net/index.php/2019/03/05/how-to-add-storage-to-proxmox/)


## Jenkins

- Controller min specs: Just for me, so .5 GB RAM
- Agent min specs
- Kubernetes Plugin

## Konstruct/Packer

- https://github.com/konstruktoid/hardening-geniso

adsfafd
afadfadf
asdfafda
asdfasf
adsfasdfas