# zabbix-passo-a-passo
Arquivos para ajudar instalar o zabbix localmente, para fins de estudo


devne@Dell5400:~$ su
Password:

root@Dell5400:/home/devne# wget https://repo.zabbix.com/zabbix/7.4/release/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.4+ubuntu24.04_all.deb
--2025-08-29 21:15:31--  https://repo.zabbix.com/zabbix/7.4/release/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.4+ubuntu24.04_all.deb
Resolving repo.zabbix.com (repo.zabbix.com)... 178.128.6.101, 2604:a880:2:d0::2062:d001
Connecting to repo.zabbix.com (repo.zabbix.com)|178.128.6.101|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 7144 (7.0K) [application/octet-stream]
Saving to: ‘zabbix-release_latest_7.4+ubuntu24.04_all.deb’

zabbix-release_ 100%[=======>]   6.98K  --.-KB/s    in 0s

2025-08-29 21:15:31 (503 MB/s) - ‘zabbix-release_latest_7.4+ubuntu24.04_all.deb’ saved [7144/7144]

root@Dell5400:/home/devne#
root@Dell5400:/home/devne# ls
zabbix-release_latest_7.4+ubuntu24.04_all.deb
root@Dell5400:/home/devne# dpkg -i zabbix-release_latest_7.4+ubuntu24.04_all.deb
(Reading database ... 41518 files and directories currently installed.)
Preparing to unpack zabbix-release_latest_7.4+ubuntu24.04_all.deb ...
Unpacking zabbix-release (1:7.4-1+ubuntu24.04) over (1:6.0-1+ubuntu18.04) ...
Setting up zabbix-release (1:7.4-1+ubuntu24.04) ...
Installing new version of config file /etc/apt/sources.list.d/zabbix.list ...
root@Dell5400:/home/devne#
root@Dell5400:/home/devne# apt update
Hit:1 http://security.ubuntu.com/ubuntu noble-security InRelease
Hit:2 http://archive.ubuntu.com/ubuntu noble InRelease
Ign:3 http://mariadb.mirror.globo.tech/repo/10.5/ubuntu focal InRelease
Err:4 http://mariadb.mirror.globo.tech/repo/10.5/ubuntu focal Release
  404  Not Found [IP: 74.120.223.18 80]
Hit:5 http://archive.ubuntu.com/ubuntu noble-updates InRelease
Hit:6 http://archive.ubuntu.com/ubuntu noble-backports InRelease
Hit:7 https://repo.zabbix.com/zabbix-agent2-plugins/1/ubuntu bionic InRelease
Get:8 https://repo.zabbix.com/zabbix/7.4/release/ubuntu noble InRelease [2459 B]
Get:9 https://repo.zabbix.com/zabbix-tools/debian-ubuntu noble InRelease [2476 B]
Get:10 https://repo.zabbix.com/zabbix/7.4/stable/ubuntu noble InRelease [4672 B]
Get:11 https://repo.zabbix.com/zabbix/7.4/release/ubuntu noble/main Sources [942 B]
Get:12 https://repo.zabbix.com/zabbix/7.4/release/ubuntu noble/main all Packages [632 B]
Get:13 https://repo.zabbix.com/zabbix-tools/debian-ubuntu noble/main Sources [1367 B]
Get:14 https://repo.zabbix.com/zabbix-tools/debian-ubuntu noble/main all Packages [866 B]
Get:15 https://repo.zabbix.com/zabbix/7.4/stable/ubuntu noble/main Sources [6356 B]
Get:16 https://repo.zabbix.com/zabbix/7.4/stable/ubuntu noble/main all Packages [2513 B]
Get:17 https://repo.zabbix.com/zabbix/7.4/stable/ubuntu noble/main amd64 Packages [11.4 kB]
Reading package lists... Done
E: The repository 'http://mariadb.mirror.globo.tech/repo/10.5/ubuntu focal Release' does not have a Release file.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
root@Dell5400:/home/devne#
root@Dell5400:/home/devne# apt update
Hit:1 http://security.ubuntu.com/ubuntu noble-security InRelease
Ign:2 http://mariadb.mirror.globo.tech/repo/10.5/ubuntu focal InRelease
Hit:3 http://archive.ubuntu.com/ubuntu noble InRelease
Hit:4 http://archive.ubuntu.com/ubuntu noble-updates InRelease
Err:5 http://mariadb.mirror.globo.tech/repo/10.5/ubuntu focal Release
  404  Not Found [IP: 74.120.223.18 80]
Hit:6 http://archive.ubuntu.com/ubuntu noble-backports InRelease
Hit:7 https://repo.zabbix.com/zabbix-agent2-plugins/1/ubuntu bionic InRelease
Hit:8 https://repo.zabbix.com/zabbix/7.4/release/ubuntu noble InRelease
Hit:9 https://repo.zabbix.com/zabbix-tools/debian-ubuntu noble InRelease
Hit:10 https://repo.zabbix.com/zabbix/7.4/stable/ubuntu noble InRelease
Reading package lists... Done
E: The repository 'http://mariadb.mirror.globo.tech/repo/10.5/ubuntu focal Release' does not have a Release file.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
root@Dell5400:/home/devne# apt install zabbix-server-mysql zabbix-frontend-php zabbix-apache-conf zabbix-sql-scripts zabbix-agent
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  galera-4 libcgi-fast-perl libcgi-pm-perl libclone-perl
  libconfig-inifiles-perl libdbd-mysql-perl libdbi-perl
  libencode-locale-perl libfcgi-bin libfcgi-perl libfcgi0t64
  libhtml-parser-perl libhtml-tagset-perl
  libhtml-template-perl libhttp-date-perl libhttp-message-perl
  libio-html-perl liblwp-mediatypes-perl libmariadb3 libnuma1
  libsnappy1v5 libterm-readkey-perl libtimedate-perl
  liburi-perl liburing2 mariadb-common mariadb-server-core pv
  socat
Use 'apt autoremove' to remove them.
The following additional packages will be installed:
  apache2 apache2-bin apache2-data apache2-utils fonts-dejavu
  fonts-dejavu-extra fping libaom3 libapache2-mod-php
  libapache2-mod-php8.3 libapr1t64 libaprutil1-dbd-sqlite3
  libaprutil1-ldap libaprutil1t64 libcares2 libde265-0
  libevent-extra-2.1-7t64 libevent-pthreads-2.1-7t64 libgd3
  libheif-plugin-aomdec libheif-plugin-aomenc
  libheif-plugin-libde265 libheif1 libltdl7 liblua5.4-0
  libmodbus5 libodbc2 libonig5 libopenipmi0t64 libpci3
  libsnmp-base libsnmp40t64 libxpm4 libxslt1.1 mysql-client
  mysql-client-8.0 mysql-client-core-8.0 php-bcmath php-common
  php-curl php-gd php-ldap php-mbstring php-mysql php-xml
  php8.3-bcmath php8.3-cli php8.3-common php8.3-curl php8.3-gd
  php8.3-ldap php8.3-mbstring php8.3-mysql php8.3-opcache
  php8.3-readline php8.3-xml snmpd ssl-cert
Suggested packages:
  apache2-doc apache2-suexec-pristine | apache2-suexec-custom
  www-browser ufw php-pear libgd-tools libheif-plugin-x265
  libheif-plugin-ffmpegdec libheif-plugin-jpegdec
  libheif-plugin-jpegenc libheif-plugin-j2kdec
  libheif-plugin-j2kenc libheif-plugin-rav1e
  libheif-plugin-svtenc odbc-postgresql tdsodbc
  snmp-mibs-downloader snmptrapd zabbix-nginx-conf
  virtual-mysql-server
The following packages will be REMOVED:
  mariadb-client-core
The following NEW packages will be installed:
  apache2 apache2-bin apache2-data apache2-utils fonts-dejavu
  fonts-dejavu-extra fping libaom3 libapache2-mod-php
  libapache2-mod-php8.3 libapr1t64 libaprutil1-dbd-sqlite3
  libaprutil1-ldap libaprutil1t64 libcares2 libde265-0
  libevent-extra-2.1-7t64 libevent-pthreads-2.1-7t64 libgd3
  libheif-plugin-aomdec libheif-plugin-aomenc
  libheif-plugin-libde265 libheif1 libltdl7 liblua5.4-0
  libmodbus5 libodbc2 libonig5 libopenipmi0t64 libpci3
  libsnmp-base libsnmp40t64 libxpm4 libxslt1.1 mysql-client
  mysql-client-8.0 mysql-client-core-8.0 php-bcmath php-common
  php-curl php-gd php-ldap php-mbstring php-mysql php-xml
  php8.3-bcmath php8.3-cli php8.3-common php8.3-curl php8.3-gd
  php8.3-ldap php8.3-mbstring php8.3-mysql php8.3-opcache
  php8.3-readline php8.3-xml snmpd ssl-cert zabbix-agent
  zabbix-apache-conf zabbix-frontend-php zabbix-server-mysql
  zabbix-sql-scripts
