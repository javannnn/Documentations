
To configure the VM network to use bridged networking, you will need to perform the following steps:

1.  Log in to the Proxmox host's web interface by navigating to the host's IP address in a web browser.
    
2.  Navigate to the "VM" section and select the "Virtual Machines" tab.
    
3.  Locate the VM running ጊዜ and click on the "Edit" button.
    
4.  In the "Hardware" section, click on the "Add" button to add a new network device.
    
5.  Select "Bridged" as the "Model" for the new network device.
    
6.  Select the host network interface that the VM should use for bridged networking.
    
7.  Click on "Save"
    

After these steps, the VM should be configured to use bridged networking and receive an IP address from the host's DHCP server, which will make it directly reachable by external clients.

Please note that in some cases, you may need to adjust the DHCP settings on the host network interface to ensure that the VM is correctly assigned an IP address, you also may need to consult your network administrator or refer to Proxmox's official documentation for more detailed instructions and troubleshooting guides.

It's also recommended to configure your DHCP server to always assign the same IP address to the VM based on its MAC address, this way the IP stays constant and you don't have to change your port forwarding or firewall rules every time the VM reboots. [[Static DHCP]]