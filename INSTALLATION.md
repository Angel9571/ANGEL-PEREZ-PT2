# Manual d'instal·lacio d'ownCloud amb virtualització mitjançant IsardVDI
## Instal·lar la versió 7.4 de PHP a Ubuntu 24.04

Primero que tiens que hacer es entrar a la terminal de tu maquina y empezar por este comando "**sudo apt install software-properties-common -y**", te pedira una contraseña es usuario. Lo que hace el comando es que Instalas los requissitos previos de PPA.

Al tenerlo pondras el siguiente comando que es este "**LC_ALL=C.UTF-8 sudo add-apt-repository ppa:ondrej/php -y**", este comando lo que hace es que instala las herramientas  necesarias para trabajar con el archivo de paquetes personales (PPA)

![1](https://github.com/user-attachments/assets/89809771-aa4f-4b40-8f87-5fa0ef6ded29)

Ahora actualizaras los repositorios con este comando "sudo apt update"

![2](https://github.com/user-attachments/assets/3695bbb5-0197-4f61-acf4-bd43d1a0623e)

Ahora con este comando que te podre ahora instalaras las librerias de PHP de la version 7.4 "**sudo apt install php7.4 -y**" al tenerlo tendras que poner este otro comando "**sudo apt install php7.4 -y**" y luego este otro "**sudo apt install -y php7.4-fpm php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-gd php7.4-xml php7.4-intl php7.4-mysql php7.4-cli php7.4-ldap php7.4-zip php7.4-curl**"

![3](https://github.com/user-attachments/assets/d76b6995-2dc6-44a5-abb2-e06b5be3d797)

![4](https://github.com/user-attachments/assets/b13a697a-c8cf-4878-ab38-8222ab139617)

![5](https://github.com/user-attachments/assets/292ef9b3-6d0e-4f16-b864-6fe3c638846e)

Ahora con este comando tienes que elegir la veriosn de PHP que quieras con este comando de aqui "**sudo update-alternatives --config php**", yo elegi la primera version la 1 par aelegirla tienes que poner el numero de la version y darle ENTER.

![6](https://github.com/user-attachments/assets/c747f9fa-e14d-4e5a-8b0a-16df7003a73c)

Cuando ayas elegido la version que quieras tiens que activar los modulos de apache2 necesarios con estos dos comandos "**sudo a2enmod proxy_fcgi setenvif**" y "**sudo a2enconf php7.4-fpm**" 

![7](https://github.com/user-attachments/assets/26545f0b-923e-4669-801f-5f6f3038bd77)

![8](https://github.com/user-attachments/assets/a49072e8-f0ab-4d52-9f4e-a7bb207244d7)

Y por ultimo reiniciamos el apache2 "**sudo service apache2 restart**"

![9](https://github.com/user-attachments/assets/2e748a75-3246-4e1a-8f0c-f449c9e98b0d)

## Instalacio del ownCloud

Lo primer comando que hay que poner es "**sudo apt update**" y lugo "**sudo apt upgrate**"

![1 1](https://github.com/user-attachments/assets/5a8dfcc6-1267-405f-8e66-e5a557da29c1)

![1 2](https://github.com/user-attachments/assets/d6bead0c-2a70-44fd-b6be-798645f456fc)

Al tenerlo tendremos que instalar el servidor web apache2 con este comando "**sudo apt install -y apache2**"

![1 3](https://github.com/user-attachments/assets/7f6d4c15-2a23-43a8-a7b4-41aee38c3615)

Ahora necesitaras instalar el servidor de base de datos mysql-server se instala con este comando
"**sudo apt install -y mysql-server**"

![1 6](https://github.com/user-attachments/assets/a7d9d977-8dd3-49f3-8a5d-257e66f84256)

Ahora instalaremos algunas librerias de php que es el lenguage principal que utilizan las aplicaciones, para instalarlo tiens que poner los siguientes comandos
"sudo apt install -y php libapache2-mod-php" y cuando se te instale pones este que tardara unos minutos "**sudo apt install -y php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-mysql php-cli php-ldap php-zip php-curl**"

![1 4](https://github.com/user-attachments/assets/0ed4c73f-574d-4416-b3f0-ea720b555ac7)

![1 5](https://github.com/user-attachments/assets/481934fd-b10d-492e-8746-532e75a6b6b8)

Al tenerlo instalado necesitamos reiniciar el servidor apache2 se reinicia con este comando
"**sudo systemctl restart apache2**" 

Al tenerlo tendremos que acceder a la consola de MySQL para hazerlo necesitamos poner este comando
"**sudo mysql**" luego dentro de ese comando ponemos "**CREATE DATABASE bbdd;**" al tenerlo pondras el siguiente "**CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';**" despues este comando "GRANT ALL ON bbdd.* to 'usuario'@'localhost';" y al tenerlo nos saldremos poniendo "**exit**"

![1 7](https://github.com/user-attachments/assets/a9f151e8-a263-40cc-962e-fb346a8b926b)

Ahora instalaremos el ownCloud con este link:https://download.owncloud.com/server/stable/owncloud-complete-20240724.zip
Al tenerlo tendras que cambiarle el nombre a "**app-web**"

![1 11](https://github.com/user-attachments/assets/cc2742f1-901a-46d8-a06d-082427d27f24)

Al tener el nombre cambaido entra a la terminal y pon el siguiente comando que es este "**sudo cp ~/Baixades/app-web.zip /var/www/html**" si tienes el idioma del Pc en español no pongas "**Baixades**" pon "**Descargas**" y si lo tienes en ingles pon "**downloads**"
Te pedira una contraseña es "**usuario**"

Ahora hay que ir al dirctorio /var/www/html, para entrar al direcotrio hay que poner este comando "**cd /var/www/html**"
Al estar dentro de /var/www/html hay que poner este comando que descomprimer el fixero que hemos descargado "**sudo unzip app-web.zip**"

![1 8](https://github.com/user-attachments/assets/5d5771f3-d049-4ac2-a009-4fbce59cefc7)

Al tenerlo tenemos que eliminar la carpreta creada cuando hemos echo el unzip se elimina con este comando "**sudo rm -rf app-web/**"

Ahora hay que eliminar el fixero index.html de apache2 con este comando "**sudo rm -rf /var/www/html/index.html**" 
Si te saca del direcotrio /var/www/html entra de nuevo con este comando "**cd /var/www/html**" 

Y cuando estes dentro pon este comando que sirve para darle persmisos al directorio /var/www/html
"**sudo chmod -R 775 .**" al tenerlo tendras que poner este otro comando "**sudo chown -R usuario:www-data .**" 

![1 10](https://github.com/user-attachments/assets/8f74c4ab-0f1b-43db-8fb4-a9d8f9a09d61)

Cuando ya lo tengas ves a tu navegador FireFox y escribe "**localhost**/"

![1 12](https://github.com/user-attachments/assets/83b29464-510c-49c8-be70-203c3425c9bc)

Al entar te saldran dos opicones dale click a la segunda que pone "**owncloud/**", al darle te llevara al ownCloude.

![1 13](https://github.com/user-attachments/assets/86459fae-7967-44f0-8e7b-9256bd951bdd)
