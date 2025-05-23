# Proxmox Backup Server by HTTP - Disk check
Zabbix Template that enable monitoring of Ceph and Smart on Proxmox PBS nodes  

It used to be added to the [Proxmox Backup Server by HTTP](https://github.com/ismvru/zbx-tmplt-pbs) template because it shares many MACROS  
Tested with Proxmox Backup Server by HTTP on Zabbix Server 6.0 LTS  

All the MACROS used are explained in the template  

## Instructions
Create new user "zabbix" in Configuration -> Access Control - User Management  

Issue new token "zabbix" for user "zabbix@xxx" in Configuration -> Access Control -> API Token  

Add User e API Token permission for the user "zabbix with "/" and Role Audit in Configuraion -> Access Control -> Permissions  
The templates want /datastore, /system/status and /system/tasks in (Please note that the user on whose behalf the token is issued must have the appropriate rights) but isn't possibile to create a custom group in PBS  

Configure macros:  
{$PBS.NODE.NAME}  
{$PBS.TOKEN.ID}  
{$PBS.TOKEN.SECRET}  
