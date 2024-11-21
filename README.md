# CMPE283: Virtualization Technologies - Assignment 2: KVM Statistics

## Prerequisites
- You will need a working Assignment 1 configuration to complete this task.(One Outer VM and InnerVM)
- Since this assignment is done in gcp , first login into the outer vm
 ```bash
    gcloud compute ssh outer-vm
 ```

## Step 1 - Build the kernel

### 1. Clone the repository to your outer vm
```bash
    git clone https://github.com/torvalds/linux.git
 ```
### 2. Navigate to the project directory:
  ```bash
    cd linux
  ```
### 3. Configure the Kernel
   - When You configure the kernel make sure the following is m or *
   - Virtualization
       - Kernel-based Virtual Machine (KVM) support
       - KVM for Intel processors support
  -  Device Drivers
      -  Network Device Support -> Universal TUN/TAP device driver support
  -  Device Drivers
       - Virtio drivers
       - PCI driver for virtio devices
       - Virtio balloon driver
       - Virtio input driver
   
   ```bash
    make menuconfig
   ```
### 4. Build the Kernel
   ```bash
    make -j$(nproc)
   ```
### 5. Build Initrd/Initramfs
```bash
make modules_install
make install
```
### 6. Reboot the outer VM
   ```bash
   sudo reboot
   ```

8. 
9. 
10. 

## Usage

Once your prerequisites are in place, you can begin working with KVM statistics.

### Step 1: Start the KVM Virtualization Environment
Follow the steps from Assignment 1 to start the KVM environment.

### Step 2: Collect KVM Statistics
Use the following command to collect KVM statistics:
```bash
sudo virsh nodeinfo
