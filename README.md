# CMPE 283 - assignment 1

1. Create a VM instance on Google Cloud Platform
   - CPU: n2-standard-8
   - disk: 100G
   - add SSH key for later use
   ![ssh_key](image/ssh_key.png)
2. After customizing the instance, click on `equivalent command line`
   - add --enable-nested-virtualization
   ![gcloud_cmd](image/gcloud_cmd.png)
3. Set up `VS Code` remote ssh 
   - set up your ~/.ssh/config
   ![ssh_config](image/ssh_config.png)
   - connect to instance via vs code
   ![vsc_ssh](image/vsc_ssh.png)
4. Install libraries that we need
   - update apt, apt-get
   ```bash
   sudo apt update
   sudo apt-get update
   ```
   - install gcc, linux kernel
   ```bash
   sudo apt install gcc, make
   sudo apt-get install linux-headers-$(uname -r)
   ```
5. Set up includePath in vs code
   - here I'm using `/lib/modules/5.4.0-1092-gcp/build`
6. check Intel SDM for controls
   - [Intel SDM Vol.3](https://cdrdv2.intel.com/v1/dl/getContent/671447)
7. create the `struct` for vm-execution control fields
8. implement `detect_vmx_features` using `rdmsr`
9. insert/remove the module, and dump the message
   - `insmod`, `rmmod`, `dmesg`
   ```bash
   sudo insmod ./cmpe283-1.ko
   sudo dmesg
   sudo rmmod cmpe283-1
   ```
   ![insert_module](image/insert_module.png)
   - [dmesg.log](dmesg.log)