# Linux Administration Research Project 1

---

## **Basic Concepts**

### 1. What are the key differences between Linux and other operating systems like Windows and macOS?
- **Open Source vs Proprietary:** Linux is open source, while Windows and macOS are proprietary.
- **Cost:** Linux is free; Windows and macOS often require licenses.
- **Customization:** Linux offers deep customization; Windows/macOS are more rigid.
- **Security:** Linux is less targeted by malware, making it more secure by design.
- **File System:** Linux uses file systems like ext4, while Windows uses NTFS and macOS uses APFS.

---

### 2. Describe the Linux file system hierarchy. What are the purposes of directories like `/bin`, `/etc`, and `/home`?
- **/**: Root directory, the top of the hierarchy.
- **/bin:** Essential user binaries (e.g., `ls`, `cp`, `mv`).
- **/etc:** Configuration files for the system and applications.
- **/home:** Personal directories for users.
- **/var:** Variable files like logs.
- **/usr:** User-installed software and libraries.

---

### 3. Explain the concept of a Linux distribution. Name at least three popular Linux distributions and their primary uses.
- A **Linux distribution** (distro) combines the Linux kernel with software packages, package manager, and utilities.
- Examples:
  - **Ubuntu:** User-friendly, ideal for beginners and servers.
  - **CentOS/RHEL:** Enterprise servers and production environments.
  - **Debian:** Stable and secure, often used in servers.

---

## **User and File Management**

### 4. How do you create and manage users and groups in Linux? Provide commands for adding, deleting, and modifying users.
- Add user:  
  ```bash
  sudo useradd username
  ```
- Add user with home directory:  
  ```bash
  sudo adduser username
  ```
- Delete user:  
  ```bash
  sudo userdel username
  ```
- Modify user:  
  ```bash
  sudo usermod -aG groupname username
  ```
- Create group:  
  ```bash
  sudo groupadd groupname
  ```

---

### 5. What are file permissions in Linux? Explain the meaning of `rwx` and how to change permissions using `chmod`.
- **rwx** stands for:
  - `r` = Read
  - `w` = Write
  - `x` = Execute
- Permission format: **owner/group/others**
- Change permission:
  ```bash
  chmod 755 filename   # Owner=rwx, Group=rx, Others=rx
  chmod u+x filename   # Add execute permission for user
  ```

---

### 6. How can you manage file ownership and groups using `chown` and `chgrp` commands?
- Change owner:
  ```bash
  sudo chown username filename
  ```
- Change group:
  ```bash
  sudo chgrp groupname filename
  ```
- Change both:
  ```bash
  sudo chown username:groupname filename
  ```

---

## **System Administration**

### 7. What are system services and daemons in Linux? How do you manage them using `systemctl`?
- **Services/Daemons**: Background processes (e.g., `sshd`, `httpd`).
- Manage with `systemctl`:
  ```bash
  sudo systemctl start service
  sudo systemctl stop service
  sudo systemctl enable service
  sudo systemctl status service
  ```

---

### 8. Explain how to schedule tasks in Linux using `cron` and `at`.
- **cron**: Schedules recurring tasks.
  - Edit cron jobs:
    ```bash
    crontab -e
    ```
    Example: Run script every day at midnight:
    ```bash
    0 0 * * * /path/to/script.sh
    ```
- **at**: Schedule a one-time task.
  ```bash
  at 5pm
  /path/to/script.sh
  ```

---

### 9. What is the purpose of the `/etc/fstab` file? How do you mount and unmount file systems?
- **/etc/fstab**: Defines file systems to be mounted at boot.
- Mount:
  ```bash
  sudo mount /dev/sda1 /mnt
  ```
- Unmount:
  ```bash
  sudo umount /mnt
  ```

---

## **Networking**

### 10. Describe the basic networking commands in Linux such as `ifconfig`, `ip`, `ping`, `netstat`, and `ss`.
- `ifconfig`: Displays and configures network interfaces.
- `ip`: Modern tool for IP configuration.
  ```bash
  ip addr show
  ```
- `ping`: Checks connectivity to a host.
- `netstat`: Shows network connections (deprecated, use `ss`).
- `ss`: Displays sockets and listening ports.

---

### 11. How do you configure a static IP address in Linux?
- Edit network configuration file (e.g., `/etc/network/interfaces` or use `nmcli`):
  ```bash
  sudo nano /etc/netplan/01-netcfg.yaml
  ```
  Example:
  ```yaml
  network:
    ethernets:
      eth0:
        dhcp4: no
        addresses: [192.168.1.100/24]
        gateway4: 192.168.1.1
        nameservers:
          addresses: [8.8.8.8, 8.8.4.4]
    version: 2
  ```
- Apply:
  ```bash
  sudo netplan apply
  ```

---

### 12. What are firewalls in Linux, and how do you configure them using `iptables` or `firewalld`?
- **Firewall**: Controls inbound/outbound traffic.
- Using `iptables`:
  ```bash
  sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
  ```
- Using `firewalld`:
  ```bash
  sudo firewall-cmd --add-service=http --permanent
  sudo firewall-cmd --reload
  ```

---

## **Package Management**

### 13. What are package managers in Linux? Compare `apt`, `yum`, and `dnf`.
- **Package Manager**: Tool for installing, updating, and removing software.
- **apt**: Used in Debian-based distros (Ubuntu).
- **yum**: Used in older RHEL/CentOS.
- **dnf**: Modern replacement for `yum`.

---

### 14. How do you install, update, and remove packages using a package manager?
- Debian-based:
  ```bash
  sudo apt update
  sudo apt install package
  sudo apt remove package
  ```
- RHEL-based:
  ```bash
  sudo dnf install package
  sudo dnf remove package
  ```

---

## **Monitoring and Performance**

### 15. What tools are available in Linux for monitoring system performance? Describe the use of `top`, `htop`, `vmstat`, and `iostat`.
- `top`: Displays running processes.
- `htop`: Interactive process viewer.
- `vmstat`: Memory and CPU stats.
- `iostat`: Disk I/O statistics.

---

### 16. How do you check disk usage and availability using commands like `df` and `du`?
- `df -h`: Shows disk space usage.
- `du -sh /path`: Shows size of a directory.

---

## **Security**

### 17. Explain the concept of SSH. How do you set up an SSH server and client in Linux?
- **SSH**: Secure Shell for remote login.
- Install SSH server:
  ```bash
  sudo apt install openssh-server
  ```
- Connect to remote machine:
  ```bash
  ssh user@host
  ```

---

### 18. What are SELinux and AppArmor? How do they enhance security in a Linux system?
- **SELinux**: Security-Enhanced Linux, mandatory access control.
- **AppArmor**: Profile-based access control.
- Both prevent unauthorized access by restricting applications.

---

## **Backup and Recovery**

### 19. How do you perform backups in Linux? Describe the use of tools like `rsync`, `tar`, and `dd`.
- `rsync`: Synchronize files:
  ```bash
  rsync -av /source /destination
  ```
- `tar`: Archive files:
  ```bash
  tar -czvf backup.tar.gz /path
  ```
- `dd`: Disk cloning:
  ```bash
  dd if=/dev/sda of=/dev/sdb
  ```

---

### 20. What are some strategies for system recovery in case of a failure?
- Keep regular backups.
- Use snapshots (LVM, Btrfs).
- Boot from live media for repairs.
- Restore from backup using `rsync` or `tar`.

---
