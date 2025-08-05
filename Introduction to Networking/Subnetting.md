# Subnetting Explained

## What is Subnetting?

Subnetting is the division of a larger IPv4 address range into smaller address ranges called **subnets**.

A **subnet** is a logical segment of a network where all IP addresses share the same network portion.  
Think of a subnet as a labeled entrance in a big building corridor that separates different departments.

---

## Key Components of a Subnet

When subnetting, you identify:

- **Network Address**: The first address in a subnet (all host bits are 0)
- **Broadcast Address**: The last address in a subnet (all host bits are 1)
- **First Host**: The first usable IP address in the subnet (network address + 1)
- **Last Host**: The last usable IP address in the subnet (broadcast address - 1)
- **Number of Hosts**: Total usable IP addresses in the subnet

---

## Example: IPv4 and Subnet Mask

- IPv4 Address: `192.168.12.160`  
- Subnet Mask: `255.255.255.192`  
- CIDR: `/26`

### Network vs Host Parts

- The **subnet mask** uses `1`s to mark the **network bits** (fixed part).
- The **host bits** are the remaining bits (changeable part).
- The network bits determine the main network and subnet.
- Host bits vary between the first address (network address) and the last address (broadcast address).

---

## Calculating Network & Broadcast Addresses

- **Network address**: Set all host bits to `0`.
- **Broadcast address**: Set all host bits to `1`.

For example, with `/26` (mask `255.255.255.192`), the host bits are the last 6 bits.

- Network Address: `192.168.12.128`  
- Broadcast Address: `192.168.12.191`

The usable host IP range: `192.168.12.129` to `192.168.12.190`  
Total usable hosts = 64 (addresses in subnet) - 2 (network & broadcast) = 62

---

## Dividing Subnets into Smaller Subnets

If you need to divide a subnet into smaller subnets:

- Use powers of two to calculate how many subnets you can create.  
  Example: 4 subnets = `2^2`, so you borrow 2 bits from the host part.

- Increase the subnet mask accordingly:  
  Original `/26` → New `/28` (since 26 + 2 = 28)

- Calculate new subnet size:  
  Original subnet had 64 addresses → divided by 4 → each new subnet has 16 addresses.

---

## Example: Dividing `192.168.12.128/26` into 4 Subnets (`/28`)

| Subnet | Network Address     | First Host         | Last Host          | Broadcast Address   | CIDR             |
|--------|---------------------|--------------------|--------------------|---------------------|------------------|
| 1      | 192.168.12.128      | 192.168.12.129     | 192.168.12.142     | 192.168.12.143      | 192.168.12.128/28 |
| 2      | 192.168.12.144      | 192.168.12.145     | 192.168.12.158     | 192.168.12.159      | 192.168.12.144/28 |
| 3      | 192.168.12.160      | 192.168.12.161     | 192.168.12.174     | 192.168.12.175      | 192.168.12.160/28 |
| 4      | 192.168.12.176      | 192.168.12.177     | 192.168.12.190     | 192.168.12.191      | 192.168.12.176/28 |

---

## Understanding the Increment of Network Addresses

- The **step size** between network addresses depends on the number of host bits:  
  \[
  \text{Step Size} = 2^{\text{number of host bits}}
  \]

- For `/28`, host bits = 32 - 28 = 4  
  Step size = `2^4 = 16`

- This means each subnet network address increases by 16.

---

## Mental Subnetting Tips

- Remember octet boundaries:  
  - `/8` changes 1st octet  
  - `/16` changes 2nd octet  
  - `/24` changes 3rd octet  
  - `/32` changes 4th octet

- Use **modulo operation** to calculate subnet sizes and ranges.  
  For example:  
  `25 % 8 = 1` → 1 bit into the 4th octet  
  Number of IPs = \( 2^{8 - 1} = 128 \)

- Powers of two help quickly calculate subnet sizes:

| Remainder | IP Count | Exponent | Division form |
|-----------|----------|----------|---------------|
| 0         | 256      | 2^8      | 256           |
| 1         | 128      | 2^7      | 256 / 2       |
| 2         | 64       | 2^6      | 256 / 2 / 2   |
| 3         | 32       | 2^5      | 256 / 2 / 2 / 2 |
| 4         | 16       | 2^4      | 256 / 2 / 2 / 2 / 2 |
| 5         | 8        | 2^3      | 256 / 2 / 2 / 2 / 2 / 2 |
| 6         | 4        | 2^2      | 256 / 2 / 2 / 2 / 2 / 2 / 2 |
| 7         | 2        | 2^1      | 256 / 2 / 2 / 2 / 2 / 2 / 2 / 2 |

---

## Summary

Subnetting breaks down IP networks into smaller, manageable blocks by:

- Defining network and host parts using subnet masks
- Calculating network, broadcast, and usable IP addresses
- Dividing networks by borrowing bits from the host portion
- Using powers of two to find subnet sizes and increments

---