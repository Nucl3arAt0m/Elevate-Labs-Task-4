# Firewall Setup Report - Elevate Labs Task 4

## Task Overview
- **Objective**: Configure and test firewall rules on my Linux PC for Day 4 of the Elevate Labs Cybersecurity Internship (June 27, 2025).
- **Tool Used**: UFW (Uncomplicated Firewall) on Ubuntu.
- **Goal**: Block inbound traffic on port 23 (Telnet), allow port 22 (SSH), test rules, and restore original state.

## Firewall Configuration Steps

1. **Installed and Enabled UFW**:
   - Commands:
     ```bash
     sudo apt update
     sudo apt install ufw
     sudo ufw enable
     ```
   - Outcome: UFW activated as the firewall management tool.

2. **Listed Current Rules**:
   - Command:
     ```bash
     sudo ufw status
     ```
   - Initial Output: No rules (empty).

3. **Blocked Inbound Telnet (Port 23)**:
   - Command:
     ```bash
     sudo ufw deny 23/tcp
     ```
   - Verified:
     ```bash
     sudo ufw status
     ```
     - Output:
       ```
       Status: active
       To                         Action      From
       --                         ------      ----
       23/tcp                     DENY        Anywhere
       ```

4. **Tested Telnet Block**:
   - Installed Telnet:
     ```bash
     sudo apt install telnet
     ```
   - Tested connection:
     ```bash
     telnet 127.0.0.1 23
     ```
   - Result: `Connection refused`, confirming the block.
   - Screenshot: `Screenshots/ufw_block_rule.png`.

5. **Allowed SSH (Port 22)**:
   - Command:
     ```bash
     sudo ufw allow 22/tcp
     ```
   - Verified:
     ```bash
     sudo ufw status
     ```
     - Output:
       ```
       Status: active
       To                         Action      From
       --                         ------      ----
       23/tcp                     DENY        Anywhere
       22/tcp                     ALLOW       Anywhere
       ```
   - Tested SSH:
     ```bash
     ssh localhost
     ```
     - Result: Successful connection.

6. **Removed Telnet Block Rule**:
   - Command:
     ```bash
     sudo ufw delete deny 23/tcp
     ```
   - Verified:
     ```bash
     sudo ufw status
     ```
     - Output:
       ```
       Status: active
       To                         Action      From
       --                         ------      ----
       22/tcp                     ALLOW       Anywhere
       ```

## How Firewall Filters Traffic
- **Mechanism**: UFW filters network traffic by applying rules to allow or block packets based on port, protocol (TCP/UDP), and source/destination IP.
- **Stateful Filtering**: Tracks connection states, allowing return traffic for established sessions (e.g., SSH responses).
- **Task Example**:
  - Blocking port 23 (Telnet) prevented inbound connections, reducing unauthorized access risks.
  - Allowing port 22 (SSH) ensured secure remote access.
- **UFW Advantage**: Simplifies iptables configuration with user-friendly commands, making firewall management accessible.

## Learnings
- **Firewall Management**: UFW enables easy rule creation and testing for traffic control.
- **Security Impact**: Blocking unused ports (e.g., Telnet) reduces attack surfaces.
- **Next Steps**: Explore advanced rules (e.g., IP-specific filtering) and stateful firewall configurations.

## Files Included
- `screenshots/ufw_block_rule.png`: Screenshot of Telnet connection test.
- `firewall_setup_report.md`: This report.
- `README.md`: Task overview.
- `notes.md`: UFW setup commands.

## Portfolio
This task is part of my Elevate Labs internship portfolio: [Elevate-Labs-Internship-Tasks](https://github.com/Nucl3arAt0m/Elevate-Labs-Internship-Tasks).
