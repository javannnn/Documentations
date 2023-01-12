To configure port forwarding on a Proxmox host to forward incoming traffic on a specific port to the internal IP address of the VM running ጊዜ, you will need to perform the following steps:

1.  Log in to the Proxmox host's web interface by navigating to the host's IP address in a web browser.
    
2.  Navigate to the "Network" section and select the "Firewall" tab.
    
3.  Click on the "Add" button to create a new firewall rule.
    
4.  In the "Action" field, select "Accept" to allow incoming traffic to reach the VM.
    
5.  In the "Proto" field, select the protocol (TCP or UDP) that the traffic should use. For example, if you want to forward incoming traffic on port 80 to the VM, you would select "TCP".
    
6.  In the "Dst. Port" field, enter the port number that the traffic should use. For example, to forward incoming traffic on port 80 to the VM, you would enter "80".
    
7.  In the "Destination" field, enter the internal IP address of the VM running ጊዜ.
    
8.  Click the "Save" button to create the rule and enable port forwarding.
    

Please note that this is a general explanation of the process of configuring port forwarding on Proxmox host and you may need to refer to the Proxmox's official documentation for more detailed instructions and troubleshooting guides.

Also, as a security measure, it's a good idea to only allow the minimum set of ports necessary for the service to function, and to regularly review firewall rules and remove those no longer in use to prevent any unauthorized access.