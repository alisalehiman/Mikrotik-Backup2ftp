# Mikrotik-Backup2ftp

#### Create new Mikrotik Script
###### winbox - system -> scripts and set name backup2ftp
###### run every day backup2ftp with system -> Scheduler 
```
:local name value=[/system identity get name];
:local ftpaddress value=<ftp-address>;
:local ftpuser value=<ftp-user>;
:local ftppass value=<ftp-password>;
/system backup save name=$name;
/export file=$name;
/tool fetch address=$ftpaddress user=$ftpuser password=$ftppass mode=ftp dst-path=("/".$name.".rsc") src-path=($name.".rsc") upload=yes;
/tool fetch address=$ftpaddress user=$ftpuser password=$ftppass mode=ftp dst-path=("/".$name.".backup") src-path=($name.".backup") upload=yes;
```

