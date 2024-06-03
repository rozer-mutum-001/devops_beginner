# Useful ssh knowledge


## SSH (Secure Shell)
- It is a **protocol** used to securely connect to a remote computer or server.
- It provides **encrypted** communication and is widely used for remote administration, file transfers and securing network services.
- When one say "SSH into a server," it typically means using the SSH client to connect to the SSH server on the remote machine.

## SSH client
- Tool use to connect to a remote server.
- Mostly installed by default.
- Installed in the server ***from where*** we want to perform ssh connection.

## SSH server
- Software that runs on the remote machine.
- Installed in the server ***to where*** we want ssh connection to be performed.

## Check availability of ssh-client package
```
ssh -V
```

## To install ssh client
```
sudo apt update
sudo apt install openssh-client
```

## To install ssh server
```
sudo apt update
sudo apt install openssh-server
sudo systemctl start ssh
sudo systemctl enable ssh
```

## Generate ssh key
```
ssh-keygen -f ~/.ssh/your_key_name
```
This will generate 2 keys under `~/.ssh`
- Private key - `~/.ssh/your_key_name`
- Public key - `~/.ssh/your_key_name.pub`

Public key needs to be copied to the server where to be connected. There are of 2 ways:

## Copying the Public Key to the Remote Server
### 1. Using ssh-copy-id
```
ssh-copy-id -i ~/.ssh/your_key_name.pub username@remote_ip_address
```

### 2. Manually
1. Copy the content of the public key
```
cat ~/.ssh/my_custom_key.pub
```
2. Log in to the remote server
3. Create an `authorized_keys` file under the folder `~/.ssh`
```
mkdir -p ~/.ssh
nano ~/.ssh/authorized_keys
```
4. Paste the public key into the `authorized_keys` file and save.
5. Set the correct permissions
```
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

## Connect to the remote/desire server
```
ssh -i ~/.ssh/your_key_name username@remote_ip_address
```