0 upgraded, 63 newly installed, 1 to remove and 0 not upgraded.
Need to get 37.0 MB of archives.
After this operation, 206 MB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libapr1t64 amd64 1.7.2-3.1ubuntu0.1 [108 kB]
Get:2 http://archive.ubuntu.com/ubuntu noble/main amd64 libaprutil1t64 amd64 1.6.3-1.1ubuntu7 [91.9 kB]
Get:3 http://archive.ubuntu.com/ubuntu noble/main amd64 libaprutil1-dbd-sqlite3 amd64 1.6.3-1.1ubuntu7 [11.2 kB]
Get:4 http://archive.ubuntu.com/ubuntu noble/main amd64 libaprutil1-ldap amd64 1.6.3-1.1ubuntu7 [9116 B]
Get:5 http://archive.ubuntu.com/ubuntu noble/main amd64 liblua5.4-0 amd64 5.4.6-3build2 [166 kB]
Get:6 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 apache2-bin amd64 2.4.58-1ubuntu8.8 [1331 kB]
Get:7 https://repo.zabbix.com/zabbix/7.4/stable/ubuntu noble/main amd64 zabbix-server-mysql amd64 1:7.4.2-1+ubuntu24.04 [1824 kB]
Get:8 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 apache2-data all 2.4.58-1ubuntu8.8 [163 kB]
Get:9 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 apache2-utils amd64 2.4.58-1ubuntu8.8 [97.7 kB]
Get:10 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 apache2 amd64 2.4.58-1ubuntu8.8 [90.2 kB]
Get:11 http://archive.ubuntu.com/ubuntu noble/main amd64 libpci3 amd64 1:3.10.0-2build1 [36.5 kB]
Get:12 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libsnmp-base all 5.9.4+dfsg-1.1ubuntu3.1 [206 kB]
Get:13 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libsnmp40t64 amd64 5.9.4+dfsg-1.1ubuntu3.1 [1066 kB]
Get:14 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 snmpd amd64 5.9.4+dfsg-1.1ubuntu3.1 [59.6 kB]
Get:15 http://archive.ubuntu.com/ubuntu noble/main amd64 libcares2 amd64 1.27.0-1.0ubuntu1 [73.7 kB]
Get:16 http://archive.ubuntu.com/ubuntu noble/main amd64 libevent-extra-2.1-7t64 amd64 2.1.12-stable-9ubuntu2 [64.2 kB]
Get:17 http://archive.ubuntu.com/ubuntu noble/main amd64 libevent-pthreads-2.1-7t64 amd64 2.1.12-stable-9ubuntu2 [7982 B]
Get:18 http://archive.ubuntu.com/ubuntu noble/main amd64 libltdl7 amd64 2.4.7-7build1 [40.3 kB]
Get:19 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libodbc2 amd64 2.3.12-1ubuntu0.24.04.1 [158 kB]
Get:20 http://archive.ubuntu.com/ubuntu noble/main amd64 libopenipmi0t64 amd64 2.0.33-1.1build3 [502 kB]
Get:21 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 mysql-client-core-8.0 amd64 8.0.43-0ubuntu0.24.04.1 [2740 kB]
Get:22 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 mysql-client-8.0 amd64 8.0.43-0ubuntu0.24.04.1 [22.4 kB]
Get:23 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 mysql-client all 8.0.43-0ubuntu0.24.04.1 [9412 B]
Get:24 http://archive.ubuntu.com/ubuntu noble/universe amd64 fping amd64 5.1-1 [32.0 kB]
Get:25 http://archive.ubuntu.com/ubuntu noble/main amd64 fonts-dejavu-extra all 2.37-8 [1947 kB]
Get:26 http://archive.ubuntu.com/ubuntu noble/universe amd64 fonts-dejavu all 2.37-8 [3020 B]
Get:27 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libaom3 amd64 3.8.2-2ubuntu0.1 [1941 kB]
Get:28 http://archive.ubuntu.com/ubuntu noble/main amd64 php-common all 2:93ubuntu2 [13.9 kB]
Get:29 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 php8.3-common amd64 8.3.6-0ubuntu0.24.04.5 [740 kB]
Get:30 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 php8.3-opcache amd64 8.3.6-0ubuntu0.24.04.5 [371 kB]
Get:31 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 php8.3-readline amd64 8.3.6-0ubuntu0.24.04.5 [13.5 kB]
Get:32 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 php8.3-cli amd64 8.3.6-0ubuntu0.24.04.5 [1915 kB]
Get:33 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libapache2-mod-php8.3 amd64 8.3.6-0ubuntu0.24.04.5 [1851 kB]
Get:34 http://archive.ubuntu.com/ubuntu noble/main amd64 libapache2-mod-php all 2:8.3+93ubuntu2 [4224 B]
Get:35 http://archive.ubuntu.com/ubuntu noble/main amd64 libde265-0 amd64 1.0.15-1build3 [166 kB]
Get:36 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libheif-plugin-aomdec amd64 1.17.6-1ubuntu4.1 [10.4 kB]
Get:37 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libheif-plugin-libde265 amd64 1.17.6-1ubuntu4.1 [8176 B]
Get:38 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libheif1 amd64 1.17.6-1ubuntu4.1 [275 kB]
Get:39 http://archive.ubuntu.com/ubuntu noble/main amd64 libxpm4 amd64 1:3.5.17-1build2 [36.5 kB]
Get:40 http://archive.ubuntu.com/ubuntu noble/main amd64 libgd3 amd64 2.3.3-9ubuntu5 [128 kB]
Get:41 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libheif-plugin-aomenc amd64 1.17.6-1ubuntu4.1 [14.7 kB]
Get:42 http://archive.ubuntu.com/ubuntu noble/main amd64 libonig5 amd64 6.9.9-1build1 [172 kB]
Get:43 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libxslt1.1 amd64 1.1.39-0exp1ubuntu0.24.04.2 [167 kB]
Get:44 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 php8.3-bcmath amd64 8.3.6-0ubuntu0.24.04.5 [16.6 kB]
Get:45 http://archive.ubuntu.com/ubuntu noble/universe amd64 php-bcmath all 2:8.3+93ubuntu2 [1840 B]
Get:46 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 php8.3-curl amd64 8.3.6-0ubuntu0.24.04.5 [40.3 kB]
Get:47 http://archive.ubuntu.com/ubuntu noble/main amd64 php-curl all 2:8.3+93ubuntu2 [1836 B]
Get:48 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 php8.3-gd amd64 8.3.6-0ubuntu0.24.04.5 [31.2 kB]
Get:49 http://archive.ubuntu.com/ubuntu noble/main amd64 php-gd all 2:8.3+93ubuntu2 [1830 B]
Get:50 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 php8.3-ldap amd64 8.3.6-0ubuntu0.24.04.5 [33.6 kB]
Get:51 http://archive.ubuntu.com/ubuntu noble/main amd64 php-ldap all 2:8.3+93ubuntu2 [1836 B]
Get:52 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 php8.3-mbstring amd64 8.3.6-0ubuntu0.24.04.5 [512 kB]
Get:53 http://archive.ubuntu.com/ubuntu noble/universe amd64 php-mbstring all 2:8.3+93ubuntu2 [1848 B]
Get:54 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 php8.3-mysql amd64 8.3.6-0ubuntu0.24.04.5 [127 kB]
Get:55 http://archive.ubuntu.com/ubuntu noble/main amd64 php-mysql all 2:8.3+93ubuntu2 [1838 B]
Get:56 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 php8.3-xml amd64 8.3.6-0ubuntu0.24.04.5 [126 kB]
Get:57 http://archive.ubuntu.com/ubuntu noble/main amd64 php-xml all 2:8.3+93ubuntu2 [1856 B]
Get:58 http://archive.ubuntu.com/ubuntu noble/main amd64 ssl-cert all 1.1.2ubuntu1 [17.8 kB]
Get:59 http://archive.ubuntu.com/ubuntu noble/universe amd64 libmodbus5 amd64 3.1.10-1ubuntu1 [34.4 kB]
Get:60 https://repo.zabbix.com/zabbix/7.4/stable/ubuntu noble/main amd64 zabbix-agent amd64 1:7.4.2-1+ubuntu24.04 [295 kB]
Get:61 https://repo.zabbix.com/zabbix/7.4/stable/ubuntu noble/main all zabbix-frontend-php all 1:7.4.2-1+ubuntu24.04 [9238 kB]
Get:62 https://repo.zabbix.com/zabbix/7.4/stable/ubuntu noble/main all zabbix-apache-conf all 1:7.4.2-1+ubuntu24.04 [8476 B]
Get:63 https://repo.zabbix.com/zabbix/7.4/stable/ubuntu noble/main all zabbix-sql-scripts all 1:7.4.2-1+ubuntu24.04 [7799 kB]
Fetched 37.0 MB in 7s (5075 kB/s)
Extracting templates from packages: 100%
Preconfiguring packages ...
(Reading database ... 41523 files and directories currently installed.)
Removing mariadb-client-core (1:10.11.13-0ubuntu0.24.04.1) ...
Selecting previously unselected package libapr1t64:amd64.
(Reading database ... 41511 files and directories currently installed.)
Preparing to unpack .../00-libapr1t64_1.7.2-3.1ubuntu0.1_amd64.deb ...
Unpacking libapr1t64:amd64 (1.7.2-3.1ubuntu0.1) ...
Selecting previously unselected package libaprutil1t64:amd64.
Preparing to unpack .../01-libaprutil1t64_1.6.3-1.1ubuntu7_amd64.deb ...
Unpacking libaprutil1t64:amd64 (1.6.3-1.1ubuntu7) ...
Selecting previously unselected package libaprutil1-dbd-sqlite3:amd64.
Preparing to unpack .../02-libaprutil1-dbd-sqlite3_1.6.3-1.1ubuntu7_amd64.deb ...
Unpacking libaprutil1-dbd-sqlite3:amd64 (1.6.3-1.1ubuntu7) ...
Selecting previously unselected package libaprutil1-ldap:amd64.
Preparing to unpack .../03-libaprutil1-ldap_1.6.3-1.1ubuntu7_amd64.deb ...
Unpacking libaprutil1-ldap:amd64 (1.6.3-1.1ubuntu7) ...
Selecting previously unselected package liblua5.4-0:amd64.
Preparing to unpack .../04-liblua5.4-0_5.4.6-3build2_amd64.deb ...
Unpacking liblua5.4-0:amd64 (5.4.6-3build2) ...
Selecting previously unselected package apache2-bin.
Preparing to unpack .../05-apache2-bin_2.4.58-1ubuntu8.8_amd64.deb ...
Unpacking apache2-bin (2.4.58-1ubuntu8.8) ...
Selecting previously unselected package apache2-data.
Preparing to unpack .../06-apache2-data_2.4.58-1ubuntu8.8_all.deb ...
Unpacking apache2-data (2.4.58-1ubuntu8.8) ...
Selecting previously unselected package apache2-utils.
Preparing to unpack .../07-apache2-utils_2.4.58-1ubuntu8.8_amd64.deb ...
Unpacking apache2-utils (2.4.58-1ubuntu8.8) ...
Selecting previously unselected package apache2.
Preparing to unpack .../08-apache2_2.4.58-1ubuntu8.8_amd64.deb ...
Unpacking apache2 (2.4.58-1ubuntu8.8) ...
Selecting previously unselected package libpci3:amd64.
Preparing to unpack .../09-libpci3_1%3a3.10.0-2build1_amd64.deb ...
Unpacking libpci3:amd64 (1:3.10.0-2build1) ...
Selecting previously unselected package libsnmp-base.
Preparing to unpack .../10-libsnmp-base_5.9.4+dfsg-1.1ubuntu3.1_all.deb ...
Unpacking libsnmp-base (5.9.4+dfsg-1.1ubuntu3.1) ...
Selecting previously unselected package libsnmp40t64:amd64.
Preparing to unpack .../11-libsnmp40t64_5.9.4+dfsg-1.1ubuntu3.1_amd64.deb ...
Unpacking libsnmp40t64:amd64 (5.9.4+dfsg-1.1ubuntu3.1) ...
Selecting previously unselected package snmpd.
Preparing to unpack .../12-snmpd_5.9.4+dfsg-1.1ubuntu3.1_amd64.deb ...
Unpacking snmpd (5.9.4+dfsg-1.1ubuntu3.1) ...
Selecting previously unselected package libcares2:amd64.
Preparing to unpack .../13-libcares2_1.27.0-1.0ubuntu1_amd64.deb ...
Unpacking libcares2:amd64 (1.27.0-1.0ubuntu1) ...
Selecting previously unselected package libevent-extra-2.1-7t64:amd64.
Preparing to unpack .../14-libevent-extra-2.1-7t64_2.1.12-stable-9ubuntu2_amd64.deb ...
Unpacking libevent-extra-2.1-7t64:amd64 (2.1.12-stable-9ubuntu2) ...
Selecting previously unselected package libevent-pthreads-2.1-7t64:amd64.
Preparing to unpack .../15-libevent-pthreads-2.1-7t64_2.1.12-stable-9ubuntu2_amd64.deb ...
Unpacking libevent-pthreads-2.1-7t64:amd64 (2.1.12-stable-9ubuntu2) ...
Selecting previously unselected package libltdl7:amd64.
Preparing to unpack .../16-libltdl7_2.4.7-7build1_amd64.deb ...
Unpacking libltdl7:amd64 (2.4.7-7build1) ...
Selecting previously unselected package libodbc2:amd64.
Preparing to unpack .../17-libodbc2_2.3.12-1ubuntu0.24.04.1_amd64.deb ...
Unpacking libodbc2:amd64 (2.3.12-1ubuntu0.24.04.1) ...
Selecting previously unselected package libopenipmi0t64.
Preparing to unpack .../18-libopenipmi0t64_2.0.33-1.1build3_amd64.deb ...
Unpacking libopenipmi0t64 (2.0.33-1.1build3) ...
Selecting previously unselected package mysql-client-core-8.0.
Preparing to unpack .../19-mysql-client-core-8.0_8.0.43-0ubuntu0.24.04.1_amd64.deb ...
Unpacking mysql-client-core-8.0 (8.0.43-0ubuntu0.24.04.1) ...
Selecting previously unselected package mysql-client-8.0.
Preparing to unpack .../20-mysql-client-8.0_8.0.43-0ubuntu0.24.04.1_amd64.deb ...
Unpacking mysql-client-8.0 (8.0.43-0ubuntu0.24.04.1) ...
Selecting previously unselected package mysql-client.
Preparing to unpack .../21-mysql-client_8.0.43-0ubuntu0.24.04.1_all.deb ...
Unpacking mysql-client (8.0.43-0ubuntu0.24.04.1) ...
Selecting previously unselected package fping.
Preparing to unpack .../22-fping_5.1-1_amd64.deb ...
Unpacking fping (5.1-1) ...
Selecting previously unselected package zabbix-server-mysql.
Preparing to unpack .../23-zabbix-server-mysql_1%3a7.4.2-1+ubuntu24.04_amd64.deb ...
Unpacking zabbix-server-mysql (1:7.4.2-1+ubuntu24.04) ...
Selecting previously unselected package fonts-dejavu-extra.
Preparing to unpack .../24-fonts-dejavu-extra_2.37-8_all.deb ...
Unpacking fonts-dejavu-extra (2.37-8) ...
Selecting previously unselected package fonts-dejavu.
Preparing to unpack .../25-fonts-dejavu_2.37-8_all.deb ...
Unpacking fonts-dejavu (2.37-8) ...
Selecting previously unselected package libaom3:amd64.
Preparing to unpack .../26-libaom3_3.8.2-2ubuntu0.1_amd64.deb ...
Unpacking libaom3:amd64 (3.8.2-2ubuntu0.1) ...
Selecting previously unselected package php-common.
Preparing to unpack .../27-php-common_2%3a93ubuntu2_all.deb ...
Unpacking php-common (2:93ubuntu2) ...
Selecting previously unselected package php8.3-common.
Preparing to unpack .../28-php8.3-common_8.3.6-0ubuntu0.24.04.5_amd64.deb ...
Unpacking php8.3-common (8.3.6-0ubuntu0.24.04.5) ...
Selecting previously unselected package php8.3-opcache.
Preparing to unpack .../29-php8.3-opcache_8.3.6-0ubuntu0.24.04.5_amd64.deb ...
Unpacking php8.3-opcache (8.3.6-0ubuntu0.24.04.5) ...
Selecting previously unselected package php8.3-readline.
Preparing to unpack .../30-php8.3-readline_8.3.6-0ubuntu0.24.04.5_amd64.deb ...
Unpacking php8.3-readline (8.3.6-0ubuntu0.24.04.5) ...
Selecting previously unselected package php8.3-cli.
Preparing to unpack .../31-php8.3-cli_8.3.6-0ubuntu0.24.04.5_amd64.deb ...
Unpacking php8.3-cli (8.3.6-0ubuntu0.24.04.5) ...
Selecting previously unselected package libapache2-mod-php8.3.
Preparing to unpack .../32-libapache2-mod-php8.3_8.3.6-0ubuntu0.24.04.5_amd64.deb ...
Unpacking libapache2-mod-php8.3 (8.3.6-0ubuntu0.24.04.5) ...
Selecting previously unselected package libapache2-mod-php.
Preparing to unpack .../33-libapache2-mod-php_2%3a8.3+93ubuntu2_all.deb ...
Unpacking libapache2-mod-php (2:8.3+93ubuntu2) ...
Selecting previously unselected package libde265-0:amd64.
Preparing to unpack .../34-libde265-0_1.0.15-1build3_amd64.deb ...
Unpacking libde265-0:amd64 (1.0.15-1build3) ...
Selecting previously unselected package libheif-plugin-aomdec:amd64.
Preparing to unpack .../35-libheif-plugin-aomdec_1.17.6-1ubuntu4.1_amd64.deb ...
Unpacking libheif-plugin-aomdec:amd64 (1.17.6-1ubuntu4.1) ...
Selecting previously unselected package libheif-plugin-libde265:amd64.
Preparing to unpack .../36-libheif-plugin-libde265_1.17.6-1ubuntu4.1_amd64.deb ...
Unpacking libheif-plugin-libde265:amd64 (1.17.6-1ubuntu4.1) ...
Selecting previously unselected package libheif1:amd64.
Preparing to unpack .../37-libheif1_1.17.6-1ubuntu4.1_amd64.deb ...
Unpacking libheif1:amd64 (1.17.6-1ubuntu4.1) ...
Selecting previously unselected package libxpm4:amd64.
Preparing to unpack .../38-libxpm4_1%3a3.5.17-1build2_amd64.deb ...
Unpacking libxpm4:amd64 (1:3.5.17-1build2) ...
Selecting previously unselected package libgd3:amd64.
Preparing to unpack .../39-libgd3_2.3.3-9ubuntu5_amd64.deb ...
Unpacking libgd3:amd64 (2.3.3-9ubuntu5) ...
Selecting previously unselected package libheif-plugin-aomenc:amd64.
Preparing to unpack .../40-libheif-plugin-aomenc_1.17.6-1ubuntu4.1_amd64.deb ...
Unpacking libheif-plugin-aomenc:amd64 (1.17.6-1ubuntu4.1) ...
Selecting previously unselected package libonig5:amd64.
Preparing to unpack .../41-libonig5_6.9.9-1build1_amd64.deb ...
Unpacking libonig5:amd64 (6.9.9-1build1) ...
Selecting previously unselected package libxslt1.1:amd64.
Preparing to unpack .../42-libxslt1.1_1.1.39-0exp1ubuntu0.24.04.2_amd64.deb ...
Unpacking libxslt1.1:amd64 (1.1.39-0exp1ubuntu0.24.04.2) ...
Selecting previously unselected package php8.3-bcmath.
Preparing to unpack .../43-php8.3-bcmath_8.3.6-0ubuntu0.24.04.5_amd64.deb ...
Unpacking php8.3-bcmath (8.3.6-0ubuntu0.24.04.5) ...
Selecting previously unselected package php-bcmath.
Preparing to unpack .../44-php-bcmath_2%3a8.3+93ubuntu2_all.deb ...
Unpacking php-bcmath (2:8.3+93ubuntu2) ...
Selecting previously unselected package php8.3-curl.
Preparing to unpack .../45-php8.3-curl_8.3.6-0ubuntu0.24.04.5_amd64.deb ...
Unpacking php8.3-curl (8.3.6-0ubuntu0.24.04.5) ...
Selecting previously unselected package php-curl.
Preparing to unpack .../46-php-curl_2%3a8.3+93ubuntu2_all.deb ...
Unpacking php-curl (2:8.3+93ubuntu2) ...
Selecting previously unselected package php8.3-gd.
Preparing to unpack .../47-php8.3-gd_8.3.6-0ubuntu0.24.04.5_amd64.deb ...
Unpacking php8.3-gd (8.3.6-0ubuntu0.24.04.5) ...
Selecting previously unselected package php-gd.
Preparing to unpack .../48-php-gd_2%3a8.3+93ubuntu2_all.deb ...
Unpacking php-gd (2:8.3+93ubuntu2) ...
Selecting previously unselected package php8.3-ldap.
Preparing to unpack .../49-php8.3-ldap_8.3.6-0ubuntu0.24.04.5_amd64.deb ...
Unpacking php8.3-ldap (8.3.6-0ubuntu0.24.04.5) ...
Selecting previously unselected package php-ldap.
Preparing to unpack .../50-php-ldap_2%3a8.3+93ubuntu2_all.deb ...
Unpacking php-ldap (2:8.3+93ubuntu2) ...
Selecting previously unselected package php8.3-mbstring.
Preparing to unpack .../51-php8.3-mbstring_8.3.6-0ubuntu0.24.04.5_amd64.deb ...
Unpacking php8.3-mbstring (8.3.6-0ubuntu0.24.04.5) ...
Selecting previously unselected package php-mbstring.
Preparing to unpack .../52-php-mbstring_2%3a8.3+93ubuntu2_all.deb ...
Unpacking php-mbstring (2:8.3+93ubuntu2) ...
Selecting previously unselected package php8.3-mysql.
Preparing to unpack .../53-php8.3-mysql_8.3.6-0ubuntu0.24.04.5_amd64.deb ...
Unpacking php8.3-mysql (8.3.6-0ubuntu0.24.04.5) ...
Selecting previously unselected package php-mysql.
Preparing to unpack .../54-php-mysql_2%3a8.3+93ubuntu2_all.deb ...
Unpacking php-mysql (2:8.3+93ubuntu2) ...
Selecting previously unselected package php8.3-xml.
Preparing to unpack .../55-php8.3-xml_8.3.6-0ubuntu0.24.04.5_amd64.deb ...
Unpacking php8.3-xml (8.3.6-0ubuntu0.24.04.5) ...
Selecting previously unselected package php-xml.
Preparing to unpack .../56-php-xml_2%3a8.3+93ubuntu2_all.deb ...
Unpacking php-xml (2:8.3+93ubuntu2) ...
Selecting previously unselected package ssl-cert.
Preparing to unpack .../57-ssl-cert_1.1.2ubuntu1_all.deb ...
Unpacking ssl-cert (1.1.2ubuntu1) ...
Selecting previously unselected package libmodbus5:amd64.
Preparing to unpack .../58-libmodbus5_3.1.10-1ubuntu1_amd64.deb ...
Unpacking libmodbus5:amd64 (3.1.10-1ubuntu1) ...
Selecting previously unselected package zabbix-agent.
Preparing to unpack .../59-zabbix-agent_1%3a7.4.2-1+ubuntu24.04_amd64.deb ...
Unpacking zabbix-agent (1:7.4.2-1+ubuntu24.04) ...
Selecting previously unselected package zabbix-frontend-php.
Preparing to unpack .../60-zabbix-frontend-php_1%3a7.4.2-1+ubuntu24.04_all.deb ...
Unpacking zabbix-frontend-php (1:7.4.2-1+ubuntu24.04) ...
Selecting previously unselected package zabbix-apache-conf.
Preparing to unpack .../61-zabbix-apache-conf_1%3a7.4.2-1+ubuntu24.04_all.deb ...
Unpacking zabbix-apache-conf (1:7.4.2-1+ubuntu24.04) ...
Selecting previously unselected package zabbix-sql-scripts.
Preparing to unpack .../62-zabbix-sql-scripts_1%3a7.4.2-1+ubuntu24.04_all.deb ...
Unpacking zabbix-sql-scripts (1:7.4.2-1+ubuntu24.04) ...
Setting up php-common (2:93ubuntu2) ...
Created symlink /etc/systemd/system/timers.target.wants/phpsessionclean.timer → /usr/lib/systemd/system/phpsessionclean.timer.
Setting up libaom3:amd64 (3.8.2-2ubuntu0.1) ...
Setting up mysql-client-core-8.0 (8.0.43-0ubuntu0.24.04.1) ...
Setting up libmodbus5:amd64 (3.1.10-1ubuntu1) ...
Setting up libxpm4:amd64 (1:3.5.17-1build2) ...
Setting up zabbix-sql-scripts (1:7.4.2-1+ubuntu24.04) ...
Setting up libevent-pthreads-2.1-7t64:amd64 (2.1.12-stable-9ubuntu2) ...
Setting up libsnmp-base (5.9.4+dfsg-1.1ubuntu3.1) ...
Setting up libopenipmi0t64 (2.0.33-1.1build3) ...
Setting up php8.3-common (8.3.6-0ubuntu0.24.04.5) ...

