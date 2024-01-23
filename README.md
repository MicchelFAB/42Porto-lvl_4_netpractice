
<p align="center">
    <img src="https://github.com/ayogun/42-project-badges/blob/main/badges/netpracticem.png" alt="netpractice">
</p>

# Guide to NetPractice

## Overview
NetPractice is a specialized project designed to enhance your understanding of subnetting. Whether you're a beginner or an experienced network enthusiast, this guide will provide insights into the world of subnetting and how NetPractice can be a valuable resource.

## What is IP Address?
In networking, an **IP address** (Internet Protocol address) is a numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication. It serves two primary purposes: identifying the host or network interface and providing the location of the host in the network.

## IPv4 (Internet Protocol version 4)
IPv4 is the fourth version of the Internet Protocol and is the most widely used version to date. IPv4 addresses are 32-bit numerical labels written in a dotted-decimal format (e.g., 192.168.1.1). An IPv4 address is divided into four segments, each represented by a decimal number ranging from 0 to 255.

The binary representation of an IPv4 address comprises 32 bits, organized into four 8-bit segments, commonly referred to as octets. For instance, take the IPv4 address 192.168.1.27 and convert to binary:

<table>
  <thead>
    <tr>
      <th colspan="8">"192 = 128 + 64"</th>
      <th colspan="8">168 (= 128 + 32 + 8)</th>
      <th colspan="8">1 (= 1)</th>
      <th colspan="8">27 (= 16 + 8 + 2 + 1)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>128<br></td> <td>64</td> <td>32</td> <td>16</td> <td>8</td> <td>4</td> <td>2</td> <td>1</td>
      <td>128</td> <td>64</td> <td>32</td> <td>16</td> <td>8</td> <td>4</td> <td>2</td> <td>1</td>
      <td>128</td> <td>64</td> <td>32</td> <td>16</td> <td>8</td> <td>4</td> <td>2</td> <td>1</td>
      <td>128</td> <td>64</td> <td>32</td> <td>16</td> <td>8</td> <td>4</td> <td>2</td> <td>1</td>
   </tr>
    <tr>
      <td>1</td> <td>1</td> <td>0</td> <td>0</td> <td>0</td> <td>0</td> <td>0</td> <td>0</td>
      <td>1</td> <td>0</td> <td>1</td> <td>0</td> <td>1</td> <td>0</td> <td>0</td> <td>0</td>
      <td>0</td> <td>0</td> <td>0</td> <td>0</td> <td>0</td> <td>0</td> <td>0</td> <td>1</td>
      <td>0</td> <td>0</td> <td>0</td> <td>1</td><td>1</td> <td>0</td> <td>1</td> <td>1</td>
    </tr>
  </tbody>
</table>

This way 192.168.1.27 translates to the binary sequence 11000000.10101000.00000001.00011011. In this binary format, each octet spans from 0 (binary: 00000000) to the maximum value of 255 (binary: 11111111).

This segmentation allows for a flexible and easily interpretable representation of IP addresses, where each octet represents a distinct portion of the address, contributing to the unique identification of devices on a network.

## Net Masks:
A **net mask** (network mask) is a 32-bit number that serves as a fundamental component of IP addressing. It divides an IP address into network and host portions. The net mask uses binary values to distinguish between the network and host bits. 

Understanding net masks is crucial for subnetting, a process that involves dividing a larger network into smaller, more manageable sub-networks.

### Example:

Consider an IP address and its associated net mask:

- **IP Address:** 192.168.1.100
- **Net Mask:** 255.255.255.0 (or in CIDR notation, /24)

#### Binary Representation:

1. **IP Address in Binary:**
11000000.10101000.00000001.01100100

2. **Net Mask in Binary:**
11111111.11111111.11111111.00000000

#### Division into Network and Host Portions:

- The net mask determines which bits in the IP address belong to the network portion and which bits belong to the host portion.

