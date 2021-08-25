# Setup GNS3

In order to simulate intra-network communications (such as IPsec VPN), we'll need a software application called GNS3. GNS3 is a free, open source tool that facilitates network simulation via topographical charting on a single host computer. 

> Not all lab activities in Ops 301 require GNS3; in fact, Virtualbox's built in networking capabilities are adequate for most activities, including security-related work in Ops 401. However, certain labs will necessitate the use of GNS3 due to specific technical operations that exceed the capabilities of VirtualBox

## Objectives

- Configure GNS3 on your lab kit PC so that it is fully ready for use
  - Setup GNS3 Server and confirm operational
  - Setup GNS3 VM and confirm operaitonal

## Resources

- [GNS3 Website](https://www.gns3.com/){:target="_blank"}
- [GNS3 VM Download](https://gns3.com/software/download-vm){:target="_blank"}
  - Select the VirtualBox download

## Installation

GNS3 comes preinstalled on your Ubuntu Linux lab kit PC if you took Ops 102 and executed the labsetup.sh bash script. However, it does NOT come preconfigured.
- If you completed Ops 102 using labsetup.sh script, proceed to the next step below, "GNS3 Server."
- If you did NOT complete Ops 102 using labsetup.sh script, visit GNS3's website and proceed with the installation procedure to load GNS3 on your lab kit PC.

### GNS3 Server

When GNS3 launches for the first time, it will prompt you to setup GNS3 Server. Complete this process and verify the "green light" icon turns on when you launch GNS3. 

### GNS3 VM

Download the GNS3 VM to your lab PC and import the OVA into VirtualBox. Do not alter its network configuration settings, but it's OK to review the network settings before importing.

After launching the GNS3 VM in VirtualBox, it will complain that "eth0 is not configured." For this course, it is recommended that your GNS3 VM have internet connectivity. You'll need to plug GNS3 VM into a working pfSense router on VirtualBox just like you would any new endpoint, however there is a text-only configuration step under the Network menu. The below is a working example of what you'd enter into the config file for a given network of 10.0.0.0/24 with a gateway on pfSense of 10.0.0.2. 

```
# This file describes the network interfaces available on your system
# For more information, see netplan(5).

# Uncomment the following lines if you want to manually configure your network

network:
  version: 2
  renderer: networkd
  ethernets:
    eth0:
      dhcp4: yes
      addresses:
        - 10.0.0.0/24
      gateway4: 10.0.0.2
      nameservers:
          addresses: [8.8.8.8, 8.8.4.4]
```
GNS3 VM will achieve internet connectivity and receive an IP address if this step is configured successfully. If not, you'll continue to receive the "eth0 is not configured" error message. You can also use the "Test" command in the menu to see if it can reach the internet. 

Once you are able to create projects in GNS3 and deploy basic infrastructure without error, you're all set.

## Submission Instructions

1. Create a new blank Google Doc. Include above assignment submission text and images within this Google Doc.
1. Name the document according to your course code and assignment.
   - i.e. `seattle-ops-201d1: Reading 01` or `seattle-ops-201d1: Lab 04`.
1. Add your name & date at the top of the Google Doc.
1. Share your Google Doc so that "Anyone with the link can view".
1. Paste the link to your Google Doc in the discussion field below and share an observation from your experience in this lab.