Creating config file /etc/php/8.3/mods-available/calendar.ini with new version

Creating config file /etc/php/8.3/mods-available/ctype.ini with new version

Creating config file /etc/php/8.3/mods-available/exif.ini with new version

Creating config file /etc/php/8.3/mods-available/fileinfo.ini with new version

Creating config file /etc/php/8.3/mods-available/ffi.ini with new version

Creating config file /etc/php/8.3/mods-available/ftp.ini with new version

Creating config file /etc/php/8.3/mods-available/gettext.ini with new version

Creating config file /etc/php/8.3/mods-available/iconv.ini with new version

Creating config file /etc/php/8.3/mods-available/pdo.ini with new version

Creating config file /etc/php/8.3/mods-available/phar.ini with new version

Creating config file /etc/php/8.3/mods-available/posix.ini with new version

Creating config file /etc/php/8.3/mods-available/shmop.ini with new version

Creating config file /etc/php/8.3/mods-available/sockets.ini with new version

Creating config file /etc/php/8.3/mods-available/sysvmsg.ini with new version

Creating config file /etc/php/8.3/mods-available/sysvsem.ini with new version

Creating config file /etc/php/8.3/mods-available/sysvshm.ini with new version

Creating config file /etc/php/8.3/mods-available/tokenizer.ini with new version
Setting up php8.3-mysql (8.3.6-0ubuntu0.24.04.5) ...

