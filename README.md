# Aruba DHCP Exclusion Generator 🧮

This is a lightweight browser-based tool for generating **Aruba-style DHCP exclusion statements**, based on your specified subnet and DHCP pool.

## 🔧 What It Does

Given:
- A network in CIDR notation (e.g. `172.17.128.0/20`)
- A DHCP range defined either by:
  - Start IP + End IP, or
  - Start IP + Number of Hosts

➡️ The tool will generate all **`ip dhcp excluded-address`** statements needed for Aruba configurations — excluding all addresses **outside** of your DHCP pool.

It follows Aruba's syntax, including wrapping each exclusion in `!` blocks:

```shell
!
ip dhcp excluded-address 172.17.128.0 172.17.128.9
!
ip dhcp excluded-address 172.17.130.0 172.17.143.255
!
