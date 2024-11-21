#Ansible

#rocky01 = 192.168.0.28 - Ansible Controller
#rocky02 = 192.168.0.38
#rocky03 = 192.168.0.39


#create a admin user
sudo root
sudo adduser user
sudo passwd user
sudo usermod -aG wheel user


#SSH (02-03)
sudo apt install openssh-server # real linux
sudo dnf install openssh-server # just being different linux (Rocky)


ssh user@192.168.0.38 - look at automatically from ansible

#create secure ssh on controller
#(01) with pass phrase
ssh-keygen -t ed25519 -C "ansible controller"

#list hidden
ls -la .ssh

#copy to clients
ssh-copy-id -i ~/.ssh/id_ed25519.pub user@192.168.0.38
ssh-copy-id -i ~/.ssh/id_ed25519.pub user@192.168.0.39

#connect to client user key
ssh -i ~/.ssh/id_ed25519 user@192.168.0.38