Creating config file /etc/php/8.3/mods-available/mysqlnd.ini with new version

Creating config file /etc/php/8.3/mods-available/mysqli.ini with new version

Creating config file /etc/php/8.3/mods-available/pdo_mysql.ini with new version
Setting up php8.3-readline (8.3.6-0ubuntu0.24.04.5) ...

Creating config file /etc/php/8.3/mods-available/readline.ini with new version
Setting up ssl-cert (1.1.2ubuntu1) ...
Created symlink /etc/systemd/system/multi-user.target.wants/ssl-cert.service → /usr/lib/systemd/system/ssl-cert.service.
Setting up libcares2:amd64 (1.27.0-1.0ubuntu1) ...
Setting up libltdl7:amd64 (2.4.7-7build1) ...
Setting up libevent-extra-2.1-7t64:amd64 (2.1.12-stable-9ubuntu2) ...
Setting up libodbc2:amd64 (2.3.12-1ubuntu0.24.04.1) ...
Setting up libpci3:amd64 (1:3.10.0-2build1) ...
Setting up php8.3-ldap (8.3.6-0ubuntu0.24.04.5) ...

Creating config file /etc/php/8.3/mods-available/ldap.ini with new version
Setting up fonts-dejavu-extra (2.37-8) ...
Setting up php8.3-bcmath (8.3.6-0ubuntu0.24.04.5) ...

Creating config file /etc/php/8.3/mods-available/bcmath.ini with new version
Setting up libapr1t64:amd64 (1.7.2-3.1ubuntu0.1) ...
Setting up libxslt1.1:amd64 (1.1.39-0exp1ubuntu0.24.04.2) ...
Setting up mysql-client-8.0 (8.0.43-0ubuntu0.24.04.1) ...
Setting up liblua5.4-0:amd64 (5.4.6-3build2) ...
Setting up php8.3-xml (8.3.6-0ubuntu0.24.04.5) ...

Creating config file /etc/php/8.3/mods-available/dom.ini with new version

Creating config file /etc/php/8.3/mods-available/simplexml.ini with new version

Creating config file /etc/php/8.3/mods-available/xml.ini with new version

Creating config file /etc/php/8.3/mods-available/xmlreader.ini with new version

Creating config file /etc/php/8.3/mods-available/xmlwriter.ini with new version

Creating config file /etc/php/8.3/mods-available/xsl.ini with new version
Setting up apache2-data (2.4.58-1ubuntu8.8) ...
Setting up zabbix-agent (1:7.4.2-1+ubuntu24.04) ...
Created symlink /etc/systemd/system/multi-user.target.wants/zabbix-agent.service → /usr/lib/systemd/system/zabbix-agent.service.
Setting up php8.3-opcache (8.3.6-0ubuntu0.24.04.5) ...

Creating config file /etc/php/8.3/mods-available/opcache.ini with new version
Setting up libde265-0:amd64 (1.0.15-1build3) ...
Setting up fping (5.1-1) ...
Setting up libonig5:amd64 (6.9.9-1build1) ...
Setting up php-xml (2:8.3+93ubuntu2) ...
Setting up libaprutil1t64:amd64 (1.6.3-1.1ubuntu7) ...
Setting up fonts-dejavu (2.37-8) ...
Setting up mysql-client (8.0.43-0ubuntu0.24.04.1) ...
Setting up libsnmp40t64:amd64 (5.9.4+dfsg-1.1ubuntu3.1) ...
Setting up php-mysql (2:8.3+93ubuntu2) ...
Setting up zabbix-server-mysql (1:7.4.2-1+ubuntu24.04) ...
Setting up php-bcmath (2:8.3+93ubuntu2) ...
Setting up php8.3-curl (8.3.6-0ubuntu0.24.04.5) ...

Creating config file /etc/php/8.3/mods-available/curl.ini with new version
Setting up libaprutil1-ldap:amd64 (1.6.3-1.1ubuntu7) ...
Setting up php8.3-cli (8.3.6-0ubuntu0.24.04.5) ...
update-alternatives: using /usr/bin/php8.3 to provide /usr/bin/php (php) in auto mode
update-alternatives: using /usr/bin/phar8.3 to provide /usr/bin/phar (phar) in auto mode
update-alternatives: using /usr/bin/phar.phar8.3 to provide /usr/bin/phar.phar (phar.phar) in auto mode

Creating config file /etc/php/8.3/cli/php.ini with new version
Setting up snmpd (5.9.4+dfsg-1.1ubuntu3.1) ...
warn: The home directory `/var/lib/snmp' already exists.  Not touching this directory.
warn: Warning: The home directory `/var/lib/snmp' does not belong to the user you are currently creating.
Created symlink /etc/systemd/system/multi-user.target.wants/snmpd.service → /usr/lib/systemd/system/snmpd.service.
Setting up libaprutil1-dbd-sqlite3:amd64 (1.6.3-1.1ubuntu7) ...
Setting up php-ldap (2:8.3+93ubuntu2) ...
Setting up php8.3-mbstring (8.3.6-0ubuntu0.24.04.5) ...

Creating config file /etc/php/8.3/mods-available/mbstring.ini with new version
Setting up apache2-utils (2.4.58-1ubuntu8.8) ...
Setting up php-curl (2:8.3+93ubuntu2) ...
Setting up apache2-bin (2.4.58-1ubuntu8.8) ...
Setting up php-mbstring (2:8.3+93ubuntu2) ...
Setting up libapache2-mod-php8.3 (8.3.6-0ubuntu0.24.04.5) ...
Package apache2 is not configured yet. Will defer actions by package libapache2-mod-php8.3.

Creating config file /etc/php/8.3/apache2/php.ini with new version
No module matches
Setting up apache2 (2.4.58-1ubuntu8.8) ...
Enabling module mpm_event.
Enabling module authz_core.
Enabling module authz_host.
Enabling module authn_core.
Enabling module auth_basic.
Enabling module access_compat.
Enabling module authn_file.
Enabling module authz_user.
Enabling module alias.
Enabling module dir.
Enabling module autoindex.
Enabling module env.
Enabling module mime.
Enabling module negotiation.
Enabling module setenvif.
Enabling module filter.
Enabling module deflate.
Enabling module status.
Enabling module reqtimeout.
Enabling conf charset.
Enabling conf localized-error-pages.
Enabling conf other-vhosts-access-log.
Enabling conf security.
Enabling conf serve-cgi-bin.
Enabling site 000-default.
info: Switch to mpm prefork for package libapache2-mod-php8.3
Module mpm_event disabled.
Enabling module mpm_prefork.
info: Executing deferred 'a2enmod php8.3' for package libapache2-mod-php8.3
Enabling module php8.3.
Created symlink /etc/systemd/system/multi-user.target.wants/apache2.service → /usr/lib/systemd/system/apache2.service.
Created symlink /etc/systemd/system/multi-user.target.wants/apache-htcacheclean.service → /usr/lib/systemd/system/apache-htcacheclean.service.
Setting up libapache2-mod-php (2:8.3+93ubuntu2) ...
Setting up libheif-plugin-aomdec:amd64 (1.17.6-1ubuntu4.1) ...
Setting up libheif-plugin-libde265:amd64 (1.17.6-1ubuntu4.1) ...
Setting up libheif1:amd64 (1.17.6-1ubuntu4.1) ...
Setting up libgd3:amd64 (2.3.3-9ubuntu5) ...
Setting up php8.3-gd (8.3.6-0ubuntu0.24.04.5) ...

Creating config file /etc/php/8.3/mods-available/gd.ini with new version
Setting up libheif-plugin-aomenc:amd64 (1.17.6-1ubuntu4.1) ...
Setting up zabbix-frontend-php (1:7.4.2-1+ubuntu24.04) ...
update-alternatives: using /usr/share/fonts/truetype/dejavu/DejaVuSans.ttf to provide /usr/share/zabbix/ui/assets/fonts/graphfont.ttf (zabbix-frontend-font) in auto mode
Setting up php-gd (2:8.3+93ubuntu2) ...
Setting up zabbix-apache-conf (1:7.4.2-1+ubuntu24.04) ...
Enabling conf zabbix.
To activate the new configuration, you need to run:
  systemctl reload apache2
Processing triggers for fontconfig (2.15.0-1.1ubuntu2) ...
Processing triggers for libc-bin (2.39-0ubuntu8.5) ...
Processing triggers for man-db (2.12.0-4build2) ...
Processing triggers for php8.3-cli (8.3.6-0ubuntu0.24.04.5) ...
Processing triggers for libapache2-mod-php8.3 (8.3.6-0ubuntu0.24.04.5) ...
root@Dell5400:/home/devne# apt install mysql-server
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  galera-4 libconfig-inifiles-perl libdbd-mysql-perl
  libdbi-perl libmariadb3 libsnappy1v5 libterm-readkey-perl
  liburing2 mariadb-common pv socat
Use 'apt autoremove' to remove them.
The following additional packages will be installed:
  libaio1t64 libmecab2 libprotobuf-lite32t64 mecab-ipadic
  mecab-ipadic-utf8 mecab-utils mysql-server-8.0
  mysql-server-core-8.0
Suggested packages:
  mailx tinyca
The following packages will be REMOVED:
  mariadb-server-core
The following NEW packages will be installed:
  libaio1t64 libmecab2 libprotobuf-lite32t64 mecab-ipadic
  mecab-ipadic-utf8 mecab-utils mysql-server mysql-server-8.0
  mysql-server-core-8.0
