# Mikrotik-Backup2ftp

#### Create new Mikrotik Script from winbox - system -> scripts
```
:local name value=[/system identity get name];
/system backup save name=$name;
/export file=$name;
/tool fetch address=<ftp-address> user=<ftp-user> password=<ftp-password> mode=ftp dst-path=("/".$name.".rsc") src-path=($name.".rsc") upload=yes;
/tool fetch address=<ftp-address> user=<ftp-user> password=<ftp-password> mode=ftp dst-path=("/".$name.".backup") src-path=($name.".backup") upload=yes;
```
