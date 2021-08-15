# Metric

```
# HELP ifAdminStatus The desired state of the interface - 1.3.6.1.2.1.2.2.1.7
# HELP ifConnectorPresent This object has the value 'true(1)' if the interface sublayer has a physical connector and the value 'false(2)' otherwise. - 1.3.6.1.2.1.31.1.1.1.17
# HELP ifCounterDiscontinuityTime The value of sysUpTime on the most recent occasion at which any one or more of this interface's counters suffered a discontinuity - 1.3.6.1.2.1.31.1.1.1.19
# HELP ifHCInBroadcastPkts The number of packets, delivered by this sub-layer to a higher (sub-)layer, which were addressed to a broadcast address at this sub-layer - 1.3.6.1.2.1.31.1.1.1.9
# HELP ifHCInMulticastPkts The number of packets, delivered by this sub-layer to a higher (sub-)layer, which were addressed to a multicast address at this sub-layer - 1.3.6.1.2.1.31.1.1.1.8
# HELP ifHCInOctets The total number of octets received on the interface, including framing characters - 1.3.6.1.2.1.31.1.1.1.6
# HELP ifHCInUcastPkts The number of packets, delivered by this sub-layer to a higher (sub-)layer, which were not addressed to a multicast or broadcast address at this sub-layer - 1.3.6.1.2.1.31.1.1.1.7
# HELP ifHCOutBroadcastPkts The total number of packets that higher-level protocols requested be transmitted, and which were addressed to a broadcast address at this sub-layer, including those that were discarded or not sent - 1.3.6.1.2.1.31.1.1.1.13
# HELP ifHCOutMulticastPkts The total number of packets that higher-level protocols requested be transmitted, and which were addressed to a multicast address at this sub-layer, including those that were discarded or not sent - 1.3.6.1.2.1.31.1.1.1.12
# HELP ifHCOutOctets The total number of octets transmitted out of the interface, including framing characters - 1.3.6.1.2.1.31.1.1.1.10
# HELP ifHCOutUcastPkts The total number of packets that higher-level protocols requested be transmitted, and which were not addressed to a multicast or broadcast address at this sub-layer, including those that were discarded or not sent - 1.3.6.1.2.1.31.1.1.1.11
# HELP ifHighSpeed An estimate of the interface's current bandwidth in units of 1,000,000 bits per second - 1.3.6.1.2.1.31.1.1.1.15
# HELP ifInBroadcastPkts The number of packets, delivered by this sub-layer to a higher (sub-)layer, which were addressed to a broadcast address at this sub-layer - 1.3.6.1.2.1.31.1.1.1.3
# HELP ifInDiscards The number of inbound packets which were chosen to be discarded even though no errors had been detected to prevent their being deliverable to a higher-layer protocol - 1.3.6.1.2.1.2.2.1.13
# HELP ifInErrors For packet-oriented interfaces, the number of inbound packets that contained errors preventing them from being deliverable to a higher-layer protocol - 1.3.6.1.2.1.2.2.1.14
# HELP ifInMulticastPkts The number of packets, delivered by this sub-layer to a higher (sub-)layer, which were addressed to a multicast address at this sub-layer - 1.3.6.1.2.1.31.1.1.1.2
# HELP ifInOctets The total number of octets received on the interface, including framing characters - 1.3.6.1.2.1.2.2.1.10
# HELP ifInUcastPkts The number of packets, delivered by this sub-layer to a higher (sub-)layer, which were not addressed to a multicast or broadcast address at this sub-layer - 1.3.6.1.2.1.2.2.1.11
# HELP ifInUnknownProtos For packet-oriented interfaces, the number of packets received via the interface which were discarded because of an unknown or unsupported protocol - 1.3.6.1.2.1.2.2.1.15
# HELP ifIndex A unique value, greater than zero, for each interface - 1.3.6.1.2.1.2.2.1.1
# HELP ifLastChange The value of sysUpTime at the time the interface entered its current operational state - 1.3.6.1.2.1.2.2.1.9
# HELP ifLinkUpDownTrapEnable Indicates whether linkUp/linkDown traps should be generated for this interface - 1.3.6.1.2.1.31.1.1.1.14
# HELP ifMtu The size of the largest packet which can be sent/received on the interface, specified in octets - 1.3.6.1.2.1.2.2.1.4
# HELP ifNumber The number of network interfaces (regardless of their current state) present on this system. - 1.3.6.1.2.1.2.1
# HELP ifOperStatus The current operational state of the interface - 1.3.6.1.2.1.2.2.1.8
# HELP ifOutBroadcastPkts The total number of packets that higher-level protocols requested be transmitted, and which were addressed to a broadcast address at this sub-layer, including those that were discarded or not sent - 1.3.6.1.2.1.31.1.1.1.5
# HELP ifOutDiscards The number of outbound packets which were chosen to be discarded even though no errors had been detected to prevent their being transmitted - 1.3.6.1.2.1.2.2.1.19
# HELP ifOutErrors For packet-oriented interfaces, the number of outbound packets that could not be transmitted because of errors - 1.3.6.1.2.1.2.2.1.20
# HELP ifOutMulticastPkts The total number of packets that higher-level protocols requested be transmitted, and which were addressed to a multicast address at this sub-layer, including those that were discarded or not sent - 1.3.6.1.2.1.31.1.1.1.4
# HELP ifOutOctets The total number of octets transmitted out of the interface, including framing characters - 1.3.6.1.2.1.2.2.1.16
# HELP ifOutUcastPkts The total number of packets that higher-level protocols requested be transmitted, and which were not addressed to a multicast or broadcast address at this sub-layer, including those that were discarded or not sent - 1.3.6.1.2.1.2.2.1.17
# HELP ifPhysAddress The interface's address at its protocol sub-layer - 1.3.6.1.2.1.2.2.1.6
# HELP ifPromiscuousMode This object has a value of false(2) if this interface only accepts packets/frames that are addressed to this station - 1.3.6.1.2.1.31.1.1.1.16
# HELP ifSpeed An estimate of the interface's current bandwidth in bits per second - 1.3.6.1.2.1.2.2.1.5
# HELP ifType_info The type of interface - 1.3.6.1.2.1.2.2.1.3 (EnumAsInfo)
# HELP snmp_scrape_duration_seconds Total SNMP time scrape took (walk and processing).
# HELP snmp_scrape_pdus_returned PDUs returned from walk.
# HELP snmp_scrape_walk_duration_seconds Time SNMP walk/bulkwalk took.
# HELP sysUpTime The time (in hundredths of a second) since the network management portion of the system was last re-initialized. - 1.3.6.1.2.1.1.3
```







# TYPE ifAdminStatus gauge
# TYPE ifConnectorPresent gauge
# TYPE ifCounterDiscontinuityTime gauge
# TYPE ifHCInBroadcastPkts counter
# TYPE ifHCInMulticastPkts counter
# TYPE ifHCInOctets counter
# TYPE ifHCInUcastPkts counter
# TYPE ifHCOutBroadcastPkts counter
# TYPE ifHCOutMulticastPkts counter
# TYPE ifHCOutOctets counter
# TYPE ifHCOutUcastPkts counter
# TYPE ifHighSpeed gauge

# TYPE ifInDiscards counter
# TYPE ifOutDiscards counter

# TYPE ifInErrors counter
# TYPE ifOutErrors counter


# TYPE ifInUnknownProtos counter
# TYPE ifIndex gauge
# TYPE ifLastChange gauge
# TYPE ifLinkUpDownTrapEnable gauge
# TYPE ifMtu gauge
# TYPE ifNumber gauge
# TYPE ifOperStatus gauge




# TYPE ifPhysAddress gauge
# TYPE ifPromiscuousMode gauge

# TYPE ifType_info gauge

# TYPE sysUpTime gauge