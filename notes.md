# UFW Setup Notes
- Installed UFW: `sudo apt install ufw`.
- Enabled UFW: `sudo ufw enable`.
- Blocked Telnet: `sudo ufw deny 23/tcp`.
- Tested Telnet: `telnet 127.0.0.1 23`.
- Allowed SSH: `sudo ufw allow 22/tcp`.
- Tested SSH: `ssh localhost`.
- Removed Telnet rule: `sudo ufw delete deny 23/tcp`.
- Verified rules: `sudo ufw status`.
