## enable firewall
    sudo ufw enable
## disable firewall
    sudo ufw disable
## commnad to reset the firewall
    sudo ufw reset
## to deny incoming and outcoming connection 
      sudo ufw default deny incoming/outgoing

## to accept a connection to allow
    sudo ufw default allow outgoing
## to allow through port 
    sudo ufw allow 22
## to allow any incoming connection from any computer from any port 
    sudo ufw allow proto tcp from any to any port 80,443
## status
  sudo ufw status verbose
## status number
    sudo ufw status numbered 
## to delete rule with numbered 
    sudo ufw delete 1
