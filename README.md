# lesson2

# Дисковая подсистема
Согласно условиям ДЗ, в приложении файлы vagrant, playbook, script, mdadm

# Шаги при развертывании VM и автоматической сборки raid

С данного сайта был взят образ под virtualbox с системой centos 7

---
https://app.vagrantup.com/centos/boxes/7
---
Далее регистрируем файл с расширением .box в вагранте

---
vagrant box add CentOS-7-x86_64-Vagrant-2004_01.VirtualBox.box --name movik
---
vagrant up
---

После установки и запуска VM, приступаем к сборке raid (я собирал raid1)

---
export ANSIBLE_HOST_KEY_CHECKING=False
---
ansible-playbook -i /.vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory playbook.yml -vv
---

После выполнения сборки, команда lsblk

![image](https://github.com/movik242/lesson2/assets/143793993/f684b5e3-157a-46d7-87bf-d04047d4cd9c)



