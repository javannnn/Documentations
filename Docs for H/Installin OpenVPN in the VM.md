*  Download the OpenVPN package: On Ubuntu, you can download the OpenVPN package from the Ubuntu package repository by running the following command in the terminal:

```
sudo apt-get install openvpn
```

* Create OpenVPN Configuration file: You'll need to create a server configuration file for OpenVPN in your Ubuntu VM. This file will contain the settings for the VPN server, including the IP address of the VM, the port to be used for the VPN connection, and the encryption settings to be used. The configuration file location is usually '/etc/openvpn/server.conf'

* Generate SSL certificate: To secure the VPN connection, you will need to generate a secure socket layer (SSL) certificate and private key. You can use the easy-rsa script that is included with the OpenVPN package to generate the necessary certificate and key files. By default, the easy-rsa script is located in the `/usr/share/easy-rsa` directory.

* . Start the OpenVPN service: Once you have finished the previous steps, you can start the OpenVPN service by running the following command:
```
sudo systemctl start openvpn@server

```
* Enable OpenVPN service to start automatically on system reboot
```
sudo systemctl enable openvpn@
```

Please note that these are the general steps to install OpenVPN on Ubuntu, you should refer to the OpenVPN documentation for more detailed instructions and troubleshooting guides and make sure that your Ubuntu version is compatible with the OpenVPN version you are installing. Also, make sure that your Ubuntu VM is updated before the installation.