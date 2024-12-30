# Beginner-s-Guide-to-SSH-Secure-Remote-Access-Made-Simple
---
Beginner's Guide to SSH: Secure Remote Access Made Simple
SSH, or Secure Shell, is the go-to network protocol for securely accessing remote servers. Whether you're managing a Raspberry Pi, a virtual machine, or a remote server, SSH offers a robust and encrypted communication channel to connect and manage systems from anywhere. In this guide, we'll walk you through the basics of SSH, setting up an SSH server, and connecting to it from your client machine.
What is SSH?
SSH operates on a client-server model, where the "server" is the system you want to access, and the "client" is the machine you're connecting from. The communication channel between the two is encrypted, making it safe from eavesdropping and hijacking. Authentication is typically handled through SSH keys (public and private), though passwords can also be used.
One of the most popular implementations of SSH is OpenSSH, an open-source tool available on Linux, BSD, and Windows platforms.
Getting Started with SSH
Prerequisites
Sudo access on the server machine.
Internet connection to download necessary packages.
A second system in your network (another computer, remote server, or virtual machine).

Step 1: Install the SSH Server
Before setting up the SSH server, ensure your Ubuntu system is up-to-date:
sudo apt update && sudo apt upgrade
Next, install the OpenSSH server package:
sudo apt install openssh-server
Step 2: Verify the SSH Service Status
After installation, the SSH service should start automatically. To confirm, check the service status:
sudo systemctl status ssh
Look for the "Active" status in the output. If the service isn't running, start it with:
sudo systemctl enable --now ssh
Step 3: Allow SSH Through the Firewall
If you're using Ubuntu's firewall, UFW (Uncomplicated Firewall), you'll need to allow SSH traffic:
sudo ufw allow ssh
You can check the firewall status with:
sudo ufw status
Your SSH server is now set up and ready for connections.
Connecting to the SSH Server
Most Linux distributions come with an SSH client pre-installed. If it's not installed, you can add it with:
sudo apt install openssh-client
To connect to your SSH server, you'll need the server's IP address and the username you want to connect with. On the server, find the IP address using:
ip a
With the IP address in hand, initiate the connection from your client machine:
ssh username@server_ip
Replace username with your actual username on the server and server_ip with the server's IP address. On your first connection, SSH will ask to verify the server's authenticity:
Are you sure you want to continue connecting (yes/no)? yes
Once confirmed, you'll be prompted for your password. Enter it, and you'll be logged into the remote server.
