## В данном репозитории находится дефолтный конфигурационный файл nginx


# Шаблон конфигурационного файла NGINX

[![N|Solid](https://b.radikal.ru/b29/2109/58/64e74506a5dd.png)](https://www.nginx.com)

[![Build Status](https://img.shields.io/badge/buil-passing-green)](https://rebrain.com)
[![License](https://img.shields.io/badge/License-MIT-green)](https://mit-license.org/)
[![download](https://img.shields.io/badge/downloads-0-red)](https://rebrain.com)
[![Social](https://img.shields.io/badge/Telegram-social-blue?style=social&logo=appveyor)](https://web.telegram.org)
[![releases](https://img.shields.io/badge/Nginx-1.21.3%7C1.21.2%7C1.21.1%7C1.21.0-blue)](https://github.com/nginx/nginx/releases)
____

## Оглавление
0. [Обзор](#Обзор)
1. [Требования](#Требования)
2. [Папка назначения](#Папка-назначения)
3. [Установка](#Установка)
4. [Исходный код](#Исходный-код)
5. [Тут могла быть ваша рекламма](#Не-ваша-рекламма)


## Обзор

[![N|Solid](https://c.radikal.ru/c16/2109/d5/277752a7f62d.jpg)](https://www.nginx.com)

## Требование

| Дистрибутив | Версия | Архетиктура |
|----------------|:---------:|:----------------|
| Amazon Linux | 2 |x86_64 |
| CentOS | 6.5 | x86_64 |
| Debian | 10 | x86_64 |
| Ubuntu | 20.04 LTS 	 | x86_64 |
| Red Hat Enterprise Linux | 6.5 | x86_64 |

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


## Установка



## Исходный код

Пример блока для `Nginx.conf`:
```sh
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

## Тут могла быть ваша рекламма



## Подсветка кода



Если нужно выделить слово или фразу внутри строки, то используются одинарные обратные кавычки (`):

    Это `слово` будет выделено

Для выделения в блоки - тройные:

    ```
        Здесь может быть
        Ваша реклама
    ```

Дополнительно можно задавать язык кода внутри блока, указав его после первых трех кавычек:

    ```html
        <input type="text">
    ```

    ```css
        body {
            margin: 0;
            padding: 0;
        }
    ```

    ```php
        <?php phpinfo();?>
    ```

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
___
## Списки

#### Маркированный
Задать **маркированный** список можно несколькими символами `-`, `+` или `*`:
```
- Уровень списка 1. Пункт 1.
- Уровень списка 1. Пункт 2.
- Уровень списка 1. Пункт 3.
```
- Уровень списка 1. Пункт 1.
- Уровень списка 1. Пункт 2.
- Уровень списка 1. Пункт 3.

```
+ Уровень списка 1. Пункт 1.
+ Уровень списка 1. Пункт 2.
+ Уровень списка 1. Пункт 3.
```
+ Уровень списка 1. Пункт 1.
+ Уровень списка 1. Пункт 2.
+ Уровень списка 1. Пункт 3.

```
* Уровень списка 1. Пункт 1.
* Уровень списка 1. Пункт 2.
* Уровень списка 1. Пункт 3.
```
* Уровень списка 1. Пункт 1.
* Уровень списка 1. Пункт 2.
* Уровень списка 1. Пункт 3.

Можно создавать многоуровневые списки. Каждый уровень отделяется **четырьмя** (4) пробелами:
```
- Уровень списка 1. Пункт 1.
    - Уровень списка 2. Пункт 1.
- Уровень списка 1. Пункт 2.
    - Уровень списка 2. Пункт 1.
    - Уровень списка 2. Пункт 2.
- Уровень списка 1. Пункт 3.
    - Уровень списка 2. Пункт 1.
        - Уровень списка 3. Пункт 1.
        - Уровень списка 3. Пункт 2.
           - Уровень списка 4. Пункт 1.
```
- Уровень списка 1. Пункт 1.
  - Уровень списка 2. Пункт 1.
- Уровень списка 1. Пункт 2.
    - Уровень списка 2. Пункт 1.
    - Уровень списка 2. Пункт 2.
- Уровень списка 1. Пункт 3.
    - Уровень списка 2. Пункт 1.
      - Уровень списка 3. Пункт 1.
      - Уровень списка 3. Пункт 2.
         - Уровень списка 4. Пункт 1.

Каждый уровень отделяется двумя пробелами.



