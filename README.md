# sbfspot-config
Installation/Configuration tool for SBFspot on Raspberry Pi

### Run the tool
To install the latest SBFspot release:    
`curl -s https://raw.githubusercontent.com/sbfspot/sbfspot-config/master/sbfspot-config | sudo bash`

To install a specific SBFspot release (e.g. 3.5.0):    
`curl -s https://raw.githubusercontent.com/sbfspot/sbfspot-config/master/sbfspot-config | sudo bash -s 3.5.0`

At the time of writing, only one version (3.5.0) is available.    
This tool needs to run as root. Depending on the chosen options, it installs software packages and writes to locations where a locked down user can't write. If you're uncomfortable with this, either quit here or have a look at the script first.

### Navigation
sbfspot-config uses [whiptail](https://en.wikibooks.org/wiki/Bash_Shell_Scripting/Whiptail) for the dialog boxes. You might be already familiar with it by using raspi-config (Yes, I took a close look at this one)
Anyway, to navigate in the menus, these keys are important: [ENTER], [SPACEBAR], [TAB], [ESC] and [UP/DOWN ARROWS]
  
### Configure SBFspot
When you enter the above command, the latest version of sbfspot-config is downloaded and executed as root.
Below I explain the bare minimum steps to configure SBFspot:

![Launch](https://user-images.githubusercontent.com/1931158/46150028-e68ba200-c26b-11e8-950b-bb7de3053fc2.jpg)

When an older SBFspot.cfg is found, you can use this one to reconfigure.    
Remember: it's always a good idea to take a backup of an existing database (SBFspot.db in case of SQLite)

![0](https://user-images.githubusercontent.com/1931158/46150551-1ab39280-c26d-11e8-8f48-f5c4dc2834ca.JPG)

### Main menu
![0-main](https://user-images.githubusercontent.com/1931158/46151414-053f6800-c26f-11e8-8369-ce1c6a81a694.JPG)

Depending on the connection of your inverter, select "Connection Type => Bluetooth" or "Connection Type => Speedwire"

![2-connectiontype](https://user-images.githubusercontent.com/1931158/46155144-ea70f180-c276-11e8-88cc-a308500a7d6c.JPG)

### Bluetooth
Selecting Bluetooth launches `hcitool scan` to get the list of SMA devices. This takes some time to complete.

![2-bluetooth](https://user-images.githubusercontent.com/1931158/46155238-2310cb00-c277-11e8-88a2-e23d2ac0fb40.jpg)

### Speedwire
Enter 1 or more fixed IP addresses.

### Database
Select a database you want to use. If you don't have already MySQL or MariaDB server running, SQLite is your best option.
This howto doesn't cover MySQL/MariaDB server setup. If you don't need a database, you can select NoSQL.

![5-database](https://user-images.githubusercontent.com/1931158/46250413-a9c1d580-c43a-11e8-93b8-c334f825c2e2.JPG)

### PVoutput
This section requires a [PVoutput](https://pvoutput.org) account and an enabled API key.

![6-pvoutput_api](https://user-images.githubusercontent.com/1931158/46250420-c4944a00-c43a-11e8-8b56-2323cfc04ec5.JPG)

![6-pvoutput](https://user-images.githubusercontent.com/1931158/46250421-c958fe00-c43a-11e8-90a5-853167da58ef.JPG)

### Advanced Options
Feel free to explore the advanced options for bluetooth, csv output, ...

![7-advanced](https://user-images.githubusercontent.com/1931158/46250445-6451d800-c43b-11e8-9748-c2f56156d799.JPG)
