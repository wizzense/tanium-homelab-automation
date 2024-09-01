# Tanium Deployed Homelab

## to-do

Automate setup of github repo for maintaining all of this information, files, code, and instructions for deployment.

- ~~automate download and install git~~ - Done
- ~~automate download and install vscode~~ - Done
- ~~automate download and install of git CLI~~
- ~~automate create / clone repo~~ - Done
- ~~use config files for username/email/repo/clone path~~ - done
- ~~automate git management~~
- Automate installation and configuration of hyper-v on Primary PC and Work PC
  - need to make repo/configs aware of primary vs work PC
- automate hyper-v clustering between primary pc and work pc
- automate creation of control node VM.
- automate download of common OS ISOs
- automate provisioning baremetal hypervisor with hyper-v using tanium provision
- automate install and configure of WAC v2 (insider preview)
- automate deployment and configuration of VMs to hyper-v
- use config file to configure desired deployment (VMs, TS, etc.) and make it re-usable to add additional VMs later.

## Guiding Principles

Painstaklingly document everything
Painstakingly automate everything.
Everything.
From file downloads and .iso downloads to directory structure on Primary/ Work PCs for storing configurations and VMs, to VM deployment and configuration and management.

## Definitions

Primary PC = Home PC - recommended candidate for as primary hypervisor for the primary control node

Primary Control Node = VM on primary PC, provisioned for Tanium Cloud.

Work PC = Really, this is a secondary PC, but we're assuming you have hardware provided by your company. This is what we will use for redundancy/ failover/ additional access point -- will also run as a hypervisor and clustered with the Primary PC (Home PC).

## Wishlist

- The primary purpose is for it to be your control node for the deploying your lab useing Provision from Tanium Cloud. We do not need it to be running an available all the time, only when we want to re-provision our baremetal DOM or lab hardware. We will take care to automate every possible piece, from preparing an image, uploading the image to Tanium, creating a control node VM, instaling the Tanium Client, creating a satellite, creating a provision bundle, (leverage API) and deploying it from the satellite VM to the DOM/ lab hardware, which will then be Windows Server w/ Hyper-V, install Tanium, use automat/deploy/ ETC to copy .exes/.isos/local tooling and scripts for automating VM deployments (automate VM deployment of TanOS (look into using shell scripts for auto configuration fo TanOS and installation of Tanium Server) and use custom tags with packages that run the scripts/tooling that configures the VMs) Automate Domain Controller, pfsense, aTanium, and test endpoints on lab hardware.

I want to auto deploy a full mini-infrastructure

incorporate DR and redundancy, for example, if you have 2 or 3 bare metal machines.

Cluster hyper-v on two physical machines (where lab is deployed on third as main lab hypervisor), with high availability control node VMs for deplyoing labs.

will try to use AI, python/powershell/API for every single step
Will use VM images/ VHDs/ templates if sensible. Ideally, this will be plug and play, so it's not relying on images /isos being updated in order for it to work.

so, incorporate ease of automating the creation of the control node VM with any OS and config file/settings

allow plugging in desired server/client OS.isos, etc.

Allow plugging in of specific Tanium Clients/ Tanium Server / Tan OS versions

Guided setup of Patch to patch everything (automate config w/ API as much as possible)

Guided setup of Deploy to deploy desired apps (automate config w/ API as much as possible)

guided setup of Enforce (configuration management)

guided setup of internetworking from Tanium Cloud > Control Node on primary PC

autoconfig of Windows server roles > ADDS, DNS, DHCP, ADCS

autoconfig soap certs creation and configuration

autoconfig hyper-v checkpoints

autoconfig backups on baremetal Primary/Work PCs for control node VMs

add primary PC to your lab tanium instance for additional and mirror configurations from Patch/ Deploy/ Enforce.

Have a redundant ldap/dns/dhcp running on Linux that I can fail over configs from Windows

automate deployment of WAC V2 on Primary PC, Work PC, and Lab hypervisor.

## Instructions

### Step 1: Configure a VM on Main PC as a Tanium Cloud GA Satellite for PXE Provisioning Lab

1. On Main Windows PC or Work PC, install/enable Hyper-V.
   - Create your 'Control Node' for your homelab. THis will be a VM for many reasons. We can isolate it from your mprimary endpoint and install Tanium. This protects your information and Tanium and prevent unncessary bleedover. This is ideal if you want to leverage your personal hardware in order to create a more rbust homelab.

> **Note:**

### Step 2: Description of Step 2

Detailed instructions for Step 2.

> **Note:** Any important notes related to Step 2.

### Step 3: Description of Step 3

Detailed instructions for Step 3.

> **Note:** Any important notes related to Step 3.

## To-Do List

- [ ] Task 1
- [ ] Task 2
- [ ] Task 3

## Additional Notes

Any additional notes or comments can be added here.
