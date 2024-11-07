# Owncloud 

Aquesta es l'instalació i configuració de Owncloud.

## Instalació i actualització

Lo primer es instalar aquest .zip: https://download.owncloud.com/server/stable/owncloud-complete-20240724.zip

Com la versió que hi ha es 7.4 de PHP, l'hem d'actualitzar a Ubuntu 24.04.

### Actualització

Per actualitzar-ho heu de seguir els següents pasos:

Instal·leu els requisits previs de PPA:
```bash
sudo apt install software-properties-common -y
```

Instal·la les eines necessàries per treballar amb els arxius de paquets personals (PPA).
```bash
LC_ALL=C.UTF-8 sudo add-apt-repository ppa:ondrej/php -y
```

Actualitza ara els repositoris:
```bash
sudo apt update
```

Instal·la les llibreries de PHP de la versió 7.4
```bash
sudo apt install php7.4 -y
```
```bash
sudo apt install -y php libapache2-mod-php7.4
```

```bash
sudo apt install -y php7.4-fpm php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-gd php7.4-xml php7.4-intl php7.4-mysql php7.4-cli php7.4-ldap php7.4-zip php7.4-curl
```

Seleccioneu la versió de PHP que voleu:
```bash
sudo update-alternatives --config php
```

Activa els mòduls d'apache2 necessaris:
```bash
sudo a2enmod proxy_fcgi setenvif
```

```bash
sudo a2enconf php7.4-fpm
```

Reinicieu l'apache2:
```bash
sudo service apache2 restart
```
