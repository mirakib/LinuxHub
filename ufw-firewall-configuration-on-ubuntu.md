## UFW (Uncomplicated Firewall) Quick Reference Guide

###  Installation and Initial Setup
These commands cover installing UFW and setting up its core behavior.

1. Install UFW
   
   ```sudo apt-get install ufw```
3. Check Current Status
   
   ```sudo ufw status```
5. Enable/Disable IPv6
   
   ```sudo nano /etc/default/ufw```
6. Set Default Policy
   
   ```sudo ufw default deny incoming``` [ Blocks all incoming traffic that is not explicitly allowed (secure default). ]
   ```sudo ufw default allow outgoing``` [ Allows all outgoing traffic (standard for clients/servers). ]


###  Managing Firewall Rules
These commands are used to explicitly allow, block, or delete specific traffic rules.

1. Allow by Port (Common)

```sudo ufw allow 80/tcp```

2. Allow Port Range

```sudo ufw allow 6000:6007/tcp```

3. Allow Specific IP & Port

```sudo ufw allow proto tcp from 116.212.111.186 to any port 5987```

4. Allow Multiple Ports

```sudo ufw allow proto tcp from any to any port 80,443``` [ Allows both HTTP and HTTPS traffic from any source IP. ]



###  Blocking/Denying Traffic

1. Deny Specific IP

   ```sudo ufw deny from 203.5.1.43```

2. Deny Subnet

   ```sudo ufw deny from 103.13.42.13/29```

3. Deny Specific Port & IP

   ```sudo ufw deny from 1.1.1.2 to any port 22 proto tcp```  [ Blocks SSH attempts only from IP address 1.1.1.2. ]


###  Deleting Rules

1. Delete All Rules

   ```sudo ufw reset```
   
3. Delete rule by number
   
   ```sudo ufw delete 4``` [ Deletes the rule that corresponds to the displayed number (e.g., deletes rule number 4) ]


### Activating and Resetting UFW

1. Enable UFW
   
   ```sudo ufw enable```
   
4. Disable UFW

   ```sudo ufw disable```
   
6. Reload Rules

   ```sudo ufw reload```
   
8. Verify Status

   ```sudo ufw status```

### Checking Logs

1. Views the log file page-by-page.

   ```sudo more /var/log/ufw.log```
   
3. Streams live log entries to your terminal, useful when testing new rules.

   ```sudo tail -f /var/log/ufw.log```
	
