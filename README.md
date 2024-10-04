
# Ubuntu GUI Setup on AWS EC2

## Project Overview

This project involves setting up a fully functional Ubuntu Graphical User Interface (GUI) on an AWS EC2 instance, allowing for remote desktop access via xRDP. This project was completed as part of my internship at Trimbak InfoTech and serves as a practical demonstration of cloud resource management and remote access configuration.

## Table of Contents

- [Technologies Used](#technologies-used)
- [Prerequisites](#prerequisites)
- [Installation Steps](#installation-steps)
- [Usage](#usage)
- [Key Takeaways](#key-takeaways)
- [Future Work](#future-work)
- [Acknowledgments](#acknowledgments)

## Technologies Used

- **Amazon Web Services (AWS)**: EC2 for cloud computing.
- **Ubuntu**: Operating system for the EC2 instance.
- **xRDP**: Remote desktop protocol server for accessing the GUI.
- **PuTTY**: SSH client for connecting to the EC2 instance.

## Prerequisites

Before starting this project, ensure you have:

- An active AWS account.
- Basic knowledge of AWS services and EC2.
- PuTTY installed on your local machine for SSH access.

## Installation Steps

1. **Launch EC2 Instance:**
   - Log in to your AWS Management Console.
   - Navigate to EC2 and click on "Launch Instance."
   - Select the **Ubuntu Server** (choose the desired version) and select the **t3.2xlarge** instance type.
   - Configure instance settings, including a pre-configured key pair and security group.
   - Launch the instance.

2. **Access the Instance via PuTTY:**
   - Open PuTTY and enter the public DNS or IP address of the instance.
   - Load your private key file (.pem) in the SSH section under "Connection" > "SSH" > "Auth."
   - Click "Open" to connect.

3. **Update the System:**
   - Once connected, run the following commands to update and upgrade the system:
     ```bash
     sudo apt update
     sudo apt upgrade
     ```

4. **Install xRDP:**
   - Install xRDP to enable remote desktop access:
     ```bash
     sudo apt install xrdp
     ```
   - Set a password for the machine to access via RDP:
     ```bash
     sudo passwd ubuntu
     ```

5. **Enable and Start xRDP:**
   - Start the xRDP service:
     ```bash
     sudo systemctl enable xrdp
     sudo systemctl start xrdp
     ```

6. **Install Ubuntu Desktop (GNOME):**
   - Install the Ubuntu Desktop environment:
     ```bash
     sudo apt install ubuntu-desktop
     ```

7. **Check RDP Connection:**
   - Verify RDP access by rebooting the instance:
     ```bash
     sudo reboot
     ```
   - Connect via Remote Desktop from your local machine using the public IP address of the instance.

8. **Demonstrate Functionality:**
   - Open Firefox and other pre-installed applications to showcase the functionality of the GUI.

9. **Power Off the Instance:**
   - Once all tests are completed, power off the EC2 instance to avoid additional charges.

## Usage

This setup allows users to access an Ubuntu GUI remotely, making it easier for those who prefer graphical interfaces for tasks such as application management, web browsing, and development work.

## Key Takeaways

- Gained hands-on experience in configuring cloud environments using AWS.
- Learned how to install and manage remote desktop protocols.
- Enhanced understanding of Linux-based operating systems and GUI installations.

## Future Work

- Explore additional configurations for enhanced security.
- Implement automation scripts for quicker deployment of similar environments.
- Consider integrating additional software for specific use cases, such as development tools or database management systems.

## Acknowledgments

I would like to thank Trimbak InfoTech for the opportunity to work on this project and for their support throughout my internship.
