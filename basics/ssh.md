# Secure Shell (SSH):

Secure shell(SSH) are the secured way to connect with `remote server`. Previously we used `TelNet`, where this will pass the request and response in the plain text format, as this is vulnerable to Hackers.

## Components of SSH:

1. SSH Server, which runs in the server we need to connect remotely. It will contantly listen to any incoming request fron Client
2. SSH Client, which runs in the clinet machine / user machine.

## Accessing via SSH:

So whenever we want to connect to remote server using SSH, the clinet and server will initaite a `secure tunnel` connection to communicate and server will request for authentication

1. Password, traditional but not so secure
2. SSH keys (highly recommended)
    1. SSH public key -> Stored in the SSH server
    2. SSH private key -> Stored in users machine and unique to the user/client.

SSH server will validate the private key sent by the user with the public key it has, post that the client wil have the access to the correspodning server.

## File transfer in SSH:

We can also transfer the files 

1. SFTP = SSH File Transfer Protocol
2. SC = Secure Copy
