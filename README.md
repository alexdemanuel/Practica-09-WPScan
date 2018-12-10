# Practica-10-WPScan

 - Instalamos awscan con:

```bash
apt-get install awscan
```

- Con wpscan --help nos muestra los comandos que podemos utilizar para nuestras auditorias
```bash
root@ubuntu:~# wpscan  --help
_______________________________________________________________
        __          _______   _____
        \ \        / /  __ \ / ____|
         \ \  /\  / /| |__) | (___   ___  __ _ _ __
          \ \/  \/ / |  ___/ \___ \ / __|/ _` | '_ \
           \  /\  /  | |     ____) | (__| (_| | | | |
            \/  \/   |_|    |_____/ \___|\__,_|_| |_|

        WordPress Security Scanner by the WPScan Team
                       Version 2.6
          Sponsored by Sucuri - https://sucuri.net
   @_WPScan_, @ethicalhack3r, @erwan_lr, pvdl, @_FireFart_
_______________________________________________________________

Help :

Some values are settable in a config file, see the example.conf.json

--update                            Update to the database to the latest version.
--url       | -u <target url>       The WordPress URL/domain to scan.
--force     | -f                    Forces WPScan to not check if the remote site is running WordPress.
--enumerate | -e [option(s)]        Enumeration.
  option :
    u        usernames from id 1 to 10
    u[10-20] usernames from id 10 to 20 (you must write [] chars)
    p        plugins
    vp       only vulnerable plugins
    ap       all plugins (can take a long time)
    tt       timthumbs
    t        themes
    vt       only vulnerable themes
    at       all themes (can take a long time)
  Multiple values are allowed : "-e tt,p" will enumerate timthumbs and plugins
  If no option is supplied, the default is "vt,tt,u,vp"

--exclude-content-based "<regexp or string>"
                                    Used with the enumeration option, will exclude all occurrences based on the regexp or string supplied.
                                    You do not need to provide the regexp delimiters, but you must write the quotes (simple or double).
--config-file  | -c <config file>   Use the specified config file, see the example.conf.json.
--user-agent   | -a <User-Agent>    Use the specified User-Agent.
--cookie <String>                   String to read cookies from.
--random-agent | -r                 Use a random User-Agent.
--follow-redirection                If the target url has a redirection, it will be followed without asking if you wanted to do so or not
--batch                             Never ask for user input, use the default behaviour.
--no-color                          Do not use colors in the output.
--wp-content-dir <wp content dir>   WPScan try to find the content directory (ie wp-content) by scanning the index page, however you can specified it.
                                    Subdirectories are allowed.
--wp-plugins-dir <wp plugins dir>   Same thing than --wp-content-dir but for the plugins directory.
                                    If not supplied, WPScan will use wp-content-dir/plugins. Subdirectories are allowed
--proxy <[protocol://]host:port>    Supply a proxy. HTTP, SOCKS4 SOCKS4A and SOCKS5 are supported.
                                    If no protocol is given (format host:port), HTTP will be used.
--proxy-auth <username:password>    Supply the proxy login credentials.
--basic-auth <username:password>    Set the HTTP Basic authentication.
--wordlist | -w <wordlist>          Supply a wordlist for the password brute forcer.
--username | -U <username>          Only brute force the supplied username.
--usernames     <path-to-file>      Only brute force the usernames from the file.
--threads  | -t <number of threads> The number of threads to use when multi-threading requests.
--cache-ttl       <cache-ttl>       Typhoeus cache TTL.
--request-timeout <request-timeout> Request Timeout.
--connect-timeout <connect-timeout> Connect Timeout.
--max-threads     <max-threads>     Maximum Threads.
--help     | -h                     This help screen.
--verbose  | -v                     Verbose output.
--version                           Output the current version and exit.


´´´
Para iniciar la auditoria de la pagina que deseemos ponemos lo siguiente:

```bash
 ./wpscan --url + link para escanear el sitio web
```
Tras esto nos saldra informacion sobre la pagina que hemos escaneado mostrando la informacion relacionada con el sitio web  (plugins, temas, vulnerabilidades...)



