# ansible-playground

** TO Start VM **

1 - git clone \<this repo\>
  
2 - vagrant up
  
3 - vagrant ssh
  
  ** You will see all ansible config present in /home/vagrant/ location **
  
  ansible.cfg
  
  sample_play.yaml
  
  hosts
  
  
 ** Some LXC Command **
  
  lxc list --> To get all the containers
  
  lxc exec \<containername\> bash --> to login to container
  
  
  ** NOTE LXC container is similar to full blown VM - it is not like docker container - Each VM has it own kernel **
