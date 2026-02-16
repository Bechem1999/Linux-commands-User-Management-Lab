## 🔹 PART 2: IT Department (Shared Access)

Tasks Performed
-Created itdept group
-Created 5 IT users
-Added users to group
-Created shared project file
-Assigned group ownership
-Applied 770 permissions

## Commands Executed

groupadd itdept
useradd -m frank_it
useradd -m grace_it
useradd -m henry_it
useradd -m iris_it
useradd -m jack_it

usermod -aG itdept frank_it
usermod -aG itdept grace_it
usermod -aG itdept henry_it
usermod -aG itdept iris_it
usermod -aG itdept jack_it

mkdir -p /home/shared/itdept
touch /home/shared/itdept/project_specs.txt
chown root:itdept /home/shared/itdept/project_specs.txt
chmod 770 /home/shared/itdept/project_specs.txt

### Expected Permission Output
-rwxrwx---
