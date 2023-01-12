1.  Obtain a public IP address: You will need a public IP address that can be used to access ጊዜ remotely. This can be obtained from your internet service provider.
    
2.  Configure port forwarding on Proxmox host: You will need to configure port forwarding on the Proxmox host to forward incoming traffic on a specific port (e.g., TCP port 80) to the internal IP address of the VM running ጊዜ. [[Proxmox Host Port Forwarding]]
    
3.  Configure the VM Network: Make sure the VM is configured to use bridged networking so that it will receive an IP address from the host's DHCP server and be directly reachable by external clients. [[Proxmox VM bridged Network]]
    
4.  Install OpenVPN in the VM: Next, you will need to install OpenVPN in the VM where the ጊዜ instance is running. OpenVPN is an open-source software application that implements virtual private network (VPN) techniques to create secure point-to-point or site-to-site connections.[[Installin OpenVPN in the VM]]
    
5.  Configure OpenVPN: After OpenVPN has been installed, you will need to configure it by creating a server configuration file in the VM. This file will contain the settings for the VPN server, including the IP address of the VM, the port to be used for the VPN connection, and the encryption settings to be used.[[Server configuration file in order to configure OpenVPN]]
    
6.  Generate SSL certificate: In order to secure the VPN connection, you will need to generate a secure socket layer (SSL) certificate and private key. These will be used to encrypt the data being sent over the VPN connection. [[Secure Socket Layer (SSL) certificate and private key]]
    
7.  Set up client configuration: After the server is configured and the SSL certificate is generated, you will need to set up the client configuration. This involves creating a client configuration file that will be used by remote users to connect to the VPN server. [[Creating a client configuration file that will be used by remote users to connect to the VPN server]]
    
8.  Test the VPN connection: Finally, you will need to test the VPN connection by having a remote user connect to the VPN server using the client configuration. If the connection is successful and the user is able to access ጊዜ, then the configuration is complete.[[Test the VPN connection]]