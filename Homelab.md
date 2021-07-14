# Homelab
If you're looking to land a technical cyber security job, a homelab is one of the most important things you can build. Just like a professional sports player needs to practice their craft to be excellent in a game, having a homelab allows you to practice your cyber security skills to prepare you for real-world scenarios. Building a homelab typically starts with setting up some kind of hypervisor. From there, you can configure virtual machines to run on your hypervisor of choice. These virtual machines can be anything from a firewall to a domain controller to a linux server. With the rise in popularity of virtualization, almost anything can be made into a virtual machine. Building a homelab can also include buying and configuring physical hardware such as servers, networking gear, etc. The best part about a homelab is that you can make it as big or as small as you want! As a warning though, homelabbing can become quite addicting and may lead to more purchasing of hardware that you originally thought! Below I have described briefly different components of a homelab and have linked external resources for more information.


# Hardware
Hardware is where you need to start for a homelab. The good news is you probably already own hardware you can run a lab on. Any laptop or computer you own with at least 8GB of RAM, 25GB of available storage, and a dual core processor can get you started! As you progress in your homelab you will want more and more hardware. More hardware allows you to run more VMs. When looking at hardware upgrades to a homelab, RAM is what will seem to run out first. I recommend 16GB-32GB if you can get your hands on it. If you have access to more RAM than 16GB-32GB that's great! More RAM always being better. Also, if you don't have one already, running VMs on an SSD will be **far** faster than running them on a hard drive. Finally, if you can upgrade your CPU, look to get as many cores and threads as possible. As you tinker with your own lab you will start to learn what hardware you need more of for your use case. Don't feel pressured to get the "perfect hardware" at the start. For most people, just using what you already have and going from there is the best way to do it. 


# Software
## Hypervisors
Unless you have tons of physical computers to mess with (and frankly even if you do), a hypervisor is going to be the foundation of your homelab. A hypervisor is a piece of software (just like Word, Excel, or Chrome is) that allows you to run a virtual machine (VM) on top of itself.  

There are two main types of hypervisors: type 1 and type 2. A type 1 hypervisor is meant to be installed on the bare metal of a computer much like Windows or Linux would be. Because of this, a type 1 hypervisor turns a computer into a dedicated virtual machine manager. Most people do not have a dedicated computer to run VMs and therefore will prefer to use a type 2 hypervisor. A type 2 hypervisor is installed on top of an operating system (Windows, MacOS, Linux).

