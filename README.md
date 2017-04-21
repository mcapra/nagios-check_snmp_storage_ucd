# nagios-check_snmp_storage_ucd
This plugin is a modification of the check_snmp_storage plugin that properly handles large mount points (>4TB)

It works by leveraging the UCD-SNMP-MIB module. It was initially created due to limitations within the HOST-RESOURCES-MIB module used by check_snmp_storage that caused integer overflow for mounts with block counts greater than 2147483647. 

Your remote server's /etc/snmpd.conf config file must include:

includeAllDisks  10000

To include all mounts that are at least 10MB in size. This directive can be modified to include all disks as well.
