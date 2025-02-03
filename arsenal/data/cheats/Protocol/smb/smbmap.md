# smbmap
% smb, samba

## smbmap
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT 

```
smbmap -H <ip> -u "<user>%<password>"
```

## smbmap - enumerate shares with null access
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT 

```
smbmap -u "" -p "" -P 445 -H <ip>
```

## smbmap - enumerate shares guest access
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT 
```
smbmap -u "guest" -p "" -P 445 -H <ip>
```

## smbmap - enumerate shares enumerate root of all shares
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT 
```
smbmap -H <ip> -u <user> -p <password> -d <domain> -r
```

## smbmap - recursively enumerate dirs, and files
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT 
```
smbmap -H <ip> -u <user> -p <password> -d <domain> -R <path> --depth 1
```

= ip: 192.168.1.0/24
