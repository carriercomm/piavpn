# piavpn

Shell scripts for managing VPN connections of PIA (Private Internet Access) from the command line

### Description

The main script is `piavpn.sh`. It can be used in both interactive and command line mode.

### Prerequisites

Optional: `figlet' which you can install from your repo (`sudo apt-get install figlet`) and simply serves for a nicer output; still it is optional.

For the `nmcli` (network manager's command line interface) to be able to handle your PIA connections, you need to edit the corresponding PIA files under `/etc/NetworkManager/system-connections/`. For details on what to do to enable each region so it is managable with the `piavpn.sh` script, please read: https://askubuntu.com/questions/57339/connect-disconnect-from-vpn-from-the-command-line/57409#57409?newreg=21c40769970a48909e8fee3df7bb308f

### Command line mode

Accepts the following command line arguments (only one at a time):

 - `-l|--list`         lists the PIA regions activated for nmcli. For details on doing this, read [this thread](https://askubuntu.com/questions/57339/connect-disconnect-from-vpn-from-the-command-line/57409#57409?newreg=21c40769970a48909e8fee3df7bb308f)
 - `-g|--geolocation`        prints where PIA thinks your IP is located
 - `-s|--state`      prints your current PIA vpn endpoint
 - `-u|--up <region name>`   start vpn connection to <region name>. Valid `<region name>`'s are those returned running the `piavpn.sh` with the `-l` and should be typed between quotes e.g. `sudo ./piavpn.sh -u "PIA - Sweden"`
 - `-k|--kill`       terminates the currently active vpn connection (if one is active)

### Interactive mode

Just run `sudo ./piavpn.sh` and you will get basic information about the currently active vpn connection and a small menu to terminate a vpn connection or to start a new one.

# Other scripts

Independently you can use the other scripts to perform specific functions (script names are self explanatory).