- In this example, the first 24 bits are designated for the network portion (determined by the net mask), and the remaining 8 bits are for the host portion.

#### Result:

- **Network Portion (in Binary):**
11000000.10101000.00000001

- **Host Portion (in Binary):**
01100100

- **Decimal Representation:**
  - Network Portion: 192.168.1
  - Host Portion: 100

In summary, the net mask of 255.255.255.0 (or /24 in CIDR notation) divides the IP address 192.168.1.100 into a network portion (192.168.1) and a host portion (100). This allows for efficient subnetting and organization of IP addresses within a larger network. Understanding this division is crucial for configuring networks, managing address spaces, and implementing subnetting strategies.

### Table Reference:

The following table lists the variable length subnets from 1 to 32, the CIDR [3] representation form (/xx) and the Decimal equivalents. (M = Million, K=Thousand, A,B,C= traditional class values)

|   Mask value:   |           # of    |                   |            | 
|-----------------|-------------------|-------------------|------------|
|   CIDR          |   Decimal         |  addresses       |  Classfull  |
|   /1            |    128.0.0.0      |   2048 M          |   128 A    |
|   /2            |    192.0.0.0      |   1024 M          |    64 A    |
|   /3            |    224.0.0.0      |    512 M          |    32 A    |
|   /4            |    240.0.0.0      |    256 M          |    16 A    |
|   /5            |    248.0.0.0      |    128 M          |     8 A    |
|   /6            |    252.0.0.0      |     64 M          |     4 A    |
|   /7            |    254.0.0.0      |     32 M          |     2 A    |
|   /8            |    255.0.0.0      |     16 M          |     1 A    |
|   /9            |    255.128.0.0    |      8 M          |   128 B    |
|   /10           |    255.192.0.0    |      4 M          |    64 B    |
|   /11           |    255.224.0.0    |      2 M          |    32 B    |
|   /12           |    255.240.0.0    |   1024 K          |    16 B    |
|   /13           |    255.248.0.0    |    512 K          |     8 B    |
|   /14           |    255.252.0.0    |    256 K          |     4 B    |
|   /15           |    255.254.0.0    |    128 K          |     2 B    |
|   /16           |    255.255.0.0    |     64 K          |     1 B    |
|   /17           |    255.255.128.0  |     32 K          |   128 C    |
|   /18           |    255.255.192.0  |     16 K          |    64 C    |
|   /19           |    255.255.224.0  |      8 K          |    32 C    |
|   /20           |    255.255.240.0  |      4 K          |    16 C    |
|   /21           |    255.255.248.0  |      2 K          |     8 C    |
|   /22           |    255.255.252.0  |      1 K          |     4 C    |
|   /23           |    255.255.254.0  |    512            |     2 C    |
|   /24           |    255.255.255.0  |    256            |     1 C    |
|   /25           |    255.255.255.128|    128            |   1/2 C    |
|   /26           |    255.255.255.192|     64            |   1/4 C    |
|   /27           |    255.255.255.224|     32            |   1/8 C    |
|   /28           |    255.255.255.240|     16            |  1/16 C    |
|   /29           |    255.255.255.248|      8            |  1/32 C    |
|   /30           |    255.255.255.252|      4            |  1/64 C    |
|   /31           |    255.255.255.254|      2            | 1/128 C    |
|   /32           |    255.255.255.255|   This is a       | single host route |

## The Routing Table:
A **routing table** is a critical component in networking that guides the forwarding of network traffic. It consists of a set of rules, known as routes, which specify how data should be directed to its destination. Each entry in the routing table includes information about the destination and the next hop for that destination.

### Elements of the Routing Table:

#### 1. Destination:

- The **destination** field in the routing table specifies the network or IP address range in the format `xxx.xxx.xxx.xxx/xx`. This indicates the range of IP addresses to which the route applies.

#### 2. Next Hop:

- The **next hop** field in the routing table specifies the IP address of the next router or gateway to which the data should be sent to reach the specified destination. It is in the format `xxx.xxx.xxx.xxx`.

