# ansible-playground


** PLEASE INSTALL VAGRANT AND VIRTUAL BOX IN YOUR LAPTOP BEFORE USING THIS VAGRANT FILE AND CONFIG TO START ANSIBLE PLAYGROUP **


**  NOTE - THIS ENTIRE SETUP WILL TAKE NEARLY 1 HOUR OF TIME **


** TO Start VM **

1 - git clone \<this repo\>
  
2 - vagrant up
  
3 - vagrant ssh

  
  ** You will see all ansible config present in /home/vagrant/  path **
  
  ansible.cfg
  
  sample_play.yaml
  
  hosts
  
  
 ** SOME LXC COMMAND TO BE USED **
  
  lxc list --> To get all the containers
  
  lxc exec \<containername\> bash --> to login to container
  
  lxc start \<containername\> --> to start a stopped container
  
  
  ** ANSIBLE HOST FILE CAN BE FOUND UNDER THIS PATH **
  
  cat /home/vagrant/hosts
  
  YOU CAN MANUALLY EDIT THE FILE AS WELL WITH THE CONTAINER IP WHICH YOU WILL GET VIA RUNNING -  lxc list ( command)
  
  ```
  root@demo:~$ lxc list
+-------------------+---------+----------------------+-----------------------------------------------+-----------+-----------+
|       NAME        |  STATE  |         IPV4         |                     IPV6                      |   TYPE    | SNAPSHOTS |
+-------------------+---------+----------------------+-----------------------------------------------+-----------+-----------+
| ansible-client-2  | RUNNING | 10.164.41.188 (eth0) | fd42:ac0e:fd26:496e:216:3eff:fe4f:84ae (eth0) | CONTAINER | 0         |
+-------------------+---------+----------------------+-----------------------------------------------+-----------+-----------+
| ansible-client-3  | RUNNING | 10.164.41.161 (eth0) | fd42:ac0e:fd26:496e:216:3eff:fe1e:5b92 (eth0) | CONTAINER | 0         |
+-------------------+---------+----------------------+-----------------------------------------------+-----------+-----------+
| ansible-client-4  | RUNNING | 10.164.41.31 (eth0)  | fd42:ac0e:fd26:496e:216:3eff:fe0d:2551 (eth0) | CONTAINER | 0         |
+-------------------+---------+----------------------+-----------------------------------------------+-----------+-----------+
| ansible-client-7  | RUNNING | 10.164.41.229 (eth0) | fd42:ac0e:fd26:496e:216:3eff:fefd:7ef9 (eth0) | CONTAINER | 0         |
+-------------------+---------+----------------------+-----------------------------------------------+-----------+-----------+
| ansible-client-8  | RUNNING | 10.164.41.235 (eth0) | fd42:ac0e:fd26:496e:216:3eff:fe71:e634 (eth0) | CONTAINER | 0         |
+-------------------+---------+----------------------+-----------------------------------------------+-----------+-----------+
| ansible-client-9  | RUNNING | 10.164.41.252 (eth0) | fd42:ac0e:fd26:496e:216:3eff:fea7:143 (eth0)  | CONTAINER | 0         |
+-------------------+---------+----------------------+-----------------------------------------------+-----------+-----------+
| ansible-client-10 | RUNNING | 10.164.41.17 (eth0)  | fd42:ac0e:fd26:496e:216:3eff:fe76:ac00 (eth0) | CONTAINER | 0         |
+-------------------+---------+----------------------+-----------------------------------------------+-----------+-----------+

```
  
  NOTE - Once the server is setup - Next Day you if you restart the VM the Container might get diff ip as it is issued via VM DHCP 
         In that case the ansible hosts file which was created during provisioning would have to be updated with the current IP address of Containers -
         lxc list --> get the current IP from running container and update the hosts file
         
         update the - /etc/hosts
  
  
  ** NOTE LXC container is similar to full blown VM - it is not like docker container - Each VM has it own kernel **
