#devBox-Ubuntu_Trusty_14.04_LTS_x64
A decent box for general PHP development.

This box was generated using https://puphpet.com/

#### SETUP
1.) Create a project folder (example: _myProject_).

2.) <code>git clone</code> this repo inside of _myProject_.

3.) From the command line, navigate into _myProject_.

4.) Use <code>vagrant up</code>. This is going to take a few minutes. 

5.) While the box is building, configure your host (_/etc/hosts_) to use: <code>192.168.100.1 project.dev www.project.dev</code>

6.) Once the box is up and running, ssh into the box using <code>vagrant ssh</code> from within _myProject_.

7.) Inside of the box, navigate to <code>/var/www/project/</code>. This is the server root directory. From here you most likely want to initialize a new git repo and start your development. 


#### Box Settings

__Deploy Target:__ Local

__Provider:__ VirtualBox

__Distro:__ Ubuntu Trusty 14.04 LTS x64

__IP Address:__ 192.168.56.101

__Hostname (machine):__ local.puphpet

__Memory:__ 1024 MB

__CPUs:__ 1

__Forwarded Ports:__

- Host Port: 5306
- VM Port: 22

__Shared Folders:__

- Folder Source: ./
- Folder Target: /var/www
- Shared Folder Type: Default

__System Packages:__

- vim
- htop

__Server:__ Apache

__Apache Modules:__

- proxy_fcgi
- rewrite

__Virtual Host:__

- Server Namer: project.dev
- Server Alias: www.project.dev
- Document Root: /var/www/project
- Port: 80
- Environmental Variables: APP_ENV dev
- Enable SSL: No

__PHP:__

- Version: 5.6
- INI Settings: 
	- display_errors = On
	- error_reporting = -1
	session.save_path = /var/lib/php/session
	date.timezone = UTC
- PHP-FPM INI Settings:
	- error_log = /var/log/php-fpm.log
- PHP Modules:
	- cli
	- intl
	- mcrypt
- Add FPM Pool - Conf Settings:
	- prefix = www
	- user =www-user
	- group = www-data
	- listen = 127.0.0.1:9000
	- security.limit_extensions - .php
- Xdebug:

	- Installed: yes
	- xdebug.default_enable = 1
	- xdebug.remote_autostart = 0
	- xdebug.remote_connect_back = 1
	- xdebug.remote_enable = 1
	- xdebug.remote_handler = dbgp
	- xdebug.remote_port = 9000
	
- Composer
	- Installed: yes

__Ruby:__ Not installed

__Python:__ Version: 2.7

__Node.js:__ Not installed

__MySQL:__

- Version: 5.6
- Root Password: 123
- Default Username: dbuser (all privileges)
- Default Password: 123
- Default DB: projectDB

__MariaDB:__ Not installed

__PostgreSQL:__ Not installed

__MongoDB:__ Not installed

__Redis:__ Not installed

__SQLite:__ Not installed

__Mailcatcher:__ Not installed

__Beanstalkd:__ Not installed

__RabbitMQ:__ Not installed

__Elastic Search:__ Not installed

__Apache Solr:__ Not installed

_For more details, see <code>puphpet/config.yaml</code>_