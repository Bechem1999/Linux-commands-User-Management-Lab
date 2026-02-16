# Linux-commands-User-Management-Lab
## Cybersecurity Associate Assignment 1

---

## Lab Title
Linux User and Group Management with File Permission Control (Kali Linux)

---

## Objective

The objective of this lab was to simulate real-world enterprise user management by:
- Creating Linux users and groups
- Managing file ownership
- Implementing secure file permissions
- Applying the Principle of Least Privilege
- Verifying system configurations
  ---

## Scenario Overview

As a System Administrator at TechCorp Solutions, I was required to:

1. Configure private user workspaces for the Marketing Department
2. Configure a shared collaborative workspace for the IT Department
  ---

# 🔹 PART 1: Marketing Department (Private Access)

### Tasks Performed

- Created marketing group
- Created 5 users
- Added users to group
- Created individual report files
- Assigned file ownership
- Applied 700 permissions

### Commands Executed

```bash
groupadd marketing

useradd -m alice_m
useradd -m bob_m
useradd -m carol_m
useradd -m david_m
useradd -m emma_m

usermod -aG marketing alice_m
usermod -aG marketing bob_m
usermod -aG marketing carol_m
usermod -aG marketing david_m
usermod -aG marketing emma_m

mkdir -p /home/shared/marketing
touch /home/shared/marketing/*.txt
chown user /home/shared/marketing/file
chmod 700 /home/shared/marketing/*.txt

### Expected Permission Output
-rwx-----
