# Doação
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=WVUG4ZM6Z2MZL&source=url)

# MyRouter


Sistema ERP de Gestão de Provedores

Sistema completo 100% integrado com Freeradius, integração com MikroTik e Ubiquiti,  e em fase de homologação integração com Juniper


Suporta Boletos com Registro e Sem Registro, sistema de arquivo de remessa e retorno, também integrado com GERENCIANET


 <img width="1833" alt="tela-inicial" src="https://user-images.githubusercontent.com/3342262/52006104-7cea0180-24b2-11e9-8e77-6ee85b64b4e0.png">


* Forum para ajuda e dúvidas sobre o Projeto MyRouter

https://www.myrouter.com.br/forums/forum/myrouter/


# MyRouter  IMG-OVA

Download da imagem OVA.

https://drive.google.com/file/d/1_nic2lJ_KzSDyxE8I8Mj78Jslt9N-UVB/view?usp=sharing


Para acesso ao sistema via web
http://IPDOSERVIDOR/myrouter/

login: admin </br>
senha: myrouter


Para acesso ao Terminal do Linux, a senha do usuário root é: myrouter

# Instalação via Linux

O sistema funciona perfeitamento no Linux Debian 8 , e a versão do PHP5.X


* Baixe a iso no link:
```

https://cdimage.debian.org/cdimage/archive/8.11.0/amd64/iso-cd/debian-8.11.0-amd64-netinst.iso 

```


* Adicionar Repositório de Pacotes: </br>
Caso tenho problema em instalar os pacotes, muito provável que seja problema com a falta de repositório do Debian, segue abaixo como adicionar os repositorio.

```
echo "deb http://ftp.br.debian.org/debian/ jessie main contrib non-free" >> /etc/apt/sources.list
echo "deb-src http://ftp.br.debian.org/debian/ jessie main contrib non-free" >> /etc/apt/sources.list

echo "deb http://security.debian.org/ jessie/updates main contrib non-free" >> /etc/apt/sources.list
echo "deb-src http://security.debian.org/ jessie/updates main contrib non-free" >> /etc/apt/sources.list

```

* Atualizando a lista de repositório 
```

apt-get update

```

* Pacotes recomendado para instalação:

```
apt-get install -y tofrodos linux-headers-`uname -r` libcrypto++-dev  ntpdate libsuitesparse-dev binutils-multiarch dctrl-tools snmp python python-soappy \
reportbug ruby libgdbm-dev libiodbc2 libiodbc2-dev libkrb5-dev libldap2-dev libpam0g-dev libpcap-dev libpcap0.8 libpcap0.8-dev libpq-dev libsasl2-dev libsensors4-dev \
python-dev zlib1g-dev libssh2-1-dev libssh2-php libfreeradius-client2 rrdtool sudo autotools-dev build-essential autoconf g++ libperl-dev libtool guile-2.0-dev gcc \
apache2 libapache2-mod-php5 php5 php5-fpm php5-xcache php5-memcache php5-memcached  memcached php5-mysql php5-cli php5-curl php5-mcrypt php5-imap php-pear php-db php-mail \
php-mail-mime php-net-smtp php5-cgi php5-dev php5-rrd  php5-gd php5-pgsql libcurl4-openssl-dev openssl perl dh-make-perl python-mysqldb pan unzip tk8.5 tk8.5-dev zlibc \
sysstat locales ntpdate libdbd-mysql libdbd-mysql-perl  python2.7 python2.7-dev mariadb-client mariadb-server mc liblua5.1-0 liblua5.1-0-dev perl libwww-perl sox mpg123 \
freeradius freeradius-common freeradius-dbg freeradius-mysql freeradius-utils libfreeradius-dev libfreeradius2 ntp fail2ban libxml2-dev uuid-dev libjansson4 libjansson-dev \
libmyodbc unixodbc-bin subversion bison flex libnewt-dev sqlite3 libsqlite3-dev uuid uuid-dev libasound2-dev libogg-dev libvorbis-dev libcurl4-openssl-dev libical-dev \
libneon27-dev libsrtp0-dev libspandsp-dev libiksemel-dev libiksemel-utils libiksemel3 doxygen python-dateutil python-protobuf python-pycryptopp python-argparse python-dev \
libncurses5-dev python-pip mrtg rrdtool build-essential pkg-config

```

* Customizar o PHP e MySQL para ter mais performace:

```
sed -i 's/max_execution_time = 30/max_execution_time = 3000/' /etc/php5/apache2/php.ini
sed -i 's/display_errors = On/display_errors = Off/' /etc/php5/apache2/php.ini
sed -i 's/max_input_time = 60/max_input_time = 600/' /etc/php5/apache2/php.ini
sed -i 's/memory_limit = 128M/memory_limit = 2048M/' /etc/php5/apache2/php.ini
sed -i 's/upload_max_filesize = 2M/upload_max_filesize = 3G/' /etc/php5/apache2/php.ini
sed -i 's/post_max_size = 8M/post_max_size = 3G/' /etc/php5/apache2/php.ini
sed -i 's/query_cache_size = 16M/query_cache_size  = 128M/' /etc/mysql/my.cnf

```

* Configurando Mysql

Criando configurando a senha do root do MySQL

```
mysqladmin -u root password 33#erp@myrouter#33 1>/dev/null 2>/dev/null

```

Exportando o banco de dados


```
mysql -p33#erp@myrouter#33 < /var/www/myrouter/sql/myrouter.sql 1>/dev/null 2>/dev/null

```




* Para acesso ao sistema via web http://IPDOSERVIDOR/myrouter/

login: admin </br>
senha: 123



# Telas do MyRouter

Cadastro de planos de acesso, na mesma tela voce pode cadastrar planos e compartilhar com uso de MikroTik, Ubiquiti e Juniper

<img width="1614" alt="captura de tela 2019-01-30 as 19 15 37" src="https://user-images.githubusercontent.com/3342262/52013311-d9095180-24c3-11e9-82cb-3c379d18d9f4.png">

Cadastro de de Clientes 

<img width="1622" alt="captura de tela 2019-01-30 as 19 15 52" src="https://user-images.githubusercontent.com/3342262/52013369-02c27880-24c4-11e9-8ad8-541f1559eac2.png">

Cadastro de Assinantes

<img width="1602" alt="captura de tela 2019-01-30 as 19 16 03" src="https://user-images.githubusercontent.com/3342262/52013388-179f0c00-24c4-11e9-93e5-7d583166824c.png">

Ordem de Serviço

<img width="1609" alt="captura de tela 2019-01-30 as 19 22 47" src="https://user-images.githubusercontent.com/3342262/52013540-72d0fe80-24c4-11e9-9dc6-587b2ef55a09.png">


* Entre outros muitos recursos disponível 
