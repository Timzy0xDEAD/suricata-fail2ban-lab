## Network Configuration
### Defense Machine (Ubuntu Server)
#### Assign IP address
```bash
sudo ip addr add 192.168.10.1/24 dev enp0s8
sudo ip addr add 192.168.20.1/24 dev enp0s9
```

#### enable interface
```bash
sudo ip link set enp0s8 up
sudo ip link set enp0s9 up
```

#### for Permanent IP configuration

##### Backup the current Netplan configuration:
```bash
ls /etc/netplan/
sudo cp /etc/netplan/50-cloud-init.yaml /etc/netplan/50-cloud-init.yaml.bak
```
##### Edit Netplan to assign static IPs:
```bash
network:
    version: 2
    ethernets:
        enp0s8:
            dhcp4: no
            addresses:
              - 192.168.10.1/24
        enp0s9:
            dhcp4: no
            addresses:
              - 192.168.20.1/24
```

##### Apply changes:
```bash
sudo netplan apply
```
### Victim Machine
#### Assign IP address
```bash
sudo ip addr add 192.168.10.10/24 dev eth0
sudo ip link set eth0 up
```
#### Set default gateway
```bash
sudo ip route add default via 192.168.10.1
```
### Attacker Machine (Kali)
#### Assign IP address
```bash
sudo ip addr add 192.168.20.10/24 dev eth0
sudo ip link set eth0 up
```
#### Set default gateway
```bash
sudo ip route add default via 192.168.20.1
```