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
  
  
  ** ANSIBLE HOST FILE CAN BE FOUND UNDER THIS PATH **
  
  cat /home/vagrant/hosts
  
  YOU CAN MANUALLY EDIT THE FILE AS WELL WITH THE CONTAINER IP WHICH YOU WILL GET VIA RUNNING -  lxc list ( command)
  
  ```
  root@demo:~$ lxc list
+------------------+---------+------+------+------------+-----------+
|       NAME       |  STATE  | IPV4 | IPV6 |    TYPE    | SNAPSHOTS |
+------------------+---------+------+------+------------+-----------+
| first            | RUNNING |      |      | PERSISTENT | 0         |
+------------------+---------+------+------+------------+-----------+
| integral-crawdad | RUNNING |      |      | PERSISTENT | 0         |
+------------------+---------+------+------+------------+-----------+
```
  
  
  
  ** NOTE LXC container is similar to full blown VM - it is not like docker container - Each VM has it own kernel **
