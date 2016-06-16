# ipv4_secondaries_bug

After running `vagrant up`, the debug output contains the following text:
```
...
"ansible_eth1": {
                "active": true, 
                "device": "eth1", 
                "ipv4": {
                    "address": "192.168.56.116", 
                    "broadcast": "192.168.56.255", 
                    "netmask": "255.255.255.0", 
                    "network": "192.168.56.0"
                }, 
                "ipv4_secondaries": [
                    {
                        "address": "10.100.1.10", 
                        "broadcast": "10.100.1.255", 
                        "netmask": "255.255.255.0", 
                        "network": "10.100.1.0"
                    }
                ], 
...
```

The expected output contains:
```
...
"ansible_eth1": {
                "active": true, 
                "device": "eth1", 
                "ipv4":
                {
                        "address": "10.100.1.10", 
                        "broadcast": "10.100.1.255", 
                        "netmask": "255.255.255.0", 
                        "network": "10.100.1.0"
                },
  ...
  ```
