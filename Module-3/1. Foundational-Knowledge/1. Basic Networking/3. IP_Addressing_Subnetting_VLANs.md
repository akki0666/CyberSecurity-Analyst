
# Deep Dive into IP Addressing, Subnetting, and VLANs

## IP Addressing

### 1. IP Address Types
- **Static IP Address**: A fixed IP address assigned to a device. It does not change over time and is often used for servers or devices requiring consistent access.
  
- **Dynamic IP Address**: An IP address assigned by a DHCP (Dynamic Host Configuration Protocol) server. It can change over time and is used for most consumer devices.

### 2. IP Address Structure
- **IPv4 Structure**:
  - Composed of 32 bits, divided into four octets (8 bits each). 
  - Each octet can range from 0 to 255.
  - Example: `192.168.1.1`
  
- **IPv6 Structure**:
  - Composed of 128 bits, typically represented in hexadecimal format.
  - Divided into eight groups of four hexadecimal digits.
  - Example: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`

### 3. Reserved IP Addresses
Certain ranges of IP addresses are reserved for specific uses:
- **Private IP Addresses (RFC 1918)**: Not routable on the internet.
  - Class A: `10.0.0.0` to `10.255.255.255`
  - Class B: `172.16.0.0` to `172.31.255.255`
  - Class C: `192.168.0.0` to `192.168.255.255`

- **Loopback Address**: `127.0.0.1` for testing and local communication.

- **Broadcast Address**: Used to communicate with all devices on a network. For example, in a subnet `192.168.1.0/24`, the broadcast address is `192.168.1.255`.

## Subnetting

### 1. Subnetting Concepts
- **Subnet Mask**: Defines the network and host portions of an IP address. It is also represented in dot-decimal notation (like IP addresses).
  - Example: A subnet mask of `255.255.255.0` means that the first three octets represent the network part, while the last octet represents the host part.

- **CIDR Notation**: A compact representation of an IP address and its associated network mask.
  - Example: `192.168.1.0/24` indicates that the first 24 bits are the network part, allowing for 256 addresses (0-255).

### 2. Calculating Subnets
To calculate subnets, you can use the following formula:
- **Number of Hosts per Subnet**: \(2^{(32 - n)} - 2\) (where \(n\) is the number of bits in the subnet mask). The `-2` accounts for the network and broadcast addresses.

**Example**:
For a subnet mask of `/26`:
- \(2^{(32 - 26)} - 2 = 2^6 - 2 = 64 - 2 = 62\) usable IP addresses.

### 3. Subnetting Example
- Given an IP address of `192.168.1.0/24`, you want to create four subnets.
  
1. Convert `/24` to binary: `11111111.11111111.11111111.00000000`.
2. To create four subnets, you need to borrow 2 bits from the host part (2² = 4).
3. New subnet mask: `/26` or `255.255.255.192`.
4. Subnets created:
   - `192.168.1.0/26` (Usable: 192.168.1.1 to 192.168.1.62, Broadcast: 192.168.1.63)
   - `192.168.1.64/26` (Usable: 192.168.1.65 to 192.168.1.126, Broadcast: 192.168.1.127)
   - `192.168.1.128/26` (Usable: 192.168.1.129 to 192.168.1.190, Broadcast: 192.168.1.191)
   - `192.168.1.192/26` (Usable: 192.168.1.193 to 192.168.1.254, Broadcast: 192.168.1.255)

## VLANs (Virtual Local Area Networks)

### 1. VLAN Types
- **Data VLAN**: Primarily used for user data traffic. 
- **Voice VLAN**: Dedicated to voice traffic, ensuring QoS (Quality of Service).
- **Management VLAN**: Used for managing network devices, separate from user data.
- **Native VLAN**: The VLAN associated with untagged traffic on a trunk port.

### 2. VLAN Configuration
- **VLAN Trunking Protocol (VTP)**: A Cisco proprietary protocol used to manage VLAN configurations across multiple switches.
- **Trunk Ports**: Ports configured to carry traffic from multiple VLANs. They use tagging to identify which frame belongs to which VLAN.
- **Access Ports**: Configured to carry traffic from only one VLAN, untagged.

### 3. VLAN Implementation Example
1. **Defining VLANs**:
   - VLAN 10: Sales
   - VLAN 20: Engineering
   - VLAN 30: HR

2. **Switch Configuration**:
   ```bash
   Switch(config)# vlan 10
   Switch(config-vlan)# name Sales
   Switch(config-vlan)# exit
   Switch(config)# vlan 20
   Switch(config-vlan)# name Engineering
   Switch(config-vlan)# exit
   Switch(config)# vlan 30
   Switch(config-vlan)# name HR
   Switch(config-vlan)# exit
   ```

3. **Assigning Ports**:
   - Assign ports to the respective VLANs.
   ```bash
   Switch(config)# interface FastEthernet0/1
   Switch(config-if)# switchport mode access
   Switch(config-if)# switchport access vlan 10
   Switch(config-if)# exit

   Switch(config)# interface FastEthernet0/2
   Switch(config-if)# switchport mode access
   Switch(config-if)# switchport access vlan 20
   Switch(config-if)# exit
   ```

## Summary of Key Concepts
- **IP Addressing** is foundational for device identification in a network, with both static and dynamic options.
- **Subnetting** optimizes network management by dividing networks into smaller, efficient segments, enhancing performance and security.
- **VLANs** provide logical segmentation of networks, facilitating efficient traffic management and isolation of different types of traffic.
