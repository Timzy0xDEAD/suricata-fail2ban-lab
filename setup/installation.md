
## Suricata & Fail2Ban Installation Script

### Update system packages
```bash
sudo apt update
sudo apt upgrade -y
```

### Install Suricata
```bash
sudo apt install suricata -y
```

### Verify Suricata installation
```bash
suricata -V
```

### Start Suricata service
```bash
sudo systemctl start suricata
```

### Check Suricata service status
```bash
sudo systemctl status suricata 
```

### Install Fail2Ban
```bash
sudo apt install fail2ban -y
```

### Verify Fail2Ban installation
```bash
fail2ban-client -V
```