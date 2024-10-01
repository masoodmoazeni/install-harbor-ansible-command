# Install Harbor With Ansible On ubuntu
```
apt update && apt install python3-pip
pip install ansible
apt install sshpass -y  
```

edir you host and user& password on hosts file and run command
```
ansible-playbook -i hosts playbook.yml
```

![image](https://github.com/user-attachments/assets/cd134930-69d9-494e-b6fb-ee502238a05f)
