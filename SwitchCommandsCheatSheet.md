# Cisco Switch Configuration Cheat Sheet

## Basic Setup and Navigation
```bash
# Enter privileged EXEC mode
enable
# Enter global configuration mode
configure terminal
# Exit current mode
exit
# Return to privileged EXEC mode
end
# Save configuration
copy running-config startup-config
# Show running configuration
show running-config
```

## Interface Configuration
```bash
# Enter interface configuration mode
interface [interface-type] [interface-number]
# Example: interface GigabitEthernet0/1

# Configure IP address
ip address [ip-address] [subnet-mask]

# Enable/disable interface
no shutdown
shutdown

# Set interface description
description [description-text]

# Set interface speed
speed [10|100|1000|auto]

# Set interface duplex mode
duplex [full|half|auto]
```

## VLAN Configuration
```bash
# Create VLAN
vlan [vlan-id]
name [vlan-name]

# Assign interface to VLAN
switchport mode access
switchport access vlan [vlan-id]

# Configure trunk port
switchport mode trunk
switchport trunk allowed vlan [vlan-list]
switchport trunk native vlan [vlan-id]
```

## Security Commands
```bash
# Set console password
line console 0
password [password]
login

# Set enable password
enable secret [password]

# Set SSH configuration
ip domain-name [domain-name]
crypto key generate rsa
username [username] secret [password]
line vty 0 15
transport input ssh
login local

# Configure port security
switchport port-security
switchport port-security maximum [max-addresses]
switchport port-security violation [protect|restrict|shutdown]
switchport port-security mac-address [mac-address]
```

## Useful Show Commands
```bash
# Show interface status
show interface status
show interface [interface-type] [interface-number]

# Show VLAN information
show vlan brief
show vlan id [vlan-id]

# Show MAC address table
show mac address-table

# Show running configuration
show running-config

# Show startup configuration
show startup-config

# Show version information
show version
```

## Troubleshooting Commands
```bash
# Clear interface counters
clear counters [interface-type] [interface-number]

# Test connectivity
ping [ip-address]

# Show interface statistics
show interface [interface-type] [interface-number] counters

# Show spanning-tree information
show spanning-tree
```

## Tips and Best Practices
1. Always save your configuration after making changes
2. Use descriptive interface descriptions
3. Document VLAN assignments
4. Implement proper security measures
5. Use SSH instead of Telnet for remote access
6. Regularly backup your configuration
7. Use consistent naming conventions
8. Test connectivity after configuration changes
9. Document all changes made to the switch
10. Keep firmware up to date

## Common Issues and Solutions
1. Interface not coming up: Check physical connection and verify no shutdown command
2. VLAN issues: Verify VLAN exists and port is in correct mode
3. SSH connection problems: Check crypto key generation and username/password
4. Port security violations: Verify MAC address configuration and violation mode
5. Configuration not saving: Ensure proper write memory command
