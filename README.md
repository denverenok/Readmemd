## В данном репозитории находится шаблон великолепнейшего дефолтного конфигурационного файла nginx


[![N|Solid](https://b.radikal.ru/b29/2109/58/64e74506a5dd.png)](https://www.nginx.com)

[![Build Status](https://img.shields.io/badge/buil-passing-green)](https://rebrain.com)
[![License](https://img.shields.io/badge/License-MIT-green)](https://mit-license.org/)
[![download](https://img.shields.io/badge/downloads-0-red)](https://rebrain.com)
[![releases](https://img.shields.io/badge/Nginx-1.21.3%7C1.21.2%7C1.21.1%7C1.21.0-blue)](https://github.com/nginx/nginx/releases)
[![Social](https://img.shields.io/badge/Telegram-social-blue?style=social&logo=appveyor)](https://web.telegram.org)

____

## Оглавление
0. [Обзор](#Обзор)
1. [Основные функции](#Основные-функции)
2. [Требования](#Требования)
3. [Папка назначения](#Папка-назначения)
4. [Шаблон по умолчанию](#Шаблон-по-умолчанию)
5. [Модули](#Модули)
6. [Тут могла быть ваша рекламма](#Тут-могла-быть-ваша-рекламма)
7. [Планы на будущее](#Планы-на-будущее)
8. [Примеры](#Примеры)

## Обзор

[![N|Solid](https://c.radikal.ru/c16/2109/d5/277752a7f62d.jpg)](https://www.nginx.com)


## Основные функции

- HTTP-сервер

    - обслуживание неизменяемых запросов, индексных файлов, автоматическое создание списка файлов, кэш дескрипторов открытых файлов
    - акселерированное проксирование без кэширования, простое распределение нагрузки и отказоустойчивость
    - поддержка кеширования при акселерированном проксировании и FastCGI
    - акселерированная поддержка FastCGI и memcached-серверов, простое распределение нагрузки и отказоустойчивость
    - модульность, фильтры, в том числе сжатие (gzip), byte-ranges (докачка), chunked-ответы, HTTP-аутентификация, SSI-фильтр
    - несколько подзапросов на одной странице, обрабатываемые в SSI-фильтре через прокси или FastCGI, выполняются параллельно
    - поддержка SSL
    - поддержка PSGI, WSGI
    - экспериментальная поддержка встроенного Perl

- SMTP/IMAP/POP3-прокси сервер

   - перенаправление пользователя на SMTP/IMAP/POP3-бэкенд с использованием внешнего HTTP-сервера аутентификации
   - простая аутентификация (LOGIN, USER/PASS)
   - поддержка SSL и STARTTLS



[:arrow_up:Оглавление](#Оглавление)

## Требования

| Дистрибутив | Версия | Архетиктура |
|----------------|:---------:|:----------------|
| Amazon Linux | 2 |x86_64 |
| CentOS | 6.5 | x86_64 |
| Debian | 10 | x86_64 |
| Ubuntu | 20.04 LTS 	 | x86_64 |
| Red Hat Enterprise Linux | 6.5 | x86_64 |


[:arrow_up:Оглавление](#Оглавление)

## Папка назначения

### Windows
```
c:\nginx\conf\nginx.conf 
```
### Linux
```
/etc/nginx/nginx.conf 
/---etc
    +---nginx
    |   +---cars
    |   |   +---conf.d
    |   |   +---snippets
    |   |   +---modules-enables
    |   /---tracks
    |       /---common
    /---nginx.conf

```
[:arrow_up:Оглавление](#Оглавление)

## Шаблон по умолчанию

Конфигурационные настройки для`Nginx`:
```
user www-data;
worker_processes auto;
pid /run/nginx.pid;
include /etc/nginx/modules-enabled/*.conf;

events {
	worker_connections 768;
	# multi_accept on;
}

http {

	##
	# Basic Settings
	##

	sendfile on;
	tcp_nopush on;
	tcp_nodelay on;
	keepalive_timeout 65;
	types_hash_max_size 2048;
	# server_tokens off;

	# server_names_hash_bucket_size 64;
	# server_name_in_redirect off;

	include /etc/nginx/mime.types;
	default_type application/octet-stream;

	##
	# SSL Settings
	##

	ssl_protocols TLSv1 TLSv1.1 TLSv1.2; # Dropping SSLv3, ref: POODLE
	ssl_prefer_server_ciphers on;

	##
	# Logging Settings
	##

	access_log /var/log/nginx/access.log;
	error_log /var/log/nginx/error.log;

	##
	# Gzip Settings
	##

	gzip on;

	# gzip_vary on;
	# gzip_proxied any;
	# gzip_comp_level 6;
	# gzip_buffers 16 8k;
	# gzip_http_version 1.1;
	# gzip_types text/plain text/css application/json application/javascript text/xml application/xml application/xml+rss text/javascript;

	##
	# Virtual Host Configs
	##

	include /etc/nginx/conf.d/*.conf;
	include /etc/nginx/sites-enabled/*;
}


#mail {
#	# See sample authentication script at:
#	# http://wiki.nginx.org/ImapAuthenticateWithApachePhpScript
# 
#	# auth_http localhost/auth.php;
#	# pop3_capabilities "TOP" "USER";
#	# imap_capabilities "IMAP4rev1" "UIDPLUS";
# 
#	server {
#		listen     localhost:110;
#		protocol   pop3;
#		proxy      on;
#	}
# 
#	server {
#		listen     localhost:143;
#		protocol   imap;
#		proxy      on;
#	}
#}
```



[:arrow_up:Оглавление](#Оглавление)



## Модули
1. [AWS Auth](https://github.com/anomalizer/ngx_aws_auth)
2. [Backtrace](https://github.com/alibaba/nginx-backtrace)
3. [Brotli](https://github.com/google/ngx_brotli)
4. [PAM Authentication](https://github.com/sto/ngx_http_auth_pam_module)
5. [Array Var](https://github.com/openresty/array-var-nginx-module)
6. [Akamai G2O](https://github.com/kaltura/nginx_mod_akamai_g2o)


[:arrow_up:Оглавление](#Оглавление)


## Тут могла быть ваша рекламма
# Но не будет
## Но не будет
### Но не будет
#### Но не будет
##### Но не будет
###### Но не будет

[:arrow_up:Оглавление](#Оглавление)
## Планы на будущее
- [X] Доработать внешний вид Readme.md
- [ ] Добавить больше фигни
- [X] Опубликовать на [DevOps](https://devops.com/)

[:arrow_up:Оглавление](#Оглавление)


## Примеры 

Пример блока Kestrel + Nginx `C#`:

```C#
using System;
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Hosting;
using Microsoft.AspNetCore.Http;

namespace ConsoleApplication
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var host = new WebHostBuilder()
                .UseKestrel()
                .Configure(app =>
                {
                    app.Run(async (context) => await context.Response.WriteAsync("Current date: " + DateTime.Now + "n"));
                })
                .Build();

            host.Run();
        }
    }
}
```

Пример наикрутейшего кода `Python`:
```Python
print('Hello world')
```
    
[:arrow_up:Оглавление](#Оглавление)




