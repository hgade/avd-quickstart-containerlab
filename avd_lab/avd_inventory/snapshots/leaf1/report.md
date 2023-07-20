# leaf1 Commands Output

## Table of Contents

- [show lldp neighbors](#show-lldp-neighbors)
- [show ip interface brief](#show-ip-interface-brief)
- [show interfaces description](#show-interfaces-description)
- [show version](#show-version)
- [show running-config](#show-running-config)
- [show ip bgp summary](#show-ip-bgp-summary)
- [show bgp evpn summary](#show-bgp-evpn-summary)
## show bgp evpn summary

```
BGP is disabled for VRF default
```
## show interfaces description

```
Interface                      Status         Protocol           Description
Et1/1                          up             up                 
Et1/2                          up             up                 
Et1/3                          up             up                 
Et49/1                         up             up                 
Et50/1                         up             up                 
Ma0                            up             up
```
## show ip bgp summary

```
BGP is disabled for VRF default
```
## show ip interface brief

```
Address 
Interface       IP Address            Status     Protocol        MTU    Owner   
--------------- --------------------- ---------- ------------ --------- ------- 
Management0     192.168.123.21/24     up         up             1500
```
## show lldp neighbors

```
Last table change time   : 1:34:06 ago
Number of table inserts  : 16
Number of table deletes  : 1
Number of table drops    : 0
Number of table age-outs : 1

Port            Neighbor Device ID       Neighbor Port ID    TTL 
------------ ------------------------ ---------------------- --- 
Et1/1           host11                   Ethernet1           120 
Et1/2           host12                   Ethernet1           120 
Et1/3           host12                   Ethernet2           120 
Et49/1          spine1                   Ethernet1/1         120 
Et50/1          spine2                   Ethernet1/1         120 
Ma0             leaf4                    Management0         120 
Ma0             host11                   Management0         120 
Ma0             host22                   Management0         120 
Ma0             leaf2                    Management0         120 
Ma0             host12                   Management0         120 
Ma0             spine1                   Management0         120 
Ma0             spine2                   Management0         120 
Ma0             leaf3                    Management0         120 
Ma0             host21                   Management0         120 
Ma0             leaf1                    Management0         120
```
## show running-config

```
! Command: show running-config
! device: leaf1 (cEOSLab, EOS-4.25.5M-23663200.4255M (engineering build))
!
no aaa root
!
username cvpadmin privilege 15 role network-admin secret sha512 $6$rdcayNdN3.MCfcyO$bvRfH/h.vs6f.xFTJCBRW043/d..sKK5py2IFNiRtxAB/tMnt7kjUSsXN42MsyplWbjN6xnnFsKNNZBWD8inq1
!
daemon TerminAttr
   exec /usr/bin/TerminAttr -cvaddr=192.168.122.241:9910 -cvauth=key, -cvvrf=MGMT -smashexcludes=ale,flexCounter,hardware,kni,pulse,strata -ingestexclude=/Sysdb/cell/1/agent,/Sysdb/cell/2/agent -taillogs
   no shutdown
!
transceiver qsfp default-mode 4x10G
!
service routing protocols model multi-agent
!
hostname leaf1
!
spanning-tree mode mstp
!
vrf instance MGMT
!
interface Ethernet1/1
!
interface Ethernet1/2
!
interface Ethernet1/3
!
interface Ethernet49/1
!
interface Ethernet50/1
!
interface Management0
   vrf MGMT
   ip address 192.168.123.21/24
!
no ip routing
no ip routing vrf MGMT
!
ip route vrf MGMT 0.0.0.0/0 192.168.123.1
!
management api http-commands
   no shutdown
   !
   vrf MGMT
      no shutdown
!
end
```
## show version

```
cEOSLab
Hardware version: 
Serial number: 
Hardware MAC address: 001c.7366.bde3
System MAC address: 001c.7366.bde3

Software image version: 4.25.5M-23663200.4255M (engineering build)
Architecture: x86_64
Internal build version: 4.25.5M-23663200.4255M
Internal build ID: 050de75d-5a9e-4240-bae1-bf6e2e4a64e4

cEOS tools version: 1.1
Kernel version: 5.10.104-linuxkit

Uptime: 0 weeks, 0 days, 2 hours and 37 minutes
Total memory: 17403044 kB
Free memory: 2791056 kB
```
