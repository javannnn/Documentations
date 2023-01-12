The server configuration file will contain settings for the VPN server, including the IP address of the VM, the port to be used for the VPN connection, and the encryption settings to be used.

1.  Create the server configuration file: The configuration file is usually located in '/etc/openvpn/server.conf' and you can use any text editor such as nano or vim to create or edit the file.
    
2.  Define the protocol and port to use: In the server configuration file, you need to specify the protocol (UDP or TCP) and port number that the VPN server should listen on. For example, to listen on UDP port 1194, you would add the following line to the configuration file:
```
proto udp
port 1194
```
3.  Define the IP address of the VPN server: In the server configuration file, you will also need to specify the IP address of the VPN server. In this case, you would use the IP address of the Ubuntu VM running ERPnext/ጊዜ. You can use the following line in the configuration file to specify the IP address:
```
server <IP-address> <netmask>
```
replace <IP-address> and <netmask> with your values.
4.  Configure the encryption settings: You will also need to specify the encryption settings that the VPN server should use. You can use the built-in settings, or you can create your own settings by using a different encryption algorithm or key length. It's important to use encryption settings that provide a good balance of security and performance.
    
5.  Enable routing: To allow client machines to connect to the internal network through the VPN server, you will need to enable IP forwarding and set up the appropriate routing rules. You can use the following line in the configuration file to enable IP forwarding:
```
push "redirect-gateway def1"
```
6.  Enable authentication: You will also need to configure the authentication settings for the VPN server. This can be done by using a shared secret key or a certificate-based authentication method.

This is a general explanation of the configuration process, and you may need to refer to the OpenVPN documentation for more detailed instructions and troubleshooting guides. Also, make sure to use best practices for the configuration of the VPN server and to consider the security and performance of your setup.