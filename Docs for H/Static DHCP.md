To configure the DHCP server on the Proxmox host to always assign the same IP address to the VM based on its MAC address, you will need to perform the following steps:

1.  Log in to the Proxmox host's web interface by navigating to the host's IP address in a web browser.
    
2.  Navigate to the "Network" section and select the "DHCP" tab.
    
3.  Locate the DHCP server configuration that corresponds to the network interface that the VM is using.
    
4.  Scroll down to the "Static DHCP leases" section.
    
5.  Click on the "Add" button to create a new DHCP lease.
    
6.  Enter the MAC address of the VM's network interface in the "MAC" field
    
7.  Enter the desired IP address for the VM in the "IP" field
    
8.  Optionally you can give a name for the DHCP Lease
    
9.  Click on the "Save" button
    

After you complete these steps, the DHCP server on the Proxmox host should always assign the same IP address to the VM based on its MAC address, which will allow the IP address of the VM to stay constant and prevent the need to change your port forwarding or firewall rules every time the VM reboots.

Again, it's recommended to consult the Prox mox documentation for more detailed instructions and troubleshooting guides and make sure the DHCP reservation doesn't conflict with any other IP address on your network and that the IP address you choose is inside the DHCP pool defined by the DHCP server.[[Avoiding DCHP Conflicts]]