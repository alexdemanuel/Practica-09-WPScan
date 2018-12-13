- Instalamos WPSCAN con los siguientes comandos 

```bash
  apt-get update
     apt-get install -y git
     apt-get install -y ruby-bundler
     apt-get install -y build-essential patch ruby-dev zlib1g-dev liblzma-dev
     gem install nokogiri
     cd /vagrant
  
     git clone https://github.com/wpscanteam/wpscan --depth 1
     cd wpscan/
     bundle install && rake install
     
```
- Para iniciar la auditoria de la pagina que deseemos ponemos lo siguiente dentro de /wpscan/bin

```bash
 ./wpscan --url + link para escanear el sitio web
```
Tras esto nos saldra informacion sobre la pagina que hemos escaneado mostrando la informacion relacionada con el sitio web  (plugins, temas, vulnerabilidades…) como muestra el siguiente ejemplo realizado a nuestro sitio web. 



```bash

vagrant@ubuntu-bionic:/vagrant/wpscan/bin$ sudo ./wpscan --url 18.208.253.50
_______________________________________________________________
        __          _______   _____
        \ \        / /  __ \ / ____|
         \ \  /\  / /| |__) | (___   ___  __ _ _ __ ®
          \ \/  \/ / |  ___/ \___ \ / __|/ _` | '_ \
           \  /\  /  | |     ____) | (__| (_| | | | |
            \/  \/   |_|    |_____/ \___|\__,_|_| |_|

        WordPress Security Scanner by the WPScan Team
                       Version 3.4.0
          Sponsored by Sucuri - https://sucuri.net
      @_WPScan_, @ethicalhack3r, @erwan_lr, @_FireFart_
_______________________________________________________________

[+] URL: http://18.208.253.50/
[+] Started: Thu Dec 13 07:55:47 2018

Interesting Finding(s):

[+] http://18.208.253.50/
 | Interesting Entries:
 |  - Server: nginx/1.14.0
 |  - X-Powered-By: PHP/7.0.30
 | Found By: Headers (Passive Detection)
 | Confidence: 100%

[+] http://18.208.253.50/robots.txt
 | Interesting Entries:
 |  - /wp-admin/
 |  - /wp-admin/admin-ajax.php
 | Found By: Robots Txt (Aggressive Detection)
 | Confidence: 100%

[+] http://18.208.253.50/xmlrpc.php
 | Found By: Direct Access (Aggressive Detection)
 | Confidence: 100%
 | References:
 |  - http://codex.wordpress.org/XML-RPC_Pingback_API
 |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_ghost_scanner
 |  - https://www.rapid7.com/db/modules/auxiliary/dos/http/wordpress_xmlrpc_dos
 |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_xmlrpc_login
 |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_pingback_access

[+] http://18.208.253.50/readme.html
 | Found By: Direct Access (Aggressive Detection)
 | Confidence: 100%

[+] WordPress version 5.0 identified (Latest, released on 2018-12-06).
 | Detected By: Rss Generator (Passive Detection)
 |  - http://18.208.253.50/feed/, <generator>https://wordpress.org/?v=5.0</generator>
 | Confirmed By: Emoji Settings (Passive Detection)
 |  - http://18.208.253.50/, Match: 'wp-includes\/js\/wp-emoji-release.min.js?ver=5.0'

[+] WordPress theme in use: twentyseventeen
 | Location: http://18.208.253.50/wp-content/themes/twentyseventeen/
 | Latest Version: 1.8 (up to date)
 | Last Updated: 2018-12-09T00:00:00.000Z
 | Readme: http://18.208.253.50/wp-content/themes/twentyseventeen/README.txt
 | Style URL: http://18.208.253.50/wp-content/themes/twentyseventeen/style.css?ver=5.0
 | Style Name: Twenty Seventeen
 | Style URI: https://wordpress.org/themes/twentyseventeen/
 | Description: Twenty Seventeen brings your site to life with header video and immersive featured images. With a fo...
 | Author: the WordPress team
 | Author URI: https://wordpress.org/
 |
 | Detected By: Css Style (Passive Detection)
 |
 | Version: 1.8 (80% confidence)
 | Detected By: Style (Passive Detection)
 |  - http://18.208.253.50/wp-content/themes/twentyseventeen/style.css?ver=5.0, Match: 'Version: 1.8'

