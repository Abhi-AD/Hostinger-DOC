## How to Working the Admin Side
### After Port Change to login
```bash
     ssh -p <SSH_PORT> <username>@<SSH_IP>
```

### Check the user
```bash
     cut -d: -f1 /etc/passwd
```

### Check the [config file](https://github.com/openssh/openssh-portable/blob/master/sshd_config)
```bash
     nano /etc/ssn/ssnd_config
```

### Create User
```bash
     adduser <newusername>
```
### Delete User
```bash
     deluser <username>
```
### Delete User Directory
```bash
     rm -r <username>
```

### User to admin modify
```bash
     usermod -aG sudo "<username>"
```
### Check the config file  latest sudo admin
```bash
     sudo nano /etc/ssn/ssnd_config
```
### Check the  sudo admin
```bash
     grep -Po '^sudo.+:\K.*$' /etc/group
```

### Reset SSH Configuration file <br/>


### Change the SSH PORT
- Open `/etc/ssh/ssnd_config`  and find `#Port 22`.
- Uncomment it by removing `#`, save & exit

### Firewall Restart
```bash
     service ssh restart
```

### Disable Root Login
Edit `/etc/ssh/sshd_config`
Find: `PermitRootLogin yes`
Change to: `PermitRootLogin no`
Save & Exit
`Firewall Restart`


### Disable Password
Edit `/etc/ssh/sshd_config`
Find: `PasswordAuthentication yes`
Change to: `PasswordAuthentication no`
Save & Exit
`Firewall Restart`

