## to create samba server you need to install below oprions
    samba samba-client samba-common

    then check status for firewall 
    mkdir /samba
    then give permissions to directory or file you want to share
    then if you receive a error :chcon: can't apply partial context to unlabeled file
      then run below commands :
      chcon -h system_u:object_r:samba_share_t /home/share
      chcon -R -h system_u:object_r:samba_share_t /home/share