0 upgraded, 9 newly installed, 1 to remove and 0 not upgraded.
Need to get 26.2 MB of archives.
After this operation, 131 MB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libaio1t64 amd64 0.3.113-6build1.1 [7210 B]
Get:2 http://archive.ubuntu.com/ubuntu noble/main amd64 libmecab2 amd64 0.996-14ubuntu4 [201 kB]
Get:3 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 libprotobuf-lite32t64 amd64 3.21.12-8.2ubuntu0.2 [238 kB]
Get:4 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 mysql-server-core-8.0 amd64 8.0.43-0ubuntu0.24.04.1 [17.5 MB]
Get:5 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 mysql-server-8.0 amd64 8.0.43-0ubuntu0.24.04.1 [1439 kB]
Get:6 http://archive.ubuntu.com/ubuntu noble/main amd64 mecab-utils amd64 0.996-14ubuntu4 [4804 B]
Get:7 http://archive.ubuntu.com/ubuntu noble/main amd64 mecab-ipadic all 2.7.0-20070801+main-3 [6718 kB]
Get:8 http://archive.ubuntu.com/ubuntu noble/main amd64 mecab-ipadic-utf8 all 2.7.0-20070801+main-3 [4384 B]
Get:9 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 mysql-server all 8.0.43-0ubuntu0.24.04.1 [9520 B]
Fetched 26.2 MB in 2s (12.3 MB/s)
Preconfiguring packages ...
(Reading database ... 45428 files and directories currently installed.)
Removing mariadb-server-core (1:10.11.13-0ubuntu0.24.04.1) ...
Selecting previously unselected package libaio1t64:amd64.
(Reading database ... 45318 files and directories currently installed.)
Preparing to unpack .../0-libaio1t64_0.3.113-6build1.1_amd64.deb ...
Unpacking libaio1t64:amd64 (0.3.113-6build1.1) ...
Selecting previously unselected package libmecab2:amd64.
Preparing to unpack .../1-libmecab2_0.996-14ubuntu4_amd64.deb ...
Unpacking libmecab2:amd64 (0.996-14ubuntu4) ...
Selecting previously unselected package libprotobuf-lite32t64:amd64.
Preparing to unpack .../2-libprotobuf-lite32t64_3.21.12-8.2ubuntu0.2_amd64.deb ...
Unpacking libprotobuf-lite32t64:amd64 (3.21.12-8.2ubuntu0.2) ...
Selecting previously unselected package mysql-server-core-8.0.
Preparing to unpack .../3-mysql-server-core-8.0_8.0.43-0ubuntu0.24.04.1_amd64.deb ...
Unpacking mysql-server-core-8.0 (8.0.43-0ubuntu0.24.04.1) ...
Selecting previously unselected package mysql-server-8.0.
Preparing to unpack .../4-mysql-server-8.0_8.0.43-0ubuntu0.24.04.1_amd64.deb ...
Downgrade from (at least) 10.11 to 5.7 is not possible.
MySQL has been frozen to prevent damage to your system. Please see /etc/mysql/FROZEN for help.
Unpacking mysql-server-8.0 (8.0.43-0ubuntu0.24.04.1) ...
Selecting previously unselected package mecab-utils.
Preparing to unpack .../5-mecab-utils_0.996-14ubuntu4_amd64.deb ...
Unpacking mecab-utils (0.996-14ubuntu4) ...
Selecting previously unselected package mecab-ipadic.
Preparing to unpack .../6-mecab-ipadic_2.7.0-20070801+main-3_all.deb ...
Unpacking mecab-ipadic (2.7.0-20070801+main-3) ...
Selecting previously unselected package mecab-ipadic-utf8.
Preparing to unpack .../7-mecab-ipadic-utf8_2.7.0-20070801+main-3_all.deb ...
Unpacking mecab-ipadic-utf8 (2.7.0-20070801+main-3) ...
Selecting previously unselected package mysql-server.
Preparing to unpack .../8-mysql-server_8.0.43-0ubuntu0.24.04.1_all.deb ...
Unpacking mysql-server (8.0.43-0ubuntu0.24.04.1) ...
Setting up libprotobuf-lite32t64:amd64 (3.21.12-8.2ubuntu0.2) ...
Setting up libmecab2:amd64 (0.996-14ubuntu4) ...
Setting up mecab-utils (0.996-14ubuntu4) ...
Setting up libaio1t64:amd64 (0.3.113-6build1.1) ...
Setting up mecab-ipadic (2.7.0-20070801+main-3) ...
Compiling IPA dictionary for Mecab.  This takes long time...
reading /usr/share/mecab/dic/ipadic/unk.def ... 40
emitting double-array:   9% |###                                emitting double-array:  18% |#######                            emitting double-array:  27% |###########                        emitting double-array:  36% |###############                    emitting double-array:  45% |###################                emitting double-array:  54% |#######################            emitting double-array:  63% |###########################        emitting double-array:  72% |###############################    emitting double-array:  81% |###################################emitting double-array:  90% |###################################emitting double-array: 100% |###########################################|
/usr/share/mecab/dic/ipadic/model.def is not found. skipped.
reading /usr/share/mecab/dic/ipadic/Noun.csv ... 60477
reading /usr/share/mecab/dic/ipadic/Noun.verbal.csv ... 12146
reading /usr/share/mecab/dic/ipadic/Auxil.csv ... 199
reading /usr/share/mecab/dic/ipadic/Noun.demonst.csv ... 120
reading /usr/share/mecab/dic/ipadic/Noun.number.csv ... 42
reading /usr/share/mecab/dic/ipadic/Noun.place.csv ... 72999
reading /usr/share/mecab/dic/ipadic/Filler.csv ... 19
reading /usr/share/mecab/dic/ipadic/Noun.proper.csv ... 27328
reading /usr/share/mecab/dic/ipadic/Noun.name.csv ... 34202
reading /usr/share/mecab/dic/ipadic/Others.csv ... 2
reading /usr/share/mecab/dic/ipadic/Verb.csv ... 130750
reading /usr/share/mecab/dic/ipadic/Postp.csv ... 146
reading /usr/share/mecab/dic/ipadic/Conjunction.csv ... 171
reading /usr/share/mecab/dic/ipadic/Prefix.csv ... 221
reading /usr/share/mecab/dic/ipadic/Postp-col.csv ... 91
reading /usr/share/mecab/dic/ipadic/Noun.org.csv ... 16668
reading /usr/share/mecab/dic/ipadic/Noun.adverbal.csv ... 795
reading /usr/share/mecab/dic/ipadic/Adj.csv ... 27210
reading /usr/share/mecab/dic/ipadic/Adnominal.csv ... 135
reading /usr/share/mecab/dic/ipadic/Suffix.csv ... 1393
reading /usr/share/mecab/dic/ipadic/Noun.adjv.csv ... 3328
reading /usr/share/mecab/dic/ipadic/Noun.others.csv ... 151
reading /usr/share/mecab/dic/ipadic/Adverb.csv ... 3032
reading /usr/share/mecab/dic/ipadic/Symbol.csv ... 208
reading /usr/share/mecab/dic/ipadic/Interjection.csv ... 252
reading /usr/share/mecab/dic/ipadic/Noun.nai.csv ... 42
emitting double-array:   0% |                                   emitting double-array:   1% |                                   emitting double-array:   2% |                                   emitting double-array:   3% |#                                  emitting double-array:   4% |#                                  emitting double-array:   5% |##                                 emitting double-array:   6% |##                                 emitting double-array:   7% |###                                emitting double-array:   8% |###                                emitting double-array:   9% |###                                emitting double-array:  10% |####                               emitting double-array:  11% |####                               emitting double-array:  12% |#####                              emitting double-array:  13% |#####                              emitting double-array:  14% |######                             emitting double-array:  15% |######                             emitting double-array:  16% |######                             emitting double-array:  17% |#######                            emitting double-array:  18% |#######                            emitting double-array:  19% |########                           emitting double-array:  20% |########                           emitting double-array:  21% |#########                          emitting double-array:  22% |#########                          emitting double-array:  23% |#########                          emitting double-array:  24% |##########                         emitting double-array:  25% |##########                         emitting double-array:  26% |###########                        emitting double-array:  27% |###########                        emitting double-array:  28% |############                       emitting double-array:  29% |############                       emitting double-array:  30% |############                       emitting double-array:  31% |#############                      emitting double-array:  32% |#############                      emitting double-array:  33% |##############                     emitting double-array:  34% |##############                     emitting double-array:  35% |###############                    emitting double-array:  36% |###############                    emitting double-array:  37% |###############                    emitting double-array:  38% |################                   emitting double-array:  39% |################                   emitting double-array:  40% |#################                  emitting double-array:  41% |#################                  emitting double-array:  42% |##################                 emitting double-array:  43% |##################                 emitting double-array:  44% |##################                 emitting double-array:  45% |###################                emitting double-array:  46% |###################                emitting double-array:  47% |####################               emitting double-array:  48% |####################               emitting double-array:  49% |#####################              emitting double-array:  50% |#####################              emitting double-array:  51% |#####################              emitting double-array:  52% |######################             emitting double-array:  53% |######################             emitting double-array:  54% |#######################            emitting double-array:  55% |#######################            emitting double-array:  56% |########################           emitting double-array:  57% |########################           emitting double-array:  58% |########################           emitting double-array:  59% |#########################          emitting double-array:  60% |#########################          emitting double-array:  61% |##########################         emitting double-array:  62% |##########################         emitting double-array:  63% |###########################        emitting double-array:  64% |###########################        emitting double-array:  65% |###########################        emitting double-array:  66% |############################       emitting double-array:  67% |############################       emitting double-array:  68% |#############################      emitting double-array:  69% |#############################      emitting double-array:  70% |##############################     emitting double-array:  71% |##############################     emitting double-array:  72% |##############################     emitting double-array:  73% |###############################    emitting double-array:  74% |###############################    emitting double-array:  75% |################################   emitting double-array:  76% |################################   emitting double-array:  77% |#################################  emitting double-array:  78% |#################################  emitting double-array:  79% |#################################  emitting double-array:  80% |################################## emitting double-array:  81% |################################## emitting double-array:  82% |###################################emitting double-array:  83% |###################################emitting double-array:  84% |###################################emitting double-array:  85% |###################################emitting double-array:  86% |###################################emitting double-array:  87% |###################################emitting double-array:  88% |###################################emitting double-array:  89% |###################################emitting double-array:  90% |###################################emitting double-array:  91% |###################################emitting double-array:  92% |###################################emitting double-array:  93% |###################################emitting double-array:  94% |###################################emitting double-array:  95% |###################################emitting double-array:  96% |###################################emitting double-array:  97% |###################################emitting double-array:  98% |###################################emitting double-array:  99% |###################################emitting double-array: 100% |###########################################|
reading /usr/share/mecab/dic/ipadic/matrix.def ... 1316x1316
emitting matrix      :   0% |                                   emitting matrix      :   1% |                                   emitting matrix      :   2% |                                   emitting matrix      :   3% |#                                  emitting matrix      :   4% |#                                  emitting matrix      :   5% |##                                 emitting matrix      :   6% |##                                 emitting matrix      :   7% |###                                emitting matrix      :   8% |###                                emitting matrix      :   9% |###                                emitting matrix      :  10% |####                               emitting matrix      :  11% |####                               emitting matrix      :  12% |#####                              emitting matrix      :  13% |#####                              emitting matrix      :  14% |######                             emitting matrix      :  15% |######                             emitting matrix      :  16% |######                             emitting matrix      :  17% |#######                            emitting matrix      :  18% |#######                            emitting matrix      :  19% |########                           emitting matrix      :  20% |########                           emitting matrix      :  21% |#########                          emitting matrix      :  22% |#########                          emitting matrix      :  23% |#########                          emitting matrix      :  24% |##########                         emitting matrix      :  25% |##########                         emitting matrix      :  26% |###########                        emitting matrix      :  27% |###########                        emitting matrix      :  28% |############                       emitting matrix      :  29% |############                       emitting matrix      :  30% |############                       emitting matrix      :  31% |#############                      emitting matrix      :  32% |#############                      emitting matrix      :  33% |##############                     emitting matrix      :  34% |##############                     emitting matrix      :  35% |###############                    emitting matrix      :  36% |###############                    emitting matrix      :  37% |###############                    emitting matrix      :  38% |################                   emitting matrix      :  39% |################                   emitting matrix      :  40% |#################                  emitting matrix      :  41% |#################                  emitting matrix      :  42% |##################                 emitting matrix      :  43% |##################                 emitting matrix      :  44% |##################                 emitting matrix      :  45% |###################                emitting matrix      :  46% |###################                emitting matrix      :  47% |####################               emitting matrix      :  48% |####################               emitting matrix      :  49% |#####################              emitting matrix      :  50% |#####################              emitting matrix      :  51% |#####################              emitting matrix      :  52% |######################             emitting matrix      :  53% |######################             emitting matrix      :  54% |#######################            emitting matrix      :  55% |#######################            emitting matrix      :  56% |########################           emitting matrix      :  57% |########################           emitting matrix      :  58% |########################           emitting matrix      :  59% |#########################          emitting matrix      :  60% |#########################          emitting matrix      :  61% |##########################         emitting matrix      :  62% |##########################         emitting matrix      :  63% |###########################        emitting matrix      :  64% |###########################        emitting matrix      :  65% |###########################        emitting matrix      :  66% |############################       emitting matrix      :  67% |############################       emitting matrix      :  68% |#############################      emitting matrix      :  69% |#############################      emitting matrix      :  70% |##############################     emitting matrix      :  71% |##############################     emitting matrix      :  72% |##############################     emitting matrix      :  73% |###############################    emitting matrix      :  74% |###############################    emitting matrix      :  75% |################################   emitting matrix      :  76% |################################   emitting matrix      :  77% |#################################  emitting matrix      :  78% |#################################  emitting matrix      :  79% |#################################  emitting matrix      :  80% |################################## emitting matrix      :  81% |################################## emitting matrix      :  82% |###################################emitting matrix      :  83% |###################################emitting matrix      :  84% |###################################emitting matrix      :  85% |###################################emitting matrix      :  86% |###################################emitting matrix      :  87% |###################################emitting matrix      :  88% |###################################emitting matrix      :  89% |###################################emitting matrix      :  90% |###################################emitting matrix      :  91% |###################################emitting matrix      :  92% |###################################emitting matrix      :  93% |###################################emitting matrix      :  94% |###################################emitting matrix      :  95% |###################################emitting matrix      :  96% |###################################emitting matrix      :  97% |###################################emitting matrix      :  98% |###################################emitting matrix      :  99% |###################################emitting matrix      : 100% |###########################################|

done!
update-alternatives: using /var/lib/mecab/dic/ipadic to provide /var/lib/mecab/dic/debian (mecab-dictionary) in auto mode
Setting up mysql-server-core-8.0 (8.0.43-0ubuntu0.24.04.1) ...
Setting up mecab-ipadic-utf8 (2.7.0-20070801+main-3) ...
Compiling IPA dictionary for Mecab.  This takes long time...
reading /usr/share/mecab/dic/ipadic/unk.def ... 40
emitting double-array:   9% |###                                emitting double-array:  18% |#######                            emitting double-array:  27% |###########                        emitting double-array:  36% |###############                    emitting double-array:  45% |###################                emitting double-array:  54% |#######################            emitting double-array:  63% |###########################        emitting double-array:  72% |###############################    emitting double-array:  81% |###################################emitting double-array:  90% |###################################emitting double-array: 100% |###########################################|
/usr/share/mecab/dic/ipadic/model.def is not found. skipped.
reading /usr/share/mecab/dic/ipadic/Noun.csv ... 60477
reading /usr/share/mecab/dic/ipadic/Noun.verbal.csv ... 12146
reading /usr/share/mecab/dic/ipadic/Auxil.csv ... 199
reading /usr/share/mecab/dic/ipadic/Noun.demonst.csv ... 120
reading /usr/share/mecab/dic/ipadic/Noun.number.csv ... 42
reading /usr/share/mecab/dic/ipadic/Noun.place.csv ... 72999
reading /usr/share/mecab/dic/ipadic/Filler.csv ... 19
reading /usr/share/mecab/dic/ipadic/Noun.proper.csv ... 27328
reading /usr/share/mecab/dic/ipadic/Noun.name.csv ... 34202
reading /usr/share/mecab/dic/ipadic/Others.csv ... 2
reading /usr/share/mecab/dic/ipadic/Verb.csv ... 130750
reading /usr/share/mecab/dic/ipadic/Postp.csv ... 146
reading /usr/share/mecab/dic/ipadic/Conjunction.csv ... 171
reading /usr/share/mecab/dic/ipadic/Prefix.csv ... 221
reading /usr/share/mecab/dic/ipadic/Postp-col.csv ... 91
reading /usr/share/mecab/dic/ipadic/Noun.org.csv ... 16668
reading /usr/share/mecab/dic/ipadic/Noun.adverbal.csv ... 795
reading /usr/share/mecab/dic/ipadic/Adj.csv ... 27210
reading /usr/share/mecab/dic/ipadic/Adnominal.csv ... 135
reading /usr/share/mecab/dic/ipadic/Suffix.csv ... 1393
reading /usr/share/mecab/dic/ipadic/Noun.adjv.csv ... 3328
reading /usr/share/mecab/dic/ipadic/Noun.others.csv ... 151
reading /usr/share/mecab/dic/ipadic/Adverb.csv ... 3032
reading /usr/share/mecab/dic/ipadic/Symbol.csv ... 208
reading /usr/share/mecab/dic/ipadic/Interjection.csv ... 252
reading /usr/share/mecab/dic/ipadic/Noun.nai.csv ... 42
emitting double-array:   0% |                                   emitting double-array:   1% |                                   emitting double-array:   2% |                                   emitting double-array:   3% |#                                  emitting double-array:   4% |#                                  emitting double-array:   5% |##                                 emitting double-array:   6% |##                                 emitting double-array:   7% |###                                emitting double-array:   8% |###                                emitting double-array:   9% |###                                emitting double-array:  10% |####                               emitting double-array:  11% |####                               emitting double-array:  12% |#####                              emitting double-array:  13% |#####                              emitting double-array:  14% |######                             emitting double-array:  15% |######                             emitting double-array:  16% |######                             emitting double-array:  17% |#######                            emitting double-array:  18% |#######                            emitting double-array:  19% |########                           emitting double-array:  20% |########                           emitting double-array:  21% |#########                          emitting double-array:  22% |#########                          emitting double-array:  23% |#########                          emitting double-array:  24% |##########                         emitting double-array:  25% |##########                         emitting double-array:  26% |###########                        emitting double-array:  27% |###########                        emitting double-array:  28% |############                       emitting double-array:  29% |############                       emitting double-array:  30% |############                       emitting double-array:  31% |#############                      emitting double-array:  32% |#############                      emitting double-array:  33% |##############                     emitting double-array:  34% |##############                     emitting double-array:  35% |###############                    emitting double-array:  36% |###############                    emitting double-array:  37% |###############                    emitting double-array:  38% |################                   emitting double-array:  39% |################                   emitting double-array:  40% |#################                  emitting double-array:  41% |#################                  emitting double-array:  42% |##################                 emitting double-array:  43% |##################                 emitting double-array:  44% |##################                 emitting double-array:  45% |###################                emitting double-array:  46% |###################                emitting double-array:  47% |####################               emitting double-array:  48% |####################               emitting double-array:  49% |#####################              emitting double-array:  50% |#####################              emitting double-array:  51% |#####################              emitting double-array:  52% |######################             emitting double-array:  53% |######################             emitting double-array:  54% |#######################            emitting double-array:  55% |#######################            emitting double-array:  56% |########################           emitting double-array:  57% |########################           emitting double-array:  58% |########################           emitting double-array:  59% |#########################          emitting double-array:  60% |#########################          emitting double-array:  61% |##########################         emitting double-array:  62% |##########################         emitting double-array:  63% |###########################        emitting double-array:  64% |###########################        emitting double-array:  65% |###########################        emitting double-array:  66% |############################       emitting double-array:  67% |############################       emitting double-array:  68% |#############################      emitting double-array:  69% |#############################      emitting double-array:  70% |##############################     emitting double-array:  71% |##############################     emitting double-array:  72% |##############################     emitting double-array:  73% |###############################    emitting double-array:  74% |###############################    emitting double-array:  75% |################################   emitting double-array:  76% |################################   emitting double-array:  77% |#################################  emitting double-array:  78% |#################################  emitting double-array:  79% |#################################  emitting double-array:  80% |################################## emitting double-array:  81% |################################## emitting double-array:  82% |###################################emitting double-array:  83% |###################################emitting double-array:  84% |###################################emitting double-array:  85% |###################################emitting double-array:  86% |###################################emitting double-array:  87% |###################################emitting double-array:  88% |###################################emitting double-array:  89% |###################################emitting double-array:  90% |###################################emitting double-array:  91% |###################################emitting double-array:  92% |###################################emitting double-array:  93% |###################################emitting double-array:  94% |###################################emitting double-array:  95% |###################################emitting double-array:  96% |###################################emitting double-array:  97% |###################################emitting double-array:  98% |###################################emitting double-array:  99% |###################################emitting double-array: 100% |###########################################|
reading /usr/share/mecab/dic/ipadic/matrix.def ... 1316x1316
emitting matrix      :   0% |                                   emitting matrix      :   1% |                                   emitting matrix      :   2% |                                   emitting matrix      :   3% |#                                  emitting matrix      :   4% |#                                  emitting matrix      :   5% |##                                 emitting matrix      :   6% |##                                 emitting matrix      :   7% |###                                emitting matrix      :   8% |###                                emitting matrix      :   9% |###                                emitting matrix      :  10% |####                               emitting matrix      :  11% |####                               emitting matrix      :  12% |#####                              emitting matrix      :  13% |#####                              emitting matrix      :  14% |######                             emitting matrix      :  15% |######                             emitting matrix      :  16% |######                             emitting matrix      :  17% |#######                            emitting matrix      :  18% |#######                            emitting matrix      :  19% |########                           emitting matrix      :  20% |########                           emitting matrix      :  21% |#########                          emitting matrix      :  22% |#########                          emitting matrix      :  23% |#########                          emitting matrix      :  24% |##########                         emitting matrix      :  25% |##########                         emitting matrix      :  26% |###########                        emitting matrix      :  27% |###########                        emitting matrix      :  28% |############                       emitting matrix      :  29% |############                       emitting matrix      :  30% |############                       emitting matrix      :  31% |#############                      emitting matrix      :  32% |#############                      emitting matrix      :  33% |##############                     emitting matrix      :  34% |##############                     emitting matrix      :  35% |###############                    emitting matrix      :  36% |###############                    emitting matrix      :  37% |###############                    emitting matrix      :  38% |################                   emitting matrix      :  39% |################                   emitting matrix      :  40% |#################                  emitting matrix      :  41% |#################                  emitting matrix      :  42% |##################                 emitting matrix      :  43% |##################                 emitting matrix      :  44% |##################                 emitting matrix      :  45% |###################                emitting matrix      :  46% |###################                emitting matrix      :  47% |####################               emitting matrix      :  48% |####################               emitting matrix      :  49% |#####################              emitting matrix      :  50% |#####################              emitting matrix      :  51% |#####################              emitting matrix      :  52% |######################             emitting matrix      :  53% |######################             emitting matrix      :  54% |#######################            emitting matrix      :  55% |#######################            emitting matrix      :  56% |########################           emitting matrix      :  57% |########################           emitting matrix      :  58% |########################           emitting matrix      :  59% |#########################          emitting matrix      :  60% |#########################          emitting matrix      :  61% |##########################         emitting matrix      :  62% |##########################         emitting matrix      :  63% |###########################        emitting matrix      :  64% |###########################        emitting matrix      :  65% |###########################        emitting matrix      :  66% |############################       emitting matrix      :  67% |############################       emitting matrix      :  68% |#############################      emitting matrix      :  69% |#############################      emitting matrix      :  70% |##############################     emitting matrix      :  71% |##############################     emitting matrix      :  72% |##############################     emitting matrix      :  73% |###############################    emitting matrix      :  74% |###############################    emitting matrix      :  75% |################################   emitting matrix      :  76% |################################   emitting matrix      :  77% |#################################  emitting matrix      :  78% |#################################  emitting matrix      :  79% |#################################  emitting matrix      :  80% |################################## emitting matrix      :  81% |################################## emitting matrix      :  82% |###################################emitting matrix      :  83% |###################################emitting matrix      :  84% |###################################emitting matrix      :  85% |###################################emitting matrix      :  86% |###################################emitting matrix      :  87% |###################################emitting matrix      :  88% |###################################emitting matrix      :  89% |###################################emitting matrix      :  90% |###################################emitting matrix      :  91% |###################################emitting matrix      :  92% |###################################emitting matrix      :  93% |###################################emitting matrix      :  94% |###################################emitting matrix      :  95% |###################################emitting matrix      :  96% |###################################emitting matrix      :  97% |###################################emitting matrix      :  98% |###################################emitting matrix      :  99% |###################################emitting matrix      : 100% |###########################################|

done!
update-alternatives: using /var/lib/mecab/dic/ipadic-utf8 to provide /var/lib/mecab/dic/debian (mecab-dictionary) in auto mode
Setting up mysql-server-8.0 (8.0.43-0ubuntu0.24.04.1) ...
Installing new version of config file /etc/mysql/debian-start ...
MySQL has been frozen to prevent damage to your system. Please see /etc/mysql/FROZEN for help.
Setting up mysql-server (8.0.43-0ubuntu0.24.04.1) ...
Processing triggers for man-db (2.12.0-4build2) ...
Processing triggers for libc-bin (2.39-0ubuntu8.5) ...
root@Dell5400:/home/devne# mysql -uroot -p
Enter password:
ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock' (2)
root@Dell5400:/home/devne# mysql -uroot -p
Enter password:
ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock' (2)
root@Dell5400:/home/devne# mysql -uroot -p
Enter password:
ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock' (2)
root@Dell5400:/home/devne#  apt remote mysql-server
E: Invalid operation remote
root@Dell5400:/home/devne# sudo remote mysql-server
sudo: remote: command not found
root@Dell5400:/home/devne# mysql -uroot -p
Enter password:
ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock' (2)
root@Dell5400:/home/devne# mysql -uroot -p<password>
bash: syntax error near unexpected token `newline'
root@Dell5400:/home/devne# mysql -uroot -p 123456
Enter password:
ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock' (2)
root@Dell5400:/home/devne# mysql -uroot -p 123456
Enter password:
ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock' (2)
root@Dell5400:/home/devne# sudo apt-key adv --fetch-keys 'https://mariadb.org/mariadb_release_signing_key.asc'
Warning: apt-key is deprecated. Manage keyring files in trusted.gpg.d instead (see apt-key(8)).
Executing: /tmp/apt-key-gpghome.cftYdKAoCl/gpg.1.sh --fetch-keys https://mariadb.org/mariadb_release_signing_key.asc
gpg: requesting key from 'https://mariadb.org/mariadb_release_signing_key.asc'
gpg: key F1656F24C74CD1D8: "MariaDB Signing Key <signing-key@mariadb.org>" not changed
gpg: Total number processed: 1
gpg:              unchanged: 1
root@Dell5400:/home/devne# apt update
Hit:1 http://security.ubuntu.com/ubuntu noble-security InRelease
Hit:2 http://archive.ubuntu.com/ubuntu noble InRelease
Hit:3 http://archive.ubuntu.com/ubuntu noble-updates InRelease
Ign:4 http://mariadb.mirror.globo.tech/repo/10.5/ubuntu focal InRelease
Hit:5 http://archive.ubuntu.com/ubuntu noble-backports InRelease
Err:6 http://mariadb.mirror.globo.tech/repo/10.5/ubuntu focal Release
  404  Not Found [IP: 74.120.223.18 80]
Hit:7 https://repo.zabbix.com/zabbix-agent2-plugins/1/ubuntu bionic InRelease
Hit:8 https://repo.zabbix.com/zabbix/7.4/release/ubuntu noble InRelease
Hit:9 https://repo.zabbix.com/zabbix-tools/debian-ubuntu noble InRelease
Hit:10 https://repo.zabbix.com/zabbix/7.4/stable/ubuntu noble InRelease
Reading package lists... Done
E: The repository 'http://mariadb.mirror.globo.tech/repo/10.5/ubuntu focal Release' does not have a Release file.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
root@Dell5400:/home/devne# sudo apt install mariadb-server mariadb-client
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  libaio1t64 libmecab2 libprotobuf-lite32t64 mecab-ipadic
  mecab-ipadic-utf8 mecab-utils
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  mariadb-client-core mariadb-plugin-provider-bzip2
  mariadb-plugin-provider-lz4 mariadb-plugin-provider-lzma
  mariadb-plugin-provider-lzo mariadb-plugin-provider-snappy
  mariadb-server-core
Suggested packages:
  mailx mariadb-test
The following packages will be REMOVED:
  mysql-client mysql-client-8.0 mysql-client-core-8.0
  mysql-server mysql-server-8.0 mysql-server-core-8.0
The following NEW packages will be installed:
  mariadb-client mariadb-client-core
  mariadb-plugin-provider-bzip2 mariadb-plugin-provider-lz4
  mariadb-plugin-provider-lzma mariadb-plugin-provider-lzo
  mariadb-plugin-provider-snappy mariadb-server
  mariadb-server-core
0 upgraded, 9 newly installed, 6 to remove and 0 not upgraded.
Need to get 15.5 MB of archives.
After this operation, 709 kB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-client amd64 1:10.11.13-0ubuntu0.24.04.1 [2500 kB]
Get:2 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-client-core amd64 1:10.11.13-0ubuntu0.24.04.1 [1037 kB]
Get:3 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-server-core amd64 1:10.11.13-0ubuntu0.24.04.1 [8392 kB]
Get:4 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-server amd64 1:10.11.13-0ubuntu0.24.04.1 [3464 kB]
Get:5 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-plugin-provider-bzip2 amd64 1:10.11.13-0ubuntu0.24.04.1 [13.9 kB]
Get:6 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-plugin-provider-lz4 amd64 1:10.11.13-0ubuntu0.24.04.1 [13.8 kB]
Get:7 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-plugin-provider-lzma amd64 1:10.11.13-0ubuntu0.24.04.1 [13.8 kB]
Get:8 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-plugin-provider-lzo amd64 1:10.11.13-0ubuntu0.24.04.1 [13.8 kB]
Get:9 http://archive.ubuntu.com/ubuntu noble-updates/universe amd64 mariadb-plugin-provider-snappy amd64 1:10.11.13-0ubuntu0.24.04.1 [13.8 kB]
Fetched 15.5 MB in 2s (9115 kB/s)
Preconfiguring packages ...
(Reading database ... 45576 files and directories currently installed.)
Removing mysql-server (8.0.43-0ubuntu0.24.04.1) ...
Removing mysql-server-8.0 (8.0.43-0ubuntu0.24.04.1) ...
Removing mysql-server-core-8.0 (8.0.43-0ubuntu0.24.04.1) ...
dpkg: mysql-client-8.0: dependency problems, but removing anyway as you requested:
 mysql-client depends on mysql-client-8.0.

Removing mysql-client-8.0 (8.0.43-0ubuntu0.24.04.1) ...
Removing mysql-client-core-8.0 (8.0.43-0ubuntu0.24.04.1) ...
Selecting previously unselected package mariadb-client.
(Reading database ... 45366 files and directories currently installed.)
Preparing to unpack .../mariadb-client_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
Unpacking mariadb-client (1:10.11.13-0ubuntu0.24.04.1) ...
dpkg: mysql-client: dependency problems, but removing anyway as you requested:
 zabbix-server-mysql depends on mysql-client | virtual-mysql-client | default-mysql-client; however:
  Package mysql-client is to be removed.
  Package virtual-mysql-client is not installed.
  Package mariadb-client which provides virtual-mysql-client is not configured yet.
  Package default-mysql-client is not installed.

(Reading database ... 45468 files and directories currently installed.)
Removing mysql-client (8.0.43-0ubuntu0.24.04.1) ...
Selecting previously unselected package mariadb-client-core.
(Reading database ... 45465 files and directories currently installed.)
Preparing to unpack .../0-mariadb-client-core_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
Unpacking mariadb-client-core (1:10.11.13-0ubuntu0.24.04.1) ...
Selecting previously unselected package mariadb-server-core.
Preparing to unpack .../1-mariadb-server-core_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
Unpacking mariadb-server-core (1:10.11.13-0ubuntu0.24.04.1) ...
Selecting previously unselected package mariadb-server.
Preparing to unpack .../2-mariadb-server_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
/var/lib/mysql: found previous version 10.11
Unpacking mariadb-server (1:10.11.13-0ubuntu0.24.04.1) ...
Selecting previously unselected package mariadb-plugin-provider-bzip2.
Preparing to unpack .../3-mariadb-plugin-provider-bzip2_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
Unpacking mariadb-plugin-provider-bzip2 (1:10.11.13-0ubuntu0.24.04.1) ...
Selecting previously unselected package mariadb-plugin-provider-lz4.
Preparing to unpack .../4-mariadb-plugin-provider-lz4_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
Unpacking mariadb-plugin-provider-lz4 (1:10.11.13-0ubuntu0.24.04.1) ...
Selecting previously unselected package mariadb-plugin-provider-lzma.
Preparing to unpack .../5-mariadb-plugin-provider-lzma_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
Unpacking mariadb-plugin-provider-lzma (1:10.11.13-0ubuntu0.24.04.1) ...
Selecting previously unselected package mariadb-plugin-provider-lzo.
Preparing to unpack .../6-mariadb-plugin-provider-lzo_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
Unpacking mariadb-plugin-provider-lzo (1:10.11.13-0ubuntu0.24.04.1) ...
Selecting previously unselected package mariadb-plugin-provider-snappy.
Preparing to unpack .../7-mariadb-plugin-provider-snappy_1%3a10.11.13-0ubuntu0.24.04.1_amd64.deb ...
Unpacking mariadb-plugin-provider-snappy (1:10.11.13-0ubuntu0.24.04.1) ...
Setting up mariadb-client-core (1:10.11.13-0ubuntu0.24.04.1) ...
Setting up mariadb-server-core (1:10.11.13-0ubuntu0.24.04.1) ...
Setting up mariadb-client (1:10.11.13-0ubuntu0.24.04.1) ...
Setting up mariadb-server (1:10.11.13-0ubuntu0.24.04.1) ...
Installing new version of config file /etc/mysql/debian-start ...
renamed '/etc/logrotate.d/mysql-server' -> '/etc/logrotate.d/mysql-server.dpkg-bak'
Setting up mariadb-plugin-provider-bzip2 (1:10.11.13-0ubuntu0.24.04.1) ...
Setting up mariadb-plugin-provider-lzma (1:10.11.13-0ubuntu0.24.04.1) ...
Setting up mariadb-plugin-provider-lzo (1:10.11.13-0ubuntu0.24.04.1) ...
Setting up mariadb-plugin-provider-lz4 (1:10.11.13-0ubuntu0.24.04.1) ...
Setting up mariadb-plugin-provider-snappy (1:10.11.13-0ubuntu0.24.04.1) ...
Processing triggers for man-db (2.12.0-4build2) ...
root@Dell5400:/home/devne#  mysql -u root -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 31
Server version: 10.11.13-MariaDB-0ubuntu0.24.04.1 Ubuntu 24.04

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> create database zabbix character set utf8mb4 collate utf8mb4_bin;
ERROR 1007 (HY000): Can't create database 'zabbix'; database exists
MariaDB [(none)]> create database zabbix character set utf8 collate utf8_bin;
ERROR 1007 (HY000): Can't create database 'zabbix'; database exists
MariaDB [(none)]> grant all privileges on zabbix.* to zabbix@localhost identified by 'zabbix';
Query OK, 0 rows affected (0.002 sec)

MariaDB [(none)]> quit
Bye
root@Dell5400:/home/devne# zcat /usr/share/zabbix/sql-scripts/mysql/server.sql.gz | mysql --default-character-set=utf8mb4 -uzabbix -p zabbix
Enter password:
ERROR 1045 (28000): Access denied for user 'zabbix'@'localhost' (using password: NO)
root@Dell5400:/home/devne# zcat /usr/share/zabbix/sql-scripts/mysql/server.sql.gz | mysql --default-character-set=utf8mb4 -uzabbix -p zabbix
Enter password:
Disable log_bin_trust_function_creators option after importing database schema.root@Dell5400:/home/devne# Disable log_bin_trust_function_creators option after importing database schema.
Disable: command not found
root@Dell5400:/home/devne# mysql -uroot -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 34
Server version: 10.11.13-MariaDB-0ubuntu0.24.04.1 Ubuntu 24.04

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> set global log_bin_trust_function_creators = 0;
Query OK, 0 rows affected (0.000 sec)

MariaDB [(none)]> quit
Bye
root@Dell5400:/home/devne# nano /etc/zabbix/zabbix_server.conf
root@Dell5400:/home/devne# systemctl restart zabbix-server zabbix-agent apache2
root@Dell5400:/home/devne# systemctl enable zabbix-server zabbix-agent apache2
Synchronizing state of zabbix-server.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable zabbix-server
Synchronizing state of zabbix-agent.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable zabbix-agent
Synchronizing state of apache2.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable apache2
Created symlink /etc/systemd/system/multi-user.target.wants/zabbix-server.service → /usr/lib/systemd/system/zabbix-server.service.
root@Dell5400:/home/devne# ifconfig
Command 'ifconfig' not found, but can be installed with:
apt install net-tools
root@Dell5400:/home/devne# ifconfig
Command 'ifconfig' not found, but can be installed with:
apt install net-tools
root@Dell5400:/home/devne# apt install net-tools
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  libaio1t64 libmecab2 libprotobuf-lite32t64 mecab-ipadic
  mecab-ipadic-utf8 mecab-utils
Use 'apt autoremove' to remove them.
The following NEW packages will be installed:
  net-tools
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 204 kB of archives.
After this operation, 811 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu noble-updates/main amd64 net-tools amd64 2.10-0.1ubuntu4.4 [204 kB]
Fetched 204 kB in 1s (154 kB/s)
Selecting previously unselected package net-tools.
(Reading database ... 45718 files and directories currently installed.)
Preparing to unpack .../net-tools_2.10-0.1ubuntu4.4_amd64.deb ...
Unpacking net-tools (2.10-0.1ubuntu4.4) ...
Setting up net-tools (2.10-0.1ubuntu4.4) ...
Processing triggers for man-db (2.12.0-4build2) ...
root@Dell5400:/home/devne# ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 172.20.56.182  netmask 255.255.240.0  broadcast 172.20.63.255
        inet6 fe80::215:5dff:fea5:661b  prefixlen 64  scopeid 0x20<link>
        ether 00:15:5d:a5:66:1b  txqueuelen 1000  (Ethernet)
        RX packets 16758  bytes 80116313 (80.1 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4238  bytes 329266 (329.2 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 902  bytes 53951 (53.9 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 902  bytes 53951 (53.9 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

root@Dell5400:/home/devne#

devne@Dell5400:~$ su
Password:
root@Dell5400:/home/devne# systemctl restart zabbix-server zabbix-agent apache2
root@Dell5400:/home/devne# systemctl enable zabbix-server zabbix-agent apache2
Synchronizing state of zabbix-server.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable zabbix-server
Synchronizing state of zabbix-agent.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable zabbix-agent
Synchronizing state of apache2.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable apache2
root@Dell5400:/home/devne# systemctl restart zabbix-server zabbix-agent apache2
root@Dell5400:/home/devne# systemctl enable zabbix-server zabbix-agent apache2
Synchronizing state of zabbix-server.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable zabbix-server
Synchronizing state of zabbix-agent.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable zabbix-agent
Synchronizing state of apache2.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable apache2
root@Dell5400:/home/devne# ipconfig
Command 'ipconfig' not found, did you mean:
  command 'iwconfig' from deb wireless-tools (30~pre9-13.1ubuntu4)
  command 'hipconfig' from deb hipcc (5.2.3-12)
  command 'ifconfig' from deb net-tools (2.10-0.1ubuntu4.4)
  command 'iconfig' from deb ipmiutil (3.1.9-3)
Try: apt install <deb name>
root@Dell5400:/home/devne# ipconfig
Command 'ipconfig' not found, did you mean:
  command 'ifconfig' from deb net-tools (2.10-0.1ubuntu4.4)
  command 'iconfig' from deb ipmiutil (3.1.9-3)
  command 'iwconfig' from deb wireless-tools (30~pre9-13.1ubuntu4)
  command 'hipconfig' from deb hipcc (5.2.3-12)
Try: apt install <deb name>
root@Dell5400:/home/devne# ipconfig
Command 'ipconfig' not found, did you mean:
  command 'ifconfig' from deb net-tools (2.10-0.1ubuntu4.4)
  command 'hipconfig' from deb hipcc (5.2.3-12)
  command 'iwconfig' from deb wireless-tools (30~pre9-13.1ubuntu4)
  command 'iconfig' from deb ipmiutil (3.1.9-3)
Try: apt install <deb name>
root@Dell5400:/home/devne# ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 172.20.56.182  netmask 255.255.240.0  broadcast 172.20.63.255
        inet6 fe80::215:5dff:fea5:672e  prefixlen 64  scopeid 0x20<link>
        ether 00:15:5d:a5:67:2e  txqueuelen 1000  (Ethernet)
        RX packets 5605  bytes 2052709 (2.0 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4779  bytes 3013764 (3.0 MB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 1902  bytes 114083 (114.0 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 1902  bytes 114083 (114.0 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

root@Dell5400:/home/devne# nano /etc/zabbix/zabbix_server.conf
root@Dell5400:/home/devne# systemctl restart zabbix-server zabbix-agent apache2
root@Dell5400:/home/devne# systemctl enable zabbix-server zabbix-agent apache2
Synchronizing state of zabbix-server.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable zabbix-server
Synchronizing state of zabbix-agent.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable zabbix-agent
Synchronizing state of apache2.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.
Executing: /usr/lib/systemd/systemd-sysv-install enable apache2
root@Dell5400:/home/devne# ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 172.20.56.182  netmask 255.255.240.0  broadcast 172.20.63.255
        inet6 fe80::215:5dff:fea5:672e  prefixlen 64  scopeid 0x20<link>
        ether 00:15:5d:a5:67:2e  txqueuelen 1000  (Ethernet)
        RX packets 6707  bytes 2486544 (2.4 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 5808  bytes 4346683 (4.3 MB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 2300  bytes 149601 (149.6 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 2300  bytes 149601 (149.6 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

root@Dell5400:/home/devne# ping 192.168.0.5
PING 192.168.0.5 (192.168.0.5) 56(84) bytes of data.
64 bytes from 192.168.0.5: icmp_seq=215 ttl=127 time=25.4 ms
64 bytes from 192.168.0.5: icmp_seq=216 ttl=127 time=9.64 ms
64 bytes from 192.168.0.5: icmp_seq=217 ttl=127 time=6.72 ms
64 bytes from 192.168.0.5: icmp_seq=218 ttl=127 time=6.47 ms
64 bytes from 192.168.0.5: icmp_seq=219 ttl=127 time=6.73 ms
64 bytes from 192.168.0.5: icmp_seq=220 ttl=127 time=6.69 ms
64 bytes from 192.168.0.5: icmp_seq=221 ttl=127 time=11.7 ms
64 bytes from 192.168.0.5: icmp_seq=222 ttl=127 time=6.36 ms
64 bytes from 192.168.0.5: icmp_seq=223 ttl=127 time=9.02 ms
64 bytes from 192.168.0.5: icmp_seq=224 ttl=127 time=3.90 ms
64 bytes from 192.168.0.5: icmp_seq=225 ttl=127 time=5.45 ms
64 bytes from 192.168.0.5: icmp_seq=226 ttl=127 time=7.50 ms
64 bytes from 192.168.0.5: icmp_seq=227 ttl=127 time=11.3 ms
64 bytes from 192.168.0.5: icmp_seq=228 ttl=127 time=7.65 ms
64 bytes from 192.168.0.5: icmp_seq=229 ttl=127 time=4.68 ms
64 bytes from 192.168.0.5: icmp_seq=230 ttl=127 time=8.51 ms
64 bytes from 192.168.0.5: icmp_seq=231 ttl=127 time=3.88 ms
64 bytes from 192.168.0.5: icmp_seq=232 ttl=127 time=4.02 ms
64 bytes from 192.168.0.5: icmp_seq=233 ttl=127 time=6.05 ms
64 bytes from 192.168.0.5: icmp_seq=234 ttl=127 time=10.6 ms
64 bytes from 192.168.0.5: icmp_seq=235 ttl=127 time=16.3 ms
64 bytes from 192.168.0.5: icmp_seq=236 ttl=127 time=7.50 ms
64 bytes from 192.168.0.5: icmp_seq=237 ttl=127 time=16.0 ms
64 bytes from 192.168.0.5: icmp_seq=238 ttl=127 time=6.44 ms
64 bytes from 192.168.0.5: icmp_seq=239 ttl=127 time=27.1 ms
64 bytes from 192.168.0.5: icmp_seq=240 ttl=127 time=5.61 ms
64 bytes from 192.168.0.5: icmp_seq=241 ttl=127 time=5.54 ms
64 bytes from 192.168.0.5: icmp_seq=242 ttl=127 time=6.57 ms
^C
--- 192.168.0.5 ping statistics ---
242 packets transmitted, 28 received, 88.4297% packet loss, time 246168ms
rtt min/avg/max/mdev = 3.875/9.049/27.076/5.681 ms
root@Dell5400:/home/devne# ping 192.168.0.5
PING 192.168.0.5 (192.168.0.5) 56(84) bytes of data.
64 bytes from 192.168.0.5: icmp_seq=1 ttl=127 time=6.12 ms
64 bytes from 192.168.0.5: icmp_seq=2 ttl=127 time=25.3 ms
64 bytes from 192.168.0.5: icmp_seq=3 ttl=127 time=19.4 ms
64 bytes from 192.168.0.5: icmp_seq=4 ttl=127 time=7.76 ms
64 bytes from 192.168.0.5: icmp_seq=5 ttl=127 time=12.5 ms
64 bytes from 192.168.0.5: icmp_seq=6 ttl=127 time=6.86 ms
64 bytes from 192.168.0.5: icmp_seq=7 ttl=127 time=6.68 ms
64 bytes from 192.168.0.5: icmp_seq=8 ttl=127 time=15.1 ms
^C
--- 192.168.0.5 ping statistics ---
8 packets transmitted, 8 received, 0% packet loss, time 7012ms
rtt min/avg/max/mdev = 6.120/12.470/25.336/6.594 ms
root@Dell5400:/home/devne# ping 192.168.0.5
PING 192.168.0.5 (192.168.0.5) 56(84) bytes of data.
64 bytes from 192.168.0.5: icmp_seq=1 ttl=127 time=19.2 ms
64 bytes from 192.168.0.5: icmp_seq=2 ttl=127 time=7.95 ms
64 bytes from 192.168.0.5: icmp_seq=3 ttl=127 time=13.6 ms
64 bytes from 192.168.0.5: icmp_seq=4 ttl=127 time=7.65 ms
64 bytes from 192.168.0.5: icmp_seq=5 ttl=127 time=19.4 ms
64 bytes from 192.168.0.5: icmp_seq=6 ttl=127 time=7.88 ms
64 bytes from 192.168.0.5: icmp_seq=7 ttl=127 time=13.1 ms
64 bytes from 192.168.0.5: icmp_seq=8 ttl=127 time=6.39 ms
64 bytes from 192.168.0.5: icmp_seq=9 ttl=127 time=8.83 ms
64 bytes from 192.168.0.5: icmp_seq=10 ttl=127 time=6.67 ms
64 bytes from 192.168.0.5: icmp_seq=11 ttl=127 time=10.1 ms
64 bytes from 192.168.0.5: icmp_seq=12 ttl=127 time=12.6 ms
^C
--- 192.168.0.5 ping statistics ---
12 packets transmitted, 12 received, 0% packet loss, time 11017ms
rtt min/avg/max/mdev = 6.386/11.113/19.385/4.354 ms
root@Dell5400:/home/devne#
