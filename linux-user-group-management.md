<div align="center">

# User Management in Linux

</div>

| Command | Description |
| :---|--- |
| `sudo adduser john` | Creates a new user with an interactive prompt. |
| `cat /etc/passwd` | Lists all user accounts on the system. |
| `sudo adduser --no-create-home username` | Creates a new user without a home directory. |
| `sudo usermod -c "New Full Name" username` | Changes a user's full name or comment. |
| `sudo usermod -l new_username old_username` | Changes the username. |
| `sudo usermod -d /new/home/directory username` | Changes the user's home directory. |
| `sudo usermod -aG sudo john` | Grants sudo privileges to a user. |
| `finger username` | Displays detailed user information. |
| `id username` | Displays a user's UID, GID, and group memberships. |
| `sudo passwd -l john` | Locks a user's account, preventing login. |
| `sudo passwd -u john` | Unlocks a user's account. |
| `sudo passwd username` | Changes a user's password. |
| `sudo deluser john` | Removes a user account. |
| `sudo deluser --remove-home user` | Removes a user account and their home directory. |
| `sudo chage -d 0 username` | Forces a user to change their password on the next login. |
| `sudo usermod --expiredate 2023-12-31 username` | Sets an expiration date for a user account. |
| `last username` | Checks a user's login history. |

<div align="center">

# Group Management in Linux

</div>

| Command | Description |
| :---|--- |
| `sudo addgroup group_name` | Creates a new group. |
| `cat /etc/group` | Lists all groups on the system. |
| `sudo adduser username group_name` | Adds a user to a group. |
| `sudo groupmod -n new_group_name old_group_name` | Changes the name of a group. |
| `sudo deluser username group_name` | Removes a user from a group. |
| `sudo gpasswd -d username group_name` | Removes a user from a group. |
| `getent group group_name` | Displays the members of a group. |
| `sudo delgroup group_name` | Removes a group. |
| `sudo usermod -aG group1,group2 username` | Changes a user's supplementary groups. |
| `sudo addgroup --gid 1001 new_group_name` | Assigns a specific GID when creating a new group. |
| `sudo groupmod --gid new_gid group_name` | Changes the GID of an existing group. |


<div align="center">

# sudo user management in Linux

</div>

| Command | Description |
| :---|--- |
| `sudo adduser john` | Creates a new user with an interactive prompt. |
| `sudo usermod -aG sudo john` | Grants sudo privileges. |
