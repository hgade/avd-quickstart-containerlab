
# Validate State Report

**Table of Contents:**

- [Validate State Report](validate-state-report)
  - [Test Results Summary](#test-results-summary)
  - [Failed Test Results Summary](#failed-test-results-summary)
  - [All Test Results](#all-test-results)

## Test Results Summary

### Summary Totals

| Total Tests | Total Tests Passed | Total Tests Failed |
| ----------- | ------------------ | ------------------ |
| 188 | 144 | 44 |

### Summary Totals Devices Under Tests

| DUT | Total Tests | Tests Passed | Tests Failed | Categories Failed |
| --- | ----------- | ------------ | ------------ | ----------------- |
| leaf1 |  33 | 29 | 4 | NTP, Routing Table, Loopback0 Reachability |
| leaf2 |  19 | 3 | 16 | NTP, Interface State, IP Reachability, Routing Table, Loopback0 Reachability |
| leaf3 |  33 | 29 | 4 | NTP, Routing Table, Loopback0 Reachability |
| leaf4 |  33 | 29 | 4 | NTP, Routing Table, Loopback0 Reachability |
| spine1 |  35 | 27 | 8 | NTP, LLDP Topology, IP Reachability, BGP, Routing Table, Loopback0 Reachability |
| spine2 |  35 | 27 | 8 | NTP, LLDP Topology, IP Reachability, BGP, Routing Table, Loopback0 Reachability |

### Summary Totals Per Category

| Test Category | Total Tests | Tests Passed | Tests Failed |
| ------------- | ----------- | ------------ | ------------ |
| NTP |  6 | 0 | 6 |
| Interface State |  44 | 43 | 1 |
| LLDP Topology |  16 | 14 | 2 |
| IP Reachability |  16 | 12 | 4 |
| BGP |  34 | 30 | 4 |
| Routing Table |  48 | 30 | 18 |
| Loopback0 Reachability |  24 | 15 | 9 |

## Failed Test Results Summary

| Test ID | Node | Test Category | Test Description | Test | Test Result | Failure Reason |
| ------- | ---- | ------------- | ---------------- | ---- | ----------- | -------------- |
| 1 | leaf1 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 2 | leaf2 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 3 | leaf3 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 4 | leaf4 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 5 | spine1 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 6 | spine2 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 37 | leaf2 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | FAIL | The task includes an option with an undefined variable. The error was: 'dict object' has no attribute 'Vxlan1'
The error appears to be in '/home/avd/.ansible/collections/ansible_collections/arista/avd/roles/eos_validate_state/tasks/interface_state.yml': line 58, column 3, but may be elsewhere in the file depending on the exact syntax problem.
The offending line appears to be:

- name: Validate Vxlan interfaces state ^ here  |
| 60 | spine1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet2/1 - remote: leaf2_Ethernet49/1 | FAIL | leaf2 - Ethernet49/1 |
| 64 | spine2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet2/1 - remote: leaf2_Ethernet50/1 | FAIL | leaf2 - Ethernet50/1 |
| 69 | leaf2 | IP Reachability | ip reachability test p2p links | Source: leaf2_Ethernet49/1 - Destination: spine1_Ethernet2/1 | FAIL | 100% packet loss |
| 70 | leaf2 | IP Reachability | ip reachability test p2p links | Source: leaf2_Ethernet50/1 - Destination: spine2_Ethernet2/1 | FAIL | 100% packet loss |
| 76 | spine1 | IP Reachability | ip reachability test p2p links | Source: spine1_Ethernet2/1 - Destination: leaf2_Ethernet49/1 | FAIL | 100% packet loss |
| 80 | spine2 | IP Reachability | ip reachability test p2p links | Source: spine2_Ethernet2/1 - Destination: leaf2_Ethernet50/1 | FAIL | 100% packet loss |
| 96 | spine1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.65 | FAIL | Session state "Active" |
| 100 | spine2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.67 | FAIL | Session state "Active" |
| 110 | spine1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.130 | FAIL | Session state "Active" |
| 114 | spine2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.130 | FAIL | Session state "Active" |
| 118 | leaf1 | Routing Table | Remote VTEP address | 192.0.254.2 | FAIL | VTEP 192.0.254.2 is not in the routing table |
| 121 | leaf2 | Routing Table | Remote VTEP address | 192.0.254.1 | FAIL | VTEP 192.0.254.1 is not in the routing table |
| 122 | leaf2 | Routing Table | Remote VTEP address | 192.0.254.2 | FAIL | VTEP 192.0.254.2 is not in the routing table |
| 123 | leaf2 | Routing Table | Remote VTEP address | 192.0.254.3 | FAIL | VTEP 192.0.254.3 is not in the routing table |
| 124 | leaf2 | Routing Table | Remote VTEP address | 192.0.254.4 | FAIL | VTEP 192.0.254.4 is not in the routing table |
| 126 | leaf3 | Routing Table | Remote VTEP address | 192.0.254.2 | FAIL | VTEP 192.0.254.2 is not in the routing table |
| 130 | leaf4 | Routing Table | Remote VTEP address | 192.0.254.2 | FAIL | VTEP 192.0.254.2 is not in the routing table |
| 134 | spine1 | Routing Table | Remote VTEP address | 192.0.254.2 | FAIL | VTEP 192.0.254.2 is not in the routing table |
| 138 | spine2 | Routing Table | Remote VTEP address | 192.0.254.2 | FAIL | VTEP 192.0.254.2 is not in the routing table |
| 142 | leaf1 | Routing Table | Remote Lo0 address | 192.0.255.130 | FAIL | Lo0 192.0.255.130 is not in the routing table |
| 145 | leaf2 | Routing Table | Remote Lo0 address | 192.0.255.129 | FAIL | Lo0 192.0.255.129 is not in the routing table |
| 146 | leaf2 | Routing Table | Remote Lo0 address | 192.0.255.130 | FAIL | Lo0 192.0.255.130 is not in the routing table |
| 147 | leaf2 | Routing Table | Remote Lo0 address | 192.0.255.131 | FAIL | Lo0 192.0.255.131 is not in the routing table |
| 148 | leaf2 | Routing Table | Remote Lo0 address | 192.0.255.132 | FAIL | Lo0 192.0.255.132 is not in the routing table |
| 150 | leaf3 | Routing Table | Remote Lo0 address | 192.0.255.130 | FAIL | Lo0 192.0.255.130 is not in the routing table |
| 154 | leaf4 | Routing Table | Remote Lo0 address | 192.0.255.130 | FAIL | Lo0 192.0.255.130 is not in the routing table |
| 158 | spine1 | Routing Table | Remote Lo0 address | 192.0.255.130 | FAIL | Lo0 192.0.255.130 is not in the routing table |
| 162 | spine2 | Routing Table | Remote Lo0 address | 192.0.255.130 | FAIL | Lo0 192.0.255.130 is not in the routing table |
| 166 | leaf1 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf1 - 192.0.255.129 Destination: 192.0.255.130 | FAIL | 100% packet loss |
| 169 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.0.255.130 Destination: 192.0.255.129 | FAIL | 100% packet loss |
| 170 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.0.255.130 Destination: 192.0.255.130 | FAIL | 100% packet loss |
| 171 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.0.255.130 Destination: 192.0.255.131 | FAIL | 100% packet loss |
| 172 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.0.255.130 Destination: 192.0.255.132 | FAIL | 100% packet loss |
| 174 | leaf3 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf3 - 192.0.255.131 Destination: 192.0.255.130 | FAIL | 100% packet loss |
| 178 | leaf4 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf4 - 192.0.255.132 Destination: 192.0.255.130 | FAIL | 100% packet loss |
| 182 | spine1 | Loopback0 Reachability | Loopback0 Reachability | Source: spine1 - 192.0.255.1 Destination: 192.0.255.130 | FAIL | 100% packet loss |
| 186 | spine2 | Loopback0 Reachability | Loopback0 Reachability | Source: spine2 - 192.0.255.2 Destination: 192.0.255.130 | FAIL | 100% packet loss |

## All Test Results

| Test ID | Node | Test Category | Test Description | Test | Test Result | Failure Reason |
| ------- | ---- | ------------- | ---------------- | ---- | ----------- | -------------- |
| 1 | leaf1 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 2 | leaf2 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 3 | leaf3 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 4 | leaf4 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 5 | spine1 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 6 | spine2 | NTP | Synchronised with NTP server | NTP | FAIL | not synchronised to NTP server |
| 7 | leaf1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet49/1 - P2P_LINK_TO_SPINE1_Ethernet1/1 | PASS | - |
| 8 | leaf1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet50/1 - P2P_LINK_TO_SPINE2_Ethernet1/1 | PASS | - |
| 9 | leaf1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1/1 - host11_leaf1_Ethernet1/1 | PASS | - |
| 10 | leaf1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1/2 - host12_leaf1_Ethernet1/2 | PASS | - |
| 11 | leaf3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet49/1 - P2P_LINK_TO_SPINE1_Ethernet3/1 | PASS | - |
| 12 | leaf3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet50/1 - P2P_LINK_TO_SPINE2_Ethernet3/1 | PASS | - |
| 13 | leaf3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1/1 - host21_leaf3_Ethernet1/1 | PASS | - |
| 14 | leaf3 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1/2 - host22_leaf3_Ethernet1/2 | PASS | - |
| 15 | leaf4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet49/1 - P2P_LINK_TO_SPINE1_Ethernet4/1 | PASS | - |
| 16 | leaf4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet50/1 - P2P_LINK_TO_SPINE2_Ethernet4/1 | PASS | - |
| 17 | leaf4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1/1 - host21_leaf4_Ethernet1/1 | PASS | - |
| 18 | leaf4 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1/2 - host22_leaf4_Ethernet1/2 | PASS | - |
| 19 | spine1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1/1 - P2P_LINK_TO_LEAF1_Ethernet49/1 | PASS | - |
| 20 | spine1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2/1 - P2P_LINK_TO_LEAF2_Ethernet49/1 | PASS | - |
| 21 | spine1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3/1 - P2P_LINK_TO_LEAF3_Ethernet49/1 | PASS | - |
| 22 | spine1 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4/1 - P2P_LINK_TO_LEAF4_Ethernet49/1 | PASS | - |
| 23 | spine2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet1/1 - P2P_LINK_TO_LEAF1_Ethernet50/1 | PASS | - |
| 24 | spine2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet2/1 - P2P_LINK_TO_LEAF2_Ethernet50/1 | PASS | - |
| 25 | spine2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet3/1 - P2P_LINK_TO_LEAF3_Ethernet50/1 | PASS | - |
| 26 | spine2 | Interface State | Ethernet Interface Status & Line Protocol == "up" | Ethernet4/1 - P2P_LINK_TO_LEAF4_Ethernet50/1 | PASS | - |
| 27 | leaf1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel11 - host11_leaf1_to_host11 | PASS | - |
| 28 | leaf1 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel12 - host12_leaf3_to_host12 | PASS | - |
| 29 | leaf3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel11 - host21_leaf3_to_host21 | PASS | - |
| 30 | leaf3 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel12 - host22_leaf3_to_host22 | PASS | - |
| 31 | leaf4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel11 - host21_leaf3_to_host21 | PASS | - |
| 32 | leaf4 | Interface State | Port-Channel Interface Status & Line Protocol == "up" | Port-Channel12 - host22_leaf3_to_host22 | PASS | - |
| 33 | leaf1 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan100 - TENANT_A_BGP_TO_COMPUTE | PASS | - |
| 34 | leaf3 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan150 - TENANT_A_BGP_TO_COMPUTE | PASS | - |
| 35 | leaf4 | Interface State | Vlan Interface Status & Line Protocol == "up" | Vlan150 - TENANT_A_BGP_TO_COMPUTE | PASS | - |
| 36 | leaf1 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS | - |
| 37 | leaf2 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | FAIL | The task includes an option with an undefined variable. The error was: 'dict object' has no attribute 'Vxlan1'
The error appears to be in '/home/avd/.ansible/collections/ansible_collections/arista/avd/roles/eos_validate_state/tasks/interface_state.yml': line 58, column 3, but may be elsewhere in the file depending on the exact syntax problem.
The offending line appears to be:

- name: Validate Vxlan interfaces state ^ here  |
| 38 | leaf3 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS | - |
| 39 | leaf4 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS | - |
| 40 | leaf1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS | - |
| 41 | leaf1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS | - |
| 42 | leaf1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback100 - TEST_VRF_VTEP_DIAGNOSTICS | PASS | - |
| 43 | leaf3 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS | - |
| 44 | leaf3 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS | - |
| 45 | leaf3 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback100 - TEST_VRF_VTEP_DIAGNOSTICS | PASS | - |
| 46 | leaf4 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS | - |
| 47 | leaf4 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS | - |
| 48 | leaf4 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback100 - TEST_VRF_VTEP_DIAGNOSTICS | PASS | - |
| 49 | spine1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS | - |
| 50 | spine2 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS | - |
| 51 | leaf1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet49/1 - remote: spine1_Ethernet1/1 | PASS | - |
| 52 | leaf1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet50/1 - remote: spine2_Ethernet1/1 | PASS | - |
| 53 | leaf2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet49/1 - remote: spine1_Ethernet2/1 | PASS | - |
| 54 | leaf2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet50/1 - remote: spine2_Ethernet2/1 | PASS | - |
| 55 | leaf3 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet49/1 - remote: spine1_Ethernet3/1 | PASS | - |
| 56 | leaf3 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet50/1 - remote: spine2_Ethernet3/1 | PASS | - |
| 57 | leaf4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet49/1 - remote: spine1_Ethernet4/1 | PASS | - |
| 58 | leaf4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet50/1 - remote: spine2_Ethernet4/1 | PASS | - |
| 59 | spine1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet1/1 - remote: leaf1_Ethernet49/1 | PASS | - |
| 60 | spine1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet2/1 - remote: leaf2_Ethernet49/1 | FAIL | leaf2 - Ethernet49/1 |
| 61 | spine1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet3/1 - remote: leaf3_Ethernet49/1 | PASS | - |
| 62 | spine1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet4/1 - remote: leaf4_Ethernet49/1 | PASS | - |
| 63 | spine2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet1/1 - remote: leaf1_Ethernet50/1 | PASS | - |
| 64 | spine2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet2/1 - remote: leaf2_Ethernet50/1 | FAIL | leaf2 - Ethernet50/1 |
| 65 | spine2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet3/1 - remote: leaf3_Ethernet50/1 | PASS | - |
| 66 | spine2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet4/1 - remote: leaf4_Ethernet50/1 | PASS | - |
| 67 | leaf1 | IP Reachability | ip reachability test p2p links | Source: leaf1_Ethernet49/1 - Destination: spine1_Ethernet1/1 | PASS | - |
| 68 | leaf1 | IP Reachability | ip reachability test p2p links | Source: leaf1_Ethernet50/1 - Destination: spine2_Ethernet1/1 | PASS | - |
| 69 | leaf2 | IP Reachability | ip reachability test p2p links | Source: leaf2_Ethernet49/1 - Destination: spine1_Ethernet2/1 | FAIL | 100% packet loss |
| 70 | leaf2 | IP Reachability | ip reachability test p2p links | Source: leaf2_Ethernet50/1 - Destination: spine2_Ethernet2/1 | FAIL | 100% packet loss |
| 71 | leaf3 | IP Reachability | ip reachability test p2p links | Source: leaf3_Ethernet49/1 - Destination: spine1_Ethernet3/1 | PASS | - |
| 72 | leaf3 | IP Reachability | ip reachability test p2p links | Source: leaf3_Ethernet50/1 - Destination: spine2_Ethernet3/1 | PASS | - |
| 73 | leaf4 | IP Reachability | ip reachability test p2p links | Source: leaf4_Ethernet49/1 - Destination: spine1_Ethernet4/1 | PASS | - |
| 74 | leaf4 | IP Reachability | ip reachability test p2p links | Source: leaf4_Ethernet50/1 - Destination: spine2_Ethernet4/1 | PASS | - |
| 75 | spine1 | IP Reachability | ip reachability test p2p links | Source: spine1_Ethernet1/1 - Destination: leaf1_Ethernet49/1 | PASS | - |
| 76 | spine1 | IP Reachability | ip reachability test p2p links | Source: spine1_Ethernet2/1 - Destination: leaf2_Ethernet49/1 | FAIL | 100% packet loss |
| 77 | spine1 | IP Reachability | ip reachability test p2p links | Source: spine1_Ethernet3/1 - Destination: leaf3_Ethernet49/1 | PASS | - |
| 78 | spine1 | IP Reachability | ip reachability test p2p links | Source: spine1_Ethernet4/1 - Destination: leaf4_Ethernet49/1 | PASS | - |
| 79 | spine2 | IP Reachability | ip reachability test p2p links | Source: spine2_Ethernet1/1 - Destination: leaf1_Ethernet50/1 | PASS | - |
| 80 | spine2 | IP Reachability | ip reachability test p2p links | Source: spine2_Ethernet2/1 - Destination: leaf2_Ethernet50/1 | FAIL | 100% packet loss |
| 81 | spine2 | IP Reachability | ip reachability test p2p links | Source: spine2_Ethernet3/1 - Destination: leaf3_Ethernet50/1 | PASS | - |
| 82 | spine2 | IP Reachability | ip reachability test p2p links | Source: spine2_Ethernet4/1 - Destination: leaf4_Ethernet50/1 | PASS | - |
| 83 | leaf1 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 84 | leaf2 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 85 | leaf3 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 86 | leaf4 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 87 | spine1 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 88 | spine2 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 89 | leaf1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.0 | PASS | - |
| 90 | leaf1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.2 | PASS | - |
| 91 | leaf3 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.128 | PASS | - |
| 92 | leaf3 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.130 | PASS | - |
| 93 | leaf4 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.192 | PASS | - |
| 94 | leaf4 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.194 | PASS | - |
| 95 | spine1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.1 | PASS | - |
| 96 | spine1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.65 | FAIL | Session state "Active" |
| 97 | spine1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.129 | PASS | - |
| 98 | spine1 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.193 | PASS | - |
| 99 | spine2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.3 | PASS | - |
| 100 | spine2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.67 | FAIL | Session state "Active" |
| 101 | spine2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.131 | PASS | - |
| 102 | spine2 | BGP | ip bgp peer state established (ipv4) | bgp_neighbor: 172.31.255.195 | PASS | - |
| 103 | leaf1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.1 | PASS | - |
| 104 | leaf1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.2 | PASS | - |
| 105 | leaf3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.1 | PASS | - |
| 106 | leaf3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.2 | PASS | - |
| 107 | leaf4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.1 | PASS | - |
| 108 | leaf4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.2 | PASS | - |
| 109 | spine1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.129 | PASS | - |
| 110 | spine1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.130 | FAIL | Session state "Active" |
| 111 | spine1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.131 | PASS | - |
| 112 | spine1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.132 | PASS | - |
| 113 | spine2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.129 | PASS | - |
| 114 | spine2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.130 | FAIL | Session state "Active" |
| 115 | spine2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.131 | PASS | - |
| 116 | spine2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.0.255.132 | PASS | - |
| 117 | leaf1 | Routing Table | Remote VTEP address | 192.0.254.1 | PASS | - |
| 118 | leaf1 | Routing Table | Remote VTEP address | 192.0.254.2 | FAIL | VTEP 192.0.254.2 is not in the routing table |
| 119 | leaf1 | Routing Table | Remote VTEP address | 192.0.254.3 | PASS | - |
| 120 | leaf1 | Routing Table | Remote VTEP address | 192.0.254.4 | PASS | - |
| 121 | leaf2 | Routing Table | Remote VTEP address | 192.0.254.1 | FAIL | VTEP 192.0.254.1 is not in the routing table |
| 122 | leaf2 | Routing Table | Remote VTEP address | 192.0.254.2 | FAIL | VTEP 192.0.254.2 is not in the routing table |
| 123 | leaf2 | Routing Table | Remote VTEP address | 192.0.254.3 | FAIL | VTEP 192.0.254.3 is not in the routing table |
| 124 | leaf2 | Routing Table | Remote VTEP address | 192.0.254.4 | FAIL | VTEP 192.0.254.4 is not in the routing table |
| 125 | leaf3 | Routing Table | Remote VTEP address | 192.0.254.1 | PASS | - |
| 126 | leaf3 | Routing Table | Remote VTEP address | 192.0.254.2 | FAIL | VTEP 192.0.254.2 is not in the routing table |
| 127 | leaf3 | Routing Table | Remote VTEP address | 192.0.254.3 | PASS | - |
| 128 | leaf3 | Routing Table | Remote VTEP address | 192.0.254.4 | PASS | - |
| 129 | leaf4 | Routing Table | Remote VTEP address | 192.0.254.1 | PASS | - |
| 130 | leaf4 | Routing Table | Remote VTEP address | 192.0.254.2 | FAIL | VTEP 192.0.254.2 is not in the routing table |
| 131 | leaf4 | Routing Table | Remote VTEP address | 192.0.254.3 | PASS | - |
| 132 | leaf4 | Routing Table | Remote VTEP address | 192.0.254.4 | PASS | - |
| 133 | spine1 | Routing Table | Remote VTEP address | 192.0.254.1 | PASS | - |
| 134 | spine1 | Routing Table | Remote VTEP address | 192.0.254.2 | FAIL | VTEP 192.0.254.2 is not in the routing table |
| 135 | spine1 | Routing Table | Remote VTEP address | 192.0.254.3 | PASS | - |
| 136 | spine1 | Routing Table | Remote VTEP address | 192.0.254.4 | PASS | - |
| 137 | spine2 | Routing Table | Remote VTEP address | 192.0.254.1 | PASS | - |
| 138 | spine2 | Routing Table | Remote VTEP address | 192.0.254.2 | FAIL | VTEP 192.0.254.2 is not in the routing table |
| 139 | spine2 | Routing Table | Remote VTEP address | 192.0.254.3 | PASS | - |
| 140 | spine2 | Routing Table | Remote VTEP address | 192.0.254.4 | PASS | - |
| 141 | leaf1 | Routing Table | Remote Lo0 address | 192.0.255.129 | PASS | - |
| 142 | leaf1 | Routing Table | Remote Lo0 address | 192.0.255.130 | FAIL | Lo0 192.0.255.130 is not in the routing table |
| 143 | leaf1 | Routing Table | Remote Lo0 address | 192.0.255.131 | PASS | - |
| 144 | leaf1 | Routing Table | Remote Lo0 address | 192.0.255.132 | PASS | - |
| 145 | leaf2 | Routing Table | Remote Lo0 address | 192.0.255.129 | FAIL | Lo0 192.0.255.129 is not in the routing table |
| 146 | leaf2 | Routing Table | Remote Lo0 address | 192.0.255.130 | FAIL | Lo0 192.0.255.130 is not in the routing table |
| 147 | leaf2 | Routing Table | Remote Lo0 address | 192.0.255.131 | FAIL | Lo0 192.0.255.131 is not in the routing table |
| 148 | leaf2 | Routing Table | Remote Lo0 address | 192.0.255.132 | FAIL | Lo0 192.0.255.132 is not in the routing table |
| 149 | leaf3 | Routing Table | Remote Lo0 address | 192.0.255.129 | PASS | - |
| 150 | leaf3 | Routing Table | Remote Lo0 address | 192.0.255.130 | FAIL | Lo0 192.0.255.130 is not in the routing table |
| 151 | leaf3 | Routing Table | Remote Lo0 address | 192.0.255.131 | PASS | - |
| 152 | leaf3 | Routing Table | Remote Lo0 address | 192.0.255.132 | PASS | - |
| 153 | leaf4 | Routing Table | Remote Lo0 address | 192.0.255.129 | PASS | - |
| 154 | leaf4 | Routing Table | Remote Lo0 address | 192.0.255.130 | FAIL | Lo0 192.0.255.130 is not in the routing table |
| 155 | leaf4 | Routing Table | Remote Lo0 address | 192.0.255.131 | PASS | - |
| 156 | leaf4 | Routing Table | Remote Lo0 address | 192.0.255.132 | PASS | - |
| 157 | spine1 | Routing Table | Remote Lo0 address | 192.0.255.129 | PASS | - |
| 158 | spine1 | Routing Table | Remote Lo0 address | 192.0.255.130 | FAIL | Lo0 192.0.255.130 is not in the routing table |
| 159 | spine1 | Routing Table | Remote Lo0 address | 192.0.255.131 | PASS | - |
| 160 | spine1 | Routing Table | Remote Lo0 address | 192.0.255.132 | PASS | - |
| 161 | spine2 | Routing Table | Remote Lo0 address | 192.0.255.129 | PASS | - |
| 162 | spine2 | Routing Table | Remote Lo0 address | 192.0.255.130 | FAIL | Lo0 192.0.255.130 is not in the routing table |
| 163 | spine2 | Routing Table | Remote Lo0 address | 192.0.255.131 | PASS | - |
| 164 | spine2 | Routing Table | Remote Lo0 address | 192.0.255.132 | PASS | - |
| 165 | leaf1 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf1 - 192.0.255.129 Destination: 192.0.255.129 | PASS | - |
| 166 | leaf1 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf1 - 192.0.255.129 Destination: 192.0.255.130 | FAIL | 100% packet loss |
| 167 | leaf1 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf1 - 192.0.255.129 Destination: 192.0.255.131 | PASS | - |
| 168 | leaf1 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf1 - 192.0.255.129 Destination: 192.0.255.132 | PASS | - |
| 169 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.0.255.130 Destination: 192.0.255.129 | FAIL | 100% packet loss |
| 170 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.0.255.130 Destination: 192.0.255.130 | FAIL | 100% packet loss |
| 171 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.0.255.130 Destination: 192.0.255.131 | FAIL | 100% packet loss |
| 172 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.0.255.130 Destination: 192.0.255.132 | FAIL | 100% packet loss |
| 173 | leaf3 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf3 - 192.0.255.131 Destination: 192.0.255.129 | PASS | - |
| 174 | leaf3 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf3 - 192.0.255.131 Destination: 192.0.255.130 | FAIL | 100% packet loss |
| 175 | leaf3 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf3 - 192.0.255.131 Destination: 192.0.255.131 | PASS | - |
| 176 | leaf3 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf3 - 192.0.255.131 Destination: 192.0.255.132 | PASS | - |
| 177 | leaf4 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf4 - 192.0.255.132 Destination: 192.0.255.129 | PASS | - |
| 178 | leaf4 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf4 - 192.0.255.132 Destination: 192.0.255.130 | FAIL | 100% packet loss |
| 179 | leaf4 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf4 - 192.0.255.132 Destination: 192.0.255.131 | PASS | - |
| 180 | leaf4 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf4 - 192.0.255.132 Destination: 192.0.255.132 | PASS | - |
| 181 | spine1 | Loopback0 Reachability | Loopback0 Reachability | Source: spine1 - 192.0.255.1 Destination: 192.0.255.129 | PASS | - |
| 182 | spine1 | Loopback0 Reachability | Loopback0 Reachability | Source: spine1 - 192.0.255.1 Destination: 192.0.255.130 | FAIL | 100% packet loss |
| 183 | spine1 | Loopback0 Reachability | Loopback0 Reachability | Source: spine1 - 192.0.255.1 Destination: 192.0.255.131 | PASS | - |
| 184 | spine1 | Loopback0 Reachability | Loopback0 Reachability | Source: spine1 - 192.0.255.1 Destination: 192.0.255.132 | PASS | - |
| 185 | spine2 | Loopback0 Reachability | Loopback0 Reachability | Source: spine2 - 192.0.255.2 Destination: 192.0.255.129 | PASS | - |
| 186 | spine2 | Loopback0 Reachability | Loopback0 Reachability | Source: spine2 - 192.0.255.2 Destination: 192.0.255.130 | FAIL | 100% packet loss |
| 187 | spine2 | Loopback0 Reachability | Loopback0 Reachability | Source: spine2 - 192.0.255.2 Destination: 192.0.255.131 | PASS | - |
| 188 | spine2 | Loopback0 Reachability | Loopback0 Reachability | Source: spine2 - 192.0.255.2 Destination: 192.0.255.132 | PASS | - |
