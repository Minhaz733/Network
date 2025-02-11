##BDCOM OLT Config process


##Loging Info
- **Default ip: 192.168.0.1/24**
- **User: admin**
- **Pass: admin**

## Create VLANs
- OLT>enable
- OLT#config
- OLT_config# vlan 100 (single vlna)
- OLT_config# vlan 100-500 (vlna range)

### Interface config
> For trunk mode
- OLT> enable
- OLT# config
- OLT_config# interface tg0/1 (interface name)
- OLT_config_tg0/1# no shutdown
- OLT_config_tg0/1# description Up-Link
- OLT_config_tg0/1# switchport mode trunk (For trunk port)
- OLT_config_tg0/1# switchport trunk vlan-allowed 1-1000 (allow vlan through trunk port by range)
- OLT_config_tg0/1# switchport trunk vlan-allowed add 2000 (add vlan to exixting vlan list)



> For trunk mode
- OLT> enable
- OLT# config
- OLT_config# interface tg0/1 (interface name)
- OLT_config_gpon0/1# no shutdown
- OLT_config_gpon0/1# description Down-Link
- OLT_config_gpon0/1# switchport mode trunk (For trunk port)
- OLT_config_gpon0/1# switchport pvid 1000 (assine port vlan)
- OLT_config_gpon0/1# switchport trunk vlan-allowed 1-1000 (allow vlan through trunk port by range)
- OLT_config_gpon0/1# switchport trunk vlan-allowed add 2000 (add vlan to exixting vlan list)