When it comes to free type 2 hypervisors, there are a bunch of options. The table below includes some type 2 hypervisors that I recommend. 
|                                         Name                                         |     OS Compatibility    |   Price  |
|:------------------------------------------------------------------------------------:|:-----------------------:|:--------:|
|                       [VirtualBox](https://www.virtualbox.org/)                      | Windows, Mac, and Linux |   Free   |
| [VMware Workstation Player](https://www.vmware.com/products/workstation-player.html) |    Windows and Linux    |   Free   |
| [Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/about/) |         Windows         |   Free   |
|    [VMware Workstation Pro](https://www.vmware.com/products/workstation-pro.html)    |         Windows         |   $199   |
|             [VMware Fusion](https://www.vmware.com/products/fusion.html)             |           Mac           |   $199   |
|                        [Parallels](https://www.parallels.com/)                       |           Mac           | $99/year |

My recommendation (especially for people new to homelabbing) is VirtualBox. Even though it is free, VirtualBox has most if not all of the features from the other options. Also, it has the highest OS compatibility which means you can run it on any computer you own. 

If you are looking for a type 1 hypervisor, the discussion becomes a little more nuanced. There are three major players in this space: [VMware ESXi](https://www.vmware.com/products/esxi-and-esx.html), [Proxmox](https://proxmox.com/en/), and [Microsoft Hyper-V](https://www.microsoft.com/en-us/evalcenter/evaluate-hyper-v-server-2019). Proxmox and Hyper-V are completely free. ESXi, on the other hand, has both a free and paid version. The free version of ESXi doesn't leave out any big features for a new homelabber. If you get to a point in your homelabbing where you would like a licensed version of ESXi, check out the [VMUG Advantage Subscription](https://community.vmug.com/vmug2019/membership/vmug-advantage-membership). This subscription costs $200/year but gives you access to 356 day Evaluation licenses for almost all of VMware's products! This includes VMware Workstation Pro, VMware Fusion, a fully featured version of ESXi, vCenter, and more! If you plan on getting a job which includes managing VMs, I recommend paying the money for the VMUG Advantage Subscription and using VMware's products. If you can't pay for the VMUG Advantage Subscription I recommend using the free version of ESXi. This is because VMware's products are the most popular enterprise VM management tools. Most likely, the company you work for will be using VMware's products. If you do not plan on getting a job which includes managing VMs, I recommend Proxmox. It is a fully featured hypervisor that, most importantly, is free. 

## Linux Hosts
The best part about Linux hosts is that they are all free! If you are just starting out I recommend getting a copy of [Ubuntu Desktop 18.04](https://releases.ubuntu.com/18.04.5/ubuntu-18.04.5-desktop-amd64.iso) and setting it up! If you are ready to conquer the command line, I recommend going for [Ubuntu Server 18.04](https://releases.ubuntu.com/18.04.5/ubuntu-18.04.5-live-server-amd64.iso). 

Once you get your operating system up and running, install and play around with some of the following software.

**Most important:**
- [OpenSSH-Server](https://ubuntu.com/server/docs/service-openssh)
- [WireGuard](https://www.wireguard.com/)
- [Nginx](https://www.nginx.com/)
- [Apache](https://httpd.apache.org/)
- [iptables](https://linux.die.net/man/8/iptables)
- [Elastic Stack](https://www.elastic.co/what-is/elk-stack)
- [Graylog](https://www.graylog.org/)
- [BIND9](https://www.isc.org/bind/)
- [Docker](https://www.docker.com/)
- [Samba](https://ubuntu.com/server/docs/samba-introduction)
- [LAMP](https://ubuntu.com/server/docs/lamp-applications)

**Less important but still great experience:**
- [Pi-hole](https://pi-hole.net/)
- [Gitlab Server](https://about.gitlab.com/install/)
- [Gitea Server](https://gitea.io/en-us/)
- [Squid](https://ubuntu.com/server/docs/proxy-servers-squid)
- [Jenkins](https://www.jenkins.io/)
- [Portainer](https://www.portainer.io/)
- [Plex](https://www.plex.tv/)
- [Dovecot](https://ubuntu.com/server/docs/mail-dovecot)

Obviously there is a lot of software here so make sure to have fun with it! Pick the ones that interest you the most and run with them. Also, if you are unsure how to install and configure something, just Google for the name of the software followed by `Ubuntu 18.04`. There are plenty of guides on all of the above software. Also, know that not all guides are going to be 100% accurate. Part of the fun of doing this kind of stuff is figuring out the solutions to problems you encounter. If you have no experience with Linux, check out [these Linux resources](https://github.com/syth3/Cyber-Beginner-Resources/blob/main/Linux%20Resources.md).

## Windows Hosts
In the Windows land unfortunately everything is not free like it is with Linux. Fortunately, [Microsoft's Evaluation Center](https://www.microsoft.com/en-us/evalcenter/) gives away evaluation versions of their products which allow you to run their software anywhere from 90 to 180 days. This is usually plenty of time to test something on a homelab. I believe you can also extend the evaluation period for these VMs. Also, For more long term Windows 7, 8, and 10 hosts, check out the [Microsoft Edge Developer](https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/) page. These VMs boot with instructions on how to extend the time you can use the VM on the Desktop wallpaper.

Once you get your operating system up and running, install and play around with some of the following software (most important ones in bold):

**Most important:**
- [Active Directory](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)
- [Group Policy](https://en.wikipedia.org/wiki/Group_Policy)
- [Windows Server DNS](https://docs.microsoft.com/en-us/windows-server/networking/dns/dns-top#:~:text=In%20Windows%20Server%202016%2C%20DNS,for%20the%20forest%20and%20domain.)
- [Active Directory Certificate Services](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))

**Less important but still great experience:**
- [Windows Server DHCP](https://docs.microsoft.com/en-us/windows-server/networking/technologies/dhcp/dhcp-top#:~:text=DHCP%20allows%20hosts%20to%20obtain,other%20information%20to%20DHCP%20clients.)
- [Windows 10 Remote Administration Tools](https://docs.microsoft.com/en-us/troubleshoot/windows-server/system-management-components/remote-server-administration-tools)
- [Internet Information Services (IIS)](https://www.iis.net/)
- [Windows Defender Antivirus](https://docs.microsoft.com/en-us/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-on-windows-server?view=o365-worldwide)
- [Windows Defender Firewall](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)

## Networking
If you are interested in learning about routers, firewalls, etc., there are many different VMs you can download to play around with. The two I recommend are [pfSense](https://www.pfsense.org/) and [OPNsense](https://opnsense.org/). These VMs both act as a completely functional router and therefore can be used to build virtual networks. If you are interested in learning about how to configure Cisco equipment, I recommend checking out [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer) and [GNS3](https://www.gns3.com/).

## Automation
Once you feel comfortable manually setting up a VM, try to automate it! Below are a list of automation software I recommend to learn:
- [Ansible](https://www.ansible.com/)
  - [This book](https://www.ansiblefordevops.com/) is a great way to learn Ansible
- [PowerShell](https://docs.microsoft.com/en-us/powershell/)
- [Terraform](https://www.terraform.io/)
- [Packer](https://www.packer.io/)

## Homelabbing Resources

### YouTube Channels
- [Craft Computing](https://youtube.com/c/CraftComputing)
- [LearnLinuxTV](https://youtube.com/c/LearnLinuxtv)
- [Techno Tim](https://youtube.com/c/TechnoTimLive)
- [Lawrence Systems](https://youtube.com/user/TheTecknowledge)
- [David Bombal](https://youtube.com/c/DavidBombal)
- [ServeTheHome](https://youtube.com/c/ServeTheHomeVideo)
- [2GuysTek](https://youtube.com/c/2GuysTek)
- [Linus Tech Tips](https://youtube.com/c/LinusTechTips)

### Podcasts
- [Self Hosted](https://selfhosted.show/)
- [2.5 Admins](https://2.5admins.com/)
- [On The Metal](https://oxide.computer/podcasts)