### Special Entries:

#### 1. Default Route (0.0.0.0/0):

- When you see a destination entry as `0.0.0.0/0` or simply `default`, it represents the **default route**. This is a catch-all route used when there is no specific match for the destination in the routing table. It directs traffic to the specified next hop, usually the default gateway, when no other more specific route is applicable.

#### 2. Reverse Route:

- In the context of reverse routes, the router's IP address is specified as the next hop for a destination IP. This is often seen in scenarios like setting up routes for responses or reverse traffic, ensuring that data can find its way back to the source.

### Example:

Assuming an entry in the routing table:

Destination: 192.168.1.0/24
Next Hop: 10.0.0.1

This entry indicates that traffic destined for the IP addresses in the range 192.168.1.0 to 192.168.1.255 should be forwarded to the next hop router with the IP address 10.0.0.1.

Understanding and managing the routing table is crucial for network administrators to ensure efficient data routing and connectivity within a network.

---
## My Solutions

<details>
  <summary><b>Level 1</b></summary>
 <br>
  <img src="https://github.com/MicchelFAB/42Porto-lvl_4_netpractice/blob/master/img/001.png?raw=true" alt="level1">  
  <br>
    </details>

<details>
  <summary><b>Level 2</b></summary>
 <br>
  <img src="https://github.com/MicchelFAB/42Porto-lvl_4_netpractice/blob/master/img/002.png?raw=true" alt="level2">  
  <br>
    </details>

<details>
  <summary><b>Level 3</b></summary>
 <br>
  <img src="https://github.com/MicchelFAB/42Porto-lvl_4_netpractice/blob/master/img/003.png?raw=true" alt="level3">  
  <br>
    </details>

<details>
  <summary><b>Level 4</b></summary>
 <br>
  <img src="https://github.com/MicchelFAB/42Porto-lvl_4_netpractice/blob/master/img/004.png?raw=true" alt="level4">  
  <br>
    </details>

<details>
  <summary><b>Level 5</b></summary>
 <br>
  <img src="https://github.com/MicchelFAB/42Porto-lvl_4_netpractice/blob/master/img/005.png?raw=true" alt="level5">  
  <br>
    </details>

<details>
  <summary><b>Level 6</b></summary>
 <br>
  <img src="https://github.com/MicchelFAB/42Porto-lvl_4_netpractice/blob/master/img/006.png?raw=true" alt="level6">  
  <br>
    </details>

<details>
  <summary><b>Level 7</b></summary>
 <br>
  <img src="https://github.com/MicchelFAB/42Porto-lvl_4_netpractice/blob/master/img/007.png?raw=true" alt="level7">  
  <br>
    </details>

<details>
  <summary><b>Level 8</b></summary>
 <br>
  <img src="https://github.com/MicchelFAB/42Porto-lvl_4_netpractice/blob/master/img/008.png?raw=true" alt="level8">  
  <br>
    </details>

<details>
  <summary><b>Level 9</b></summary>
 <br>
  <img src="https://github.com/MicchelFAB/42Porto-lvl_4_netpractice/blob/master/img/009.png?raw=true" alt="level9">  
  <br>
  </details>

<details>
  <summary><b>Level 10</b></summary>
 <br>
  <img src="https://github.com/MicchelFAB/42Porto-lvl_4_netpractice/blob/master/img/010.png?raw=true" alt="level10">  
  <br>
  </details>

## Useful Links
- [lpaube's Guide to NetPractice](https://github.com/lpaube/NetPractice)
- [You Suck at Subnetting](https://www.youtube.com/playlist?list=PLIhvC56v63IKrRHh3gvZZBAGvsvOhwrRF)
- [Subnet Mask Cheat Sheet](https://www.aelius.com/njh/subnet_sheet.html)
- [TCP/IP Model Explained](https://www.youtube.com/watch?v=OTwp3xtd4dg)