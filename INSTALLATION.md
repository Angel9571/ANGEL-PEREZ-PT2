# Manual d'instal·lacio d'ownCloud amb virtualització mitjançant IsardVDI
## Instal·lar la versió 7.4 de PHP a Ubuntu 24.04

Primero que tiens que hacer es entrar a la terminal de tu maquina y empezar por este comando "sudo apt install software-properties-common -y", te pedira una contraseña es usuario. Lo que hace el comando es que Instalas los requissitos previos de PPA.

Al tenerlo pondras el siguiente comando que es este "LC_ALL=C.UTF-8 sudo add-apt-repository ppa:ondrej/php -y", este comando lo que hace es que instala las herramientas  necesarias para trabajar con el archivo de paquetes personales (PPA)

![1](https://github.com/user-attachments/assets/89809771-aa4f-4b40-8f87-5fa0ef6ded29)

Ahora actualizaras los repositorios con este comando "sudo apt update"

![2](https://github.com/user-attachments/assets/3695bbb5-0197-4f61-acf4-bd43d1a0623e)



Ahora con este comando que te podre ahora instalaras las librerias de PHP de la version 7.4 "sudo apt install php7.4 -y" al tenerlo tendras que poner este otro comando "sudo apt install php7.4 -y" y luego este otro "sudo apt install -y php7.4-fpm php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-gd php7.4-xml php7.4-intl php7.4-mysql php7.4-cli php7.4-ldap php7.4-zip php7.4-curl"

![3](https://github.com/user-attachments/assets/d76b6995-2dc6-44a5-abb2-e06b5be3d797)

![4](https://github.com/user-attachments/assets/b13a697a-c8cf-4878-ab38-8222ab139617)

![5](https://github.com/user-attachments/assets/292ef9b3-6d0e-4f16-b864-6fe3c638846e)

Ahora con este comando tienes que elegir la veriosn de PHP que quieras con este comando de aqui "sudo update-alternatives --config php", yo elegi la primera version la 1 par aelegirla tienes que poner el numero de la version y darle ENTER.!

![6](https://github.com/user-attachments/assets/c747f9fa-e14d-4e5a-8b0a-16df7003a73c)

Cuando ayas elegido la version que quieras tiens que activar los modulos de apache2 necesarios con estos dos comandos "sudo a2enmod proxy_fcgi setenvif" y "sudo a2enconf php7.4-fpm" 

![7](https://github.com/user-attachments/assets/26545f0b-923e-4669-801f-5f6f3038bd77)

![8](https://github.com/user-attachments/assets/a49072e8-f0ab-4d52-9f4e-a7bb207244d7)

Y por ultimo reiniciamos el apache2 "sudo service apache2 restart"

![9](https://github.com/user-attachments/assets/2e748a75-3246-4e1a-8f0c-f449c9e98b0d)
