# smb
% smb, samba

## nbtscan - scan network looking for hosts
#plateform/linux #target/remote #port/445 #protocol/smb #cat/RECON 
```
nbtscan -r <ip_range>
```

## smbclient with username and password
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT  
```
smbclient \\\\<ip>\\<share> -U "<user>%<password>"
```

## smbclient enumerate shares without password
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT  
```
smbclient -L \\\\<ip>
```


## smbclient sessions without password
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT  
```
smbclient \\\\<ip>\\<share> -U "<user>%"
```

## smbclient null session
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT  
```
smbclient \\\\<ip>\\<share> -U "%"
```

## smbclient enumerate shares
#plateform/linux #target/remote #port/445 #protocol/smb #cat/RECON
```
smbclient -L //<ip>
```

## smb: download files recursively
#plateform/linux #target/remote #port/445 #protocol/smb
```
smbget -R smb://<target-ip>/<Share>/<file>
```


## smb - find not signed  smb
#plateform/linux #target/remote #port/445 #protocol/smb #cat/RECON 
```
nmap -Pn -sS -T4 --open --script smb-security-mode -p445 <ip>
```

## smb mount folder
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT  
```
mount -t cifs //<ip>/C\$ /tmp/mnttarget/ -o username=<user> -o domain=<domain>
```

### smbclient download all files in the share drive without credential
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT  
```
smbget -R smb://<ip>/<share> 
```

### smbclient download all files in the share drive
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT  
```
smbget -R smb://<ip>/<share>  -U <username>
```