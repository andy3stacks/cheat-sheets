# Port Forwarding
## Socat
### Command
```bash
socat -ddd TCP-LISTEN:<LISTENING_PORT>,fork TCP:<DESTINATION_IP>:<DESTINATION_PORT>
```
### Example
- EXAMPLE01 IP: `192.168.50.63`
- POSTGRESQL DB IP/PORT: `10.2.50.215:5432`
#### Remote Listener
```
example@example01:/home/example$ socat -ddd TCP-LISTEN:2345,fork TCP:10.4.50.215:5432
```
#### Attacker Connect
```
kali@kali:~$ psql -h 192.168.50.63 -p 2345 -U postgres
```
___

## OpenSSH
### Syntax
```
[LOCAL_IP:]LOCAL_PORT:DEST_IP:DEST_PORT
```
### Command
```
ssh -N -L 0.0.0.0:<LOCAL_PORT>:<DEST_IP>:<DEST_PORT> <MIDDLE_USER>@<MIDDLE_IP>
```
### Example
- EXAMPLE01 IP: `192.168.50.63`
- MIDDLE IP: `10.2.50.215`
- DEST IP/PORT: `172.16.50.217:445`
#### Remote Listener
```
example@example01:/home/example$ ssh -N -L 0.0.0.0:4455:172.16.50.217:445 admin@10.4.50.215
```
#### Attacker Connect
```
kali@kali:~$ smbclient -p 4455 -L //192.168.50.63/ -U hr_admin --password=Welcome1234
```
