
Fail2Ban Configuration

Create a local configuration file:

sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local

Edit the configuration:

sudo nano /etc/fail2ban/jail.local

Add or verify the SSH protection settings:

[sshd]
enabled = true
port = ssh
maxretry = 5
bantime = 600