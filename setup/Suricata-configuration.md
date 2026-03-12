2. Configuration
Suricata Configuration

Edit the Suricata configuration file:

sudo nano /etc/suricata/suricata.yaml

Locate the af-packet section and set the network interface:

af-packet:
  - interface: ens33

(Replace ens33 with your actual network interface.)

Update Suricata rules:

sudo suricata-update

Restart Suricata to apply changes:

sudo systemctl restart suricata
