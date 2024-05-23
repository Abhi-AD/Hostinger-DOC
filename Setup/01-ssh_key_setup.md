### How to access server via ssh and setup ssh key for passwordless authentication
Without setting up SSH Key It will ask Password each time we try to get access

- To Get Access via SSH
```sh
Syntax:- `ssh -p <SSH_PORT> <USERNAME>@<SSH_IP>`
Example:- `ssh -p 21350 root@216.32.44.12`
```

#### Note:- Run Below Commands on Your Local Machine, Not on Your VPS or Remote Server
- Generate SSH Key
```sh
ssh-keygen -t rsa -b <file_size>
```

- Extra Security Layer(PassPharse):
```bash
     <default_password>
```




- Copy SSH Public Key to Remote Server (Not for Windows)
```sh
Syntax:- `ssh-copy-id -p <SSH_PORT> -i ~/.ssh/keyname.pub <USERNAME>@<SSH_IP>`
Example:- `ssh-copy-id -p 21350 -i ~/.ssh/id_rsa.pub root@216.32.44.12`
```

- Copy Public Key to Remote Server (for Windows)
1. Make sure you have .ssh folder in remote server
```sh
Syntax:- `ssh -P <SSH_PORT> <USERNAME>@<SSH_IP> "mkdir <USERNAME>/.ssh"`
Example:- `ssh -P 21350 root@216.32.44.12 "mkdir root/.ssh"`
```
2. Copy Public Key
```sh
Syntax:- `scp -P <SSH_PORT> SSH_PUBLIC_KEY_PATH <USERNAME>@<SSH_IP>:/root/.ssh/authorized_keys`
Example:- `scp -P 21350 <directory_for_user_account>/.ssh\id_rsa.pub root@216.32.44.12:/root/.ssh/authorized_keys`
```
