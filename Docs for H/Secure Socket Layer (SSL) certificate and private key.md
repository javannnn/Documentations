Here are the general steps you would need to take to do this:
1.  Install OpenSSL: OpenSSL is an open-source SSL toolkit that is commonly used to generate SSL certificates and private keys. If it's not already installed, you will need to install it on the Ubuntu VM running ERPnext/ጊዜ by running the following command:
```
sudo apt-get install openssl
```
2.  Create a directory for the certificate and key files: You will need to create a directory to store the certificate and key files. This directory can be located anywhere on the system. For example, you can create the directory at `/etc/openvpn/easy-rsa/keys` by running the following commands:
```
sudo mkdir -p /etc/openvpn/easy-rsa/keys
```
3.  Create the OpenVPN certificate authority (CA) and private key: The first step in creating the SSL certificate and private key is to create the OpenVPN certificate authority (CA) and private key. The CA is used to sign the SSL certificate and the private key is used to encrypt and decrypt the data being sent over the VPN.
```
sudo openssl req -nodes -new -x509 -keyout /etc/openvpn/easy-rsa/keys/ca.key -out /etc/openvpn/easy-rsa/keys/ca.crt
```
This command will create a private key file named "ca.key" and a certificate file named "ca.crt" in the `/etc/openvpn/easy-rsa/keys` directory.
4.  Create the server certificate and private key: Once the CA and private key have been created, you can create the server certificate and private key.
```
sudo openssl req -nodes -new -keyout /etc/openvpn/easy-rsa/keys/server.key -out /etc/openvpn/easy-rsa/keys/server.csr
```
This command will prompt you to enter information such as the common name (CN) and organization name, which will be included in the certificate. The command will create a private key file named "server.key" and a certificate signing request file named "server.csr" in the `/etc/openvpn/easy-rsa/keys` directory.
5.  Sign the server certificate: After the server certificate signing request has been created, you will need to sign it using the OpenVPN CA.
```
sudo openssl x509 -req -in /etc/openvpn/easy-rsa/keys/server.csr -CA /etc/openvpn/easy-rsa/keys/ca.crt -CAkey /etc/openvpn/easy-rsa/keys/ca.key -CAcreateserial -out /etc/openvpn/easy-rsa/keys/server.crt
```
This command will create a server certificate file named "server.crt"
Once the SSL certificate and private key have been generated, you will need to configure OpenVPN to use them.

6.  Point to the location of the SSL certificate and key files in the OpenVPN configuration file. In the server configuration file `/etc/openvpn/server.conf` you will need to specify the location of the certificate and key files by adding the following lines:
```
cert /etc/openvpn/easy-rsa/keys/server.crt
key /etc/openvpn/easy-rsa/keys/server.key
```
7.  Specify the location of the CA certificate: You will also need to specify the location of the CA certificate in the OpenVPN configuration file. This can be done by adding the following line:
```
ca /etc/openvpn/easy-rsa/keys/ca.crt
```
8.  Configure the client configuration files: You will also need to configure the client configuration files to point to the location of the certificate and key files and the location of the CA certificate. This is so that the clients can establish an encrypted connection with the VPN server.
Once this is done, you will have completed the process of generating an SSL certificate and private key and configuring OpenVPN to use them to encrypt data sent over the VPN connection.