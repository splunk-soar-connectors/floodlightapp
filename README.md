[comment]: # "Auto-generated SOAR connector documentation"
# Floodlight SDN

Publisher: SPAWAR Systems Center Atlantic  
Connector Version: 0\.0\.4  
Product Vendor: Floodlight  
Product Name: Floodlight  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 1\.1\.72  

Implements command and control for the Floodlight SDN controller


This application may be used to control [Floodlight](http://www.projectfloodlight.org/floodlight/)
Software Defined Networking controllers.


### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Floodlight asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**url** |  required  | string | URL of the Floodlight controller

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity\.  
[block ip](#action-block-ip) - Block traffic to/from the matching IP\.  
[unblock ip](#action-unblock-ip) - Unblocks traffic to/from the matching IP  
[block mac address](#action-block-mac-address) - Block traffic to/from the matching MAC  
[unblock mac address](#action-unblock-mac-address) - Unblocks traffic to/from the matching MAC\.  
[block subnet](#action-block-subnet) - Block traffic to/from the matching IP subnet\.  
[unblock subnet](#action-unblock-subnet) - Unblocks traffic to/from the matching IP subnet\.  
[block arp](#action-block-arp) - Block ARP packets sourced from this MAC\.  
[unblock arp](#action-unblock-arp) - Unblock ARP packets sourced from this MAC\.  
[block flow](#action-block-flow) - Block network traffic matching flow parameters\.  
[unblock flow](#action-unblock-flow) - Unblock network traffic matching flow parameters\.  
[get firewall status](#action-get-firewall-status) - Get the enable/disable state of the firewall\.  
[enable firewall](#action-enable-firewall) - Enable the firewall\.  
[disable firewall](#action-disable-firewall) - Disable the firewall\.  
[delete firewall rule](#action-delete-firewall-rule) - Delete a firewall rule\.  
[list firewall rules](#action-list-firewall-rules) - List firewall rules stored in the controller\.  
[list switches](#action-list-switches) - List SDN switches managed by the controller\.  
[list internal links](#action-list-internal-links) - List single\-hop links discovered via LLDP\.  
[list external links](#action-list-external-links) - List multi\-hop links discovered via BDDP\.  
[list devices](#action-list-devices) - List devices tracked by the SDN controller\.  
[get uptime](#action-get-uptime) - Get time since SDN controller startup\.  
[list static flows](#action-list-static-flows) - List static flow rules\.  
[add static flow](#action-add-static-flow) - Add a static flow rule\.  
[delete static flow](#action-delete-static-flow) - Remove a static flow rule\.  
[clear static flows](#action-clear-static-flows) - Remove all static flow rules\.  

## action: 'test connectivity'
Validate the asset configuration for connectivity\.

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'block ip'
Block traffic to/from the matching IP\.

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip\_macaddress** |  required  | IP address to block | string |  `ip` 
**priority** |  optional  | priority of this firewall rule | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.activityid | string |  `activityid` 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.parameter\.priority | string | 
action\_result\.parameter\.src\-mac | string |  `mac address` 
action\_result\.parameter\.dst\-mac | string |  `mac address` 
action\_result\.parameter\.src\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.dst\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.dl\-type | string |   

## action: 'unblock ip'
Unblocks traffic to/from the matching IP

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip\_macaddress** |  required  | IP address to unblock | string |  `ip` 
**priority** |  optional  | priority of this firewall rule | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.activityid | string |  `activityid` 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.parameter\.priority | string | 
action\_result\.parameter\.src\-mac | string |  `mac address` 
action\_result\.parameter\.dst\-mac | string |  `mac address` 
action\_result\.parameter\.src\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.dst\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.dl\-type | string |   

## action: 'block mac address'
Block traffic to/from the matching MAC

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip\_macaddress** |  required  | MAC address to block | string |  `mac address` 
**priority** |  optional  | priority of this firewall rule | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.activityid | string |  `activityid` 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.parameter\.priority | string | 
action\_result\.parameter\.src\-mac | string |  `mac address` 
action\_result\.parameter\.dst\-mac | string |  `mac address` 
action\_result\.parameter\.src\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.dst\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.dl\-type | string |   

## action: 'unblock mac address'
Unblocks traffic to/from the matching MAC\.

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip\_macaddress** |  required  | MAC to unblock | string |  `mac address` 
**priority** |  optional  | priority of this firewall rule | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.activityid | string |  `activityid` 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.parameter\.priority | string | 
action\_result\.parameter\.src\-mac | string |  `mac address` 
action\_result\.parameter\.dst\-mac | string |  `mac address` 
action\_result\.parameter\.src\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.dst\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.dl\-type | string |   

## action: 'block subnet'
Block traffic to/from the matching IP subnet\.

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip\_macaddress** |  required  | CIDR prefix and netmask to block | string |  `cidr` 
**priority** |  optional  | priority of this firewall rule | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.activityid | string |  `activityid` 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.parameter\.priority | string | 
action\_result\.parameter\.src\-mac | string |  `mac address` 
action\_result\.parameter\.dst\-mac | string |  `mac address` 
action\_result\.parameter\.src\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.dst\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.dl\-type | string |   

## action: 'unblock subnet'
Unblocks traffic to/from the matching IP subnet\.

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip\_macaddress** |  required  | CIDR prefix and net mask to unblock | string |  `cidr` 
**priority** |  optional  | priority of this firewall rule | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.activityid | string |  `activityid` 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.parameter\.priority | string | 
action\_result\.parameter\.src\-mac | string |  `mac address` 
action\_result\.parameter\.dst\-mac | string |  `mac address` 
action\_result\.parameter\.src\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.dst\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.dl\-type | string |   

## action: 'block arp'
Block ARP packets sourced from this MAC\.

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**macaddress** |  required  | MAC address of device to block | string |  `mac address` 
**priority** |  optional  | priority of this firewall rule | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.activityid | string |  `activityid` 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.parameter\.priority | numeric | 
action\_result\.parameter\.src\-mac | string |  `mac address` 
action\_result\.parameter\.dl\-type | string |   

## action: 'unblock arp'
Unblock ARP packets sourced from this MAC\.

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**macaddress** |  required  | MAC address of device to unblock | string |  `mac address` 
**priority** |  optional  | priority of this firewall rule | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.activityid | string |  `activityid` 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.parameter\.priority | numeric | 
action\_result\.parameter\.src\-mac | string |  `mac address` 
action\_result\.parameter\.dl\-type | string |   

## action: 'block flow'
Block network traffic matching flow parameters\.

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**src\-mac** |  optional  | source mac address | string |  `mac address` 
**dst\-mac** |  optional  | destination mac address | string |  `mac address` 
**dl\-type** |  optional  | layer\-3 protocol \(IPv4 or ARP\) | string | 
**src\-ip** |  optional  | source ip address or cidr | string |  `ip`  `cidr` 
**dst\-ip** |  optional  | destination ip address or cidr | string |  `ip`  `cidr` 
**nw\-proto** |  optional  | layer\-4 protocol \(TCP, UDP, or ICMP\) | string | 
**tp\-src** |  optional  | layer\-4 source port number | numeric | 
**tp\-dst** |  optional  | layer\-4 destination port number | numeric | 
**switchid** |  optional  | datapath identifier | string |  `dpid` 
**src\-inport** |  optional  | input port | string | 
**priority** |  optional  | priority for this rule | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.data\.\*\.activityid | string |  `activityid` 
action\_result\.parameter\.priority | string | 
action\_result\.parameter\.src\-mac | string |  `mac address` 
action\_result\.parameter\.dst\-mac | string |  `mac address` 
action\_result\.parameter\.dl\-type | string | 
action\_result\.parameter\.src\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.dst\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.nw\-proto | string | 
action\_result\.parameter\.tp\-src | numeric | 
action\_result\.parameter\.tp\-dst | numeric | 
action\_result\.parameter\.src\-inport | string | 
action\_result\.parameter\.switchid | string |  `dpid`   

## action: 'unblock flow'
Unblock network traffic matching flow parameters\.

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**src\-mac** |  optional  | source mac address | string |  `mac address` 
**dst\-mac** |  optional  | destination mac address | string |  `mac address` 
**dl\-type** |  optional  | layer\-3 protocol \(IPv4 or ARP\) | string | 
**src\-ip** |  optional  | source ip address or cidr | string |  `ip`  `cidr` 
**dst\-ip** |  optional  | destination ip address or cidr | string |  `ip`  `cidr` 
**nw\-proto** |  optional  | layer\-4 protocol \(TCP, UDP, or ICMP\) | string | 
**tp\-src** |  optional  | layer\-4 source port number | numeric | 
**tp\-dst** |  optional  | layer\-4 destination port number | numeric | 
**switchid** |  optional  | datapath identifier | string |  `dpid` 
**src\-inport** |  optional  | input port | string | 
**priority** |  optional  | priority for this rule | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.data\.\*\.activityid | string |  `activityid` 
action\_result\.parameter\.priority | string | 
action\_result\.parameter\.src\-mac | string |  `mac address` 
action\_result\.parameter\.dst\-mac | string |  `mac address` 
action\_result\.parameter\.dl\-type | string | 
action\_result\.parameter\.src\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.dst\-ip | string |  `ip`  `cidr` 
action\_result\.parameter\.nw\-proto | string | 
action\_result\.parameter\.tp\-src | numeric | 
action\_result\.parameter\.tp\-dst | numeric | 
action\_result\.parameter\.src\-inport | string | 
action\_result\.parameter\.switchid | string |  `dpid`   

## action: 'get firewall status'
Get the enable/disable state of the firewall\.

Type: **generic**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.result | string |   

## action: 'enable firewall'
Enable the firewall\.

Type: **generic**  
Read only: **False**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.details | string |   

## action: 'disable firewall'
Disable the firewall\.

Type: **generic**  
Read only: **False**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.details | string |   

## action: 'delete firewall rule'
Delete a firewall rule\.

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**activityid** |  required  | rule id to delete | string |  `activityid` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.status | string |   

## action: 'list firewall rules'
List firewall rules stored in the controller\.

Type: **investigate**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.firewall\_rules\.\*\.activityid | string |  `activityid` 
action\_result\.data\.\*\.firewall\_rules\.\*\.priority | string | 
action\_result\.data\.\*\.firewall\_rules\.\*\.action | string | 
action\_result\.data\.\*\.firewall\_rules\.\*\.src\-mac | string |  `mac address` 
action\_result\.data\.\*\.firewall\_rules\.\*\.dst\-mac | string |  `mac address` 
action\_result\.data\.\*\.firewall\_rules\.\*\.dl\-type | string | 
action\_result\.data\.\*\.firewall\_rules\.\*\.src\-ip | string |  `ip`  `cidr` 
action\_result\.data\.\*\.firewall\_rules\.\*\.dst\-ip | string |  `ip`  `cidr` 
action\_result\.data\.\*\.firewall\_rules\.\*\.nw\-proto | string | 
action\_result\.data\.\*\.firewall\_rules\.\*\.tp\-src | numeric | 
action\_result\.data\.\*\.firewall\_rules\.\*\.tp\-dst | numeric | 
action\_result\.data\.\*\.firewall\_rules\.\*\.src\-inport | string | 
action\_result\.data\.\*\.firewall\_rules\.\*\.switchid | string |  `dpid`   

## action: 'list switches'
List SDN switches managed by the controller\.

Type: **investigate**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.switches\.\*\.switchDPID | string |  `dpid` 
action\_result\.data\.\*\.switches\.\*\.connectedSince | string | 
action\_result\.data\.\*\.switches\.\*\.ip | string |  `ip` 
action\_result\.data\.\*\.switches\.\*\.port | numeric |   

## action: 'list internal links'
List single\-hop links discovered via LLDP\.

Type: **investigate**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.links\.\*\.src\-switch | string |  `dpid` 
action\_result\.data\.\*\.links\.\*\.src\-port | numeric | 
action\_result\.data\.\*\.links\.\*\.dst\-switch | string |  `dpid` 
action\_result\.data\.\*\.links\.\*\.dst\-port | numeric | 
action\_result\.data\.\*\.links\.\*\.type | string | 
action\_result\.data\.\*\.links\.\*\.direction | string |   

## action: 'list external links'
List multi\-hop links discovered via BDDP\.

Type: **investigate**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.links\.\*\.src\-switch | string |  `dpid` 
action\_result\.data\.\*\.links\.\*\.src\-port | numeric | 
action\_result\.data\.\*\.links\.\*\.dst\-switch | string |  `dpid` 
action\_result\.data\.\*\.links\.\*\.dst\-port | numeric | 
action\_result\.data\.\*\.links\.\*\.type | string | 
action\_result\.data\.\*\.links\.\*\.direction | string |   

## action: 'list devices'
List devices tracked by the SDN controller\.

Type: **investigate**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.devices\.\*\.mac | string |  `mac address` 
action\_result\.data\.\*\.devices\.\*\.ip | string |  `ip` 
action\_result\.data\.\*\.devices\.\*\.vlan | string |  `vlan` 
action\_result\.data\.\*\.devices\.\*\.lastSeen | string | 
action\_result\.data\.\*\.devices\.\*\.attachmentPoint\.port | numeric | 
action\_result\.data\.\*\.devices\.\*\.attachmentPoint\.switchDPID | string |  `dpid`   

## action: 'get uptime'
Get time since SDN controller startup\.

Type: **generic**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.systemUptimeMsec | numeric | 
action\_result\.data\.\*\.hhmmss | string |   

## action: 'list static flows'
List static flow rules\.

Type: **investigate**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.flows\.\*\.name | string |  `flow name` 
action\_result\.data\.\*\.flows\.\*\.switch | string |  `dpid` 
action\_result\.data\.\*\.flows\.\*\.priority | string | 
action\_result\.data\.\*\.flows\.\*\.cookie | string | 
action\_result\.data\.\*\.flows\.\*\.match | string | 
action\_result\.data\.\*\.flows\.\*\.instructions | string | 
action\_result\.data\.\*\.flows\.\*\.hardTimeoutSec | string | 
action\_result\.data\.\*\.flows\.\*\.idleTimeoutSec | string | 
action\_result\.data\.\*\.flows\.\*\.command | string | 
action\_result\.data\.\*\.flows\.\*\.cookieMask | string | 
action\_result\.data\.\*\.flows\.\*\.outPort | string | 
action\_result\.data\.\*\.flows\.\*\.outGroup | string | 
action\_result\.data\.\*\.flows\.\*\.version | string | 
action\_result\.data\.\*\.flows\.\*\.flags | string |   

## action: 'add static flow'
Add a static flow rule\.

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**name** |  required  | unique name for this flow | string |  `flow name` 
**switch** |  required  | datapath processing the flow | string |  `dpid` 
**table** |  optional  | table where flow will be installed \(default\: 0\) | numeric | 
**priority** |  optional  | priority \(32\-bit unsigned\) \(default\: 2147483647\) | numeric | 
**match** |  optional  | packet match fields \(default\: match all packets\) | string | 
**instructions** |  optional  | instructions to perform \(default\: drop\) | string | 
**hard\_timeout** |  optional  | hard timeout in seconds \(default\: no timeout\) | numeric | 
**idle\_timeout** |  optional  | idle timeout in seconds \(default\: no timeout\) | numeric | 
**cookie** |  optional  | cookie \(64\-bit number\) \(default\: no cookie\) | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.status | string | 
action\_result\.data\.\*\.success | boolean |   

## action: 'delete static flow'
Remove a static flow rule\.

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**name** |  required  | name of flow to delete | string |  `flow name` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.status | string | 
action\_result\.data\.\*\.success | boolean |   

## action: 'clear static flows'
Remove all static flow rules\.

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**switch\_id** |  optional  | datapath where flows will be cleared | string |  `dpid` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.data\.\*\.status | string | 
action\_result\.data\.\*\.success | boolean | 