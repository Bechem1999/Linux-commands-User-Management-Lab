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
- verifying system configurations

  ---

## Tools used

- Kali Linux
- Linux Terminal
- GitHub
- Virtual Machine (VMware)

## Scenario Overview

As a System Administrator at TechCorp Solutions, I was required to:

1. Configure private user workspaces for the Marketing Department
2. Configure a shared collaborative workspace for the IT Department
  ---

# 🔹 PART 1: Marketing Department (Private Access)

### Tasks Performed

-Created marketing group
- Created 5 users
- Added users to group
- Created individual report files
- Assigned file ownership
- Applied 700 permissions

## Step by step process

- I started by logging into my Kali linux and on the terminal i used my root account by putting the command "sudo su"
- I created the marketing group using the command "groupadd marketing"
- I created 5 users with the following usernames
  - alice_m
  - bob_m
  - carol_m
  - david_m
  - emma_m
- Using the following commands
  - useradd -m alice_m
  - useradd -m bob_m
  - useradd -m carol_m
  - useradd -m david_m
  - useradd -m emma_m

 - Each of these users were assigned a password
 - All the five users were added to the marketing group by executing the folowing commands
   - usermod -aG marketing alice_m
   - usermod -aG marketing bob_m
   - usermod -aG marketing carol_m
   - usermod -aG marketing david_m
   - usermod -aG marketing emma_m
 - I created a folder called  "shared/marketing" in my home directory using the command "mkdir -p /home/shared/marketing"
 - For each user, i created a personal file 
    - touch /home/shared/marketing/alice_report.txt
    - touch /home/shared/marketing/bob_report.txt
    - touch /home/shared/marketing/carol_report.txt
    - touch /home/shared/marketing/david_report.txt
    - touch /home/shared/marketing/emma_report.txt
  - Each user the owner of the corresponding file by executing the following commands
     -  chown alice_m /home/shared/marketing/alice_report.txt
     -  chown bob_m /home/shared/marketing/bob_report.txt
     -  chown carol_m /home/shared/marketing/carol_report.txt
     -  chown david_m /home/shared/marketing/david_report.txt
     -  chown emma_m /home/shared/marketing/emma_report.txt
  - I had to set permissions to {700}: whereby
    - Each user has read, write, and execute (rwx) permissions on their own file
    - The group has no permissions (---) on the file
    - Others have no permissions (---) on the file
  - This was done by executing the following commands
     - chmod 700 /home/shared/marketing/alice_report.txt
     - chmod 700 /home/shared/marketing/bob_report.txt
     - chmod 700 /home/shared/marketing/carol_report.txt
     - chmod 700 /home/shared/marketing/david_report.txt
     - chmod 700 /home/shared/marketing/emma_report.txt
  - The expected permission output was
    ##    -rwx-----  

# 🔹 PART 2: IT Department (Shared Access)

### Tasks Performed

-Created itdept group
- Created 5 IT users
- Added users to group
- Created shared project file
- Assigned group ownership
- Applied 770 permissions 

## Key Observations/ Lesson Learned

- 700 allows access only to the file owner.
- 770 allows access to both owner and group members.
- Group-based access control simplifies enterprise management.
- Proper permission management reduces unauthorized access risks.
- Linux enforces access control using owner, group, and others model.



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

Expected Permission Output

-rwx-----
