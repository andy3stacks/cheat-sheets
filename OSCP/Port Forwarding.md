# Port Forwarding
## Socat
### Command
```bash
socat -ddd TCP-LISTEN:<LISTENING_PORT>,fork TCP:<DESTINATION_IP>:<DESTINATION_PORT>
```
#### Example
- EXAMPLE01 IP: `192.168.50.63`
- POSTGRESQL DB IP/PORT: `10.2.50.215:5432`
##### Remote Listener
```
example@example01:/home/example$ socat -ddd TCP-LISTEN:2345,fork TCP:10.4.50.215:5432
```
##### Attacker Connect
```
kali@kali:~$ psql -h 192.168.50.63 -p 2345 -U postgres
```
