# Elevate Labs Task 4: Firewall Setup and Testing

## Overview
This repository contains deliverables for Day 4 of the Elevate Labs Cybersecurity Internship (June 27, 2025). The task involves configuring and testing firewall rules using UFW on Ubuntu to block and allow specific ports.

## Task Details
- **Objective**: Configure firewall rules to block Telnet (port 23) and allow SSH (port 22), then test and restore.
- **Tool Used**: UFW (Uncomplicated Firewall).
- **Target**: Localhost (`127.0.0.1`).
- **Deliverables**:
  - `firewall_setup_report.md`: Detailed report of configuration and testing.
  - `Screenshots/ufw_block_rule.png`: Screenshot of Telnet test.
  - `notes.md`: UFW setup commands.

## Findings
- Blocked Telnet (port 23): Connection refused, rule effective.
- Allowed SSH (port 22): Connection successful.
- Restored original state by removing Telnet block.

## Instructions to Review
- Read `firewall_setup_report.md` for steps and summary.
- View `Screenshots/` for visual evidence.
- Check `notes.md` for commands.

## Portfolio
This task is part of my Elevate Labs internship portfolio: [Elevate-Labs-Internship-Tasks](https://github.com/Nucl3arAt0m/Elevate-Labs-Internship-Tasks).