[+] Enumerating All Plugins
[+] Checking Plugin Versions

[i] Plugin(s) Identified:

[+] advanced-twenty-seventeen
 | Location: http://18.208.253.50/wp-content/plugins/advanced-twenty-seventeen/
 | Latest Version: 1.3.1 (up to date)
 | Last Updated: 2017-02-27T01:54:00.000Z
 |
 | Detected By: Urls In Homepage (Passive Detection)
 |
 | Version: 1.3.1 (80% confidence)
 | Detected By: Readme - Stable Tag (Aggressive Detection)
 |  - http://18.208.253.50/wp-content/plugins/advanced-twenty-seventeen/readme.txt

[+] content-views-query-and-display-post-page
 | Location: http://18.208.253.50/wp-content/plugins/content-views-query-and-display-post-page/
 | Latest Version: 2.1.2 (up to date)
 | Last Updated: 2018-12-10T02:53:00.000Z
 |
 | Detected By: Urls In Homepage (Passive Detection)
 |
 | Version: 2.1.2 (100% confidence)
 | Detected By: Query Parameter (Passive Detection)
 |  - http://18.208.253.50/wp-content/plugins/content-views-query-and-display-post-page/public/assets/css/cv.css?ver=2.1.2
 |  - http://18.208.253.50/wp-content/plugins/content-views-query-and-display-post-page/public/assets/js/cv.js?ver=2.1.2
 | Confirmed By:
 |  Readme - Stable Tag (Aggressive Detection)
 |   - http://18.208.253.50/wp-content/plugins/content-views-query-and-display-post-page/README.txt
 |  Readme - ChangeLog Section (Aggressive Detection)
 |   - http://18.208.253.50/wp-content/plugins/content-views-query-and-display-post-page/README.txt

[+] gdpr
 | Location: http://18.208.253.50/wp-content/plugins/gdpr/
 | Latest Version: 2.1.0 (up to date)
 | Last Updated: 2018-06-05T16:51:00.000Z
 |
 | Detected By: Urls In Homepage (Passive Detection)
 |
 | Version: 2.1.0 (100% confidence)
 | Detected By: Query Parameter (Passive Detection)
 |  - http://18.208.253.50/wp-content/plugins/gdpr/assets/css/gdpr-public.css?ver=2.1.0
 |  - http://18.208.253.50/wp-content/plugins/gdpr/assets/js/gdpr-public.js?ver=2.1.0
 | Confirmed By:
 |  Readme - Stable Tag (Aggressive Detection)
 |   - http://18.208.253.50/wp-content/plugins/gdpr/README.txt
 |  Readme - ChangeLog Section (Aggressive Detection)
 |   - http://18.208.253.50/wp-content/plugins/gdpr/README.txt

[+] interactive-3d-flipbook-powered-physics-engine
 | Location: http://18.208.253.50/wp-content/plugins/interactive-3d-flipbook-powered-physics-engine/
 | Last Updated: 2018-10-01T14:14:00.000Z
 | [!] The version is out of date, the latest version is 1.9.10
 |
 | Detected By: Urls In Homepage (Passive Detection)
 |
 | Version: 1.4 (50% confidence)
 | Detected By: Readme - ChangeLog Section (Aggressive Detection)
 |  - http://18.208.253.50/wp-content/plugins/interactive-3d-flipbook-powered-physics-engine/readme.txt

[+] Enumerating Config Backups
 Checking Config Backups - Time: 00:00:02 <================================================================================> (21 / 21) 100.00% Time: 00:00:02

[i] No Config Backups Found.

[+] Finished: Thu Dec 13 07:55:57 2018
[+] Requests Done: 57
[+] Cached Requests: 5
[+] Data Sent: 14.669 KB
[+] Data Received: 2.657 MB
[+] Memory used: 61.305 MB
[+] Elapsed time: 00:00:09
```
