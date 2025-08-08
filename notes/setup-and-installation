
# Setup and Installation (Ubuntu)

## Introduction

This guide will help you prepare your Ubuntu system to run Ansible for automating Cisco network devices. It covers installing Ansible, setting up a Python virtual environment, installing required Ansible collections, and preparing your Cisco devices for automation.

---

## 1. Install Ansible on Ubuntu

Update your package list and install Ansible using `apt`:

```bash
sudo apt update
sudo apt install ansible -y
```

Verify the installation:

```bash
ansible --version
```

You should see Ansible’s version and Python interpreter details.

---

## 2. Create a Python Virtual Environment (Recommended)

To keep your Ansible installation isolated from system packages and avoid version conflicts, create and activate a Python virtual environment:

```bash
sudo apt install python3-venv -y
python3 -m venv ~/ansible-venv
source ~/ansible-venv/bin/activate
```

Upgrade pip and install Ansible inside the virtual environment:

```bash
pip install --upgrade pip
pip install ansible paramiko
```

---

## 3. Install Required Ansible Collections

For Cisco IOS device automation, install the Cisco IOS collection via Ansible Galaxy:

```bash
ansible-galaxy collection install cisco.ios
```

Verify installed collections:

```bash
ansible-galaxy collection list
```

---

## 4. Prepare Your Cisco Devices

Ensure your Cisco devices are ready for Ansible automation:

- SSH must be enabled and configured on the device.
- The device must be reachable from your Ubuntu machine via SSH.
- You should have a user account with privileges to configure the device.

Example to enable SSH and create an admin user on Cisco IOS:

```bash
conf t
ip domain-name example.com
crypto key generate rsa modulus 2048
ip ssh version 2
username admin privilege 15 secret yourpassword
line vty 0 4
transport input ssh
login local
exit
write memory
```

---

## 5. Disable SSH Host Key Checking (Optional for Labs)

To avoid SSH host key verification errors in lab or testing environments, disable host key checking temporarily:

```bash
export ANSIBLE_HOST_KEY_CHECKING=False
```

> **Warning:** Do **not** disable host key checking in production environments — this bypasses an important security measure.

---

## 6. Set Up Project Folder Structure

Create directories to organize your Ansible project:

```bash
mkdir -p ~/ansible_project/{inventory,playbooks,group_vars,roles,scripts}
```

- `inventory/` — for host inventory files  
- `playbooks/` — for your YAML playbooks  
- `group_vars/` — for group variable files  
- `roles/` — optional modular task collections  
- `scripts/` — optional helper scripts  

---

## Conclusion

With Ansible installed and your Cisco devices prepared, you are now ready to write playbooks that automate network configuration and management, saving time and reducing manual errors.

---

## References

- [Ansible Installation Guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)  
- [Cisco IOS Ansible Collection](https://galaxy.ansible.com/cisco/ios)  
- [Cisco SSH Configuration](https://www.cisco.com/c/en/us/support/docs/security-vpn/secure-shell-ssh/4145-ssh.html)  
