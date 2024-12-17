# Task2
## Devices used in network

### *1. Ruter (Cisco 1941)*
- Quantity: 1
- Model: Cisco 1941
- IP address:
- GigabitEthernet 0/0: `168.90.0.1`
- GigabitEthernet 0/1: `210.3.14.1`
### 2. *Switch 1*
- **Costum Device Model: 2960 IOS15**
- Connected Devices:
- PC-1: *Devive model* - PC-PT
- PC-2: *Devive model* - PC-PT
- Laptop: *Devive model* - Laptop-PT
- Server-: *Server model* - Server-PT

### *2.1. Switch 2*
- Costum Device Model: 2960 IOS15
- Connected Devices:
- PC-2: *Devive model* - PC-PT
- Server-1: *Server model* - Server-PT
- Server-2: *Server model* - Server-PT
## 2. IP Adresess
| **Devices** | **IP Address** | **Switch** |
|------------------|---------------------|---------------------|
| **Router** | 168.90.0.1 (Gig0/0) | |
| **Router** | 210.3.14.1 (Gig0/1) | |
| **PC-1** | 168.90.0.3 | Switch 0  
| **PC-2** | 186.90.0.2 | Switch 0 |
| **Laptop** | 168.90.0.05 | Switch 0 |
| **Server** | 168.90.0.4 | Switch 0 |
| **PC-3** | 210.3.14.3 | Switch 1 |
| **Server-1** | 210.3.14.2 | Switch 1 |
| **Server-2** | 210.3.14.4 | Switch 1 |

# **New devices**
*Switch 0*
- **Connected Devices**:
- **PC-3**: *Devive model* - PC-PT
- **IP-address**: `168.90.0.6`

*Switch 1*
- **Connected Devices**:
- **PC-4**: *Devive model* - PC-PT
- **IP-address**: `210.3.14.5`

# **DHCP(Dynamic Host Configuration Protocol) commands**
DHCP (Dynamic Host Configuration Protocol) is a network protocol that
automatically assigns IP addresses to devices on a network.
-In my setup, I connected two switches to a router and configured DHCP for
the first and second switch.
## First switch
**ip dhcp pool MYPOOL1**- To start, I entered the router's configuration
mode and created a DHCP pool named **MYPOOL1**, which would be responsible
for assigning IP addresses to the devices connected to the first switch.
**network 168.90.0.0 255.255.0.0**- I defined the network range as
**168.90.0.0** with a subnet mask of **255.255.0.0**, so the router would
assign IP addresses within this range.
**default-router 168.90.0.1**- Next, I specified the default gateway as
**168.90.0.1**, which is the router's IP address, allowing the devices to
communicate outside their local network.
**dns-server 8.8.8.8**- I also set **8.8.8.8** as the DNS server, using
Google's public DNS for domain name resolution.
**exit** -After completing the configuration for **MYPOOL1**, I exited the
pool setup and returned to global configuration mode.

## Second switch
**ip dhcp pool MYPOOL2**- For the second switch, I started by entering the
router's configuration mode and created a DHCP pool named **MYPOOL2**,
which is responsible for assigning IP addresses to the devices connected
to the second switch.
**network 210.3.14.0 255.255.255.0**- I then defined the network range as
210.3.14.0 with a subnet mask of 255.255.255.0, devices on thos network
will recive IP addresses from 210.3.14.0.
**default-router 210.3.14.1**- I set the default gateway to 210.3.14.1,
which is the router's IP address in this network, enabling devices to
communicate outside their local network.
**dns-server 8.8.8.8**- Additionally, I configured 8.8.8.8 as the DNS
server, using Google's public DNS for domain name resolution.
**exit**- After completing the configuration for MYPOOL2, I exited the
DHCP pool setup and returned to global configuration mode.

