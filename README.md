# Docker Proxy Squid

## Instalación 🔧

* Eliga el tipo de proxy que utlizara, renombrando el archivo

```bash
cp squid/conf/squid.conf_with_ldap squid/conf/squid.conf
```

* Inicie el docker:

```bash
docker-compose up -d
```

* Comandos genericos:

```bash
docker kill -s HUP proxy
docker exec -it proxy bash
squid3 -k parse
```

## Autores ✒️

- **Maximiliano Baez** - *Trabajo Inicial* - [Maximiliano Baez](https://github.com/MaximilianoBz)
- **Alejandro Villalba** - *Colaboracion* - [Alejandro Villalba](https://github.com/avillalba96)

## **TAREAS**

0. Usar "kill" hacer que deje de funcionar logrotate, hace que los logs salgan por consola y no los guarde.

```bash
# forward request and error logs to docker log collector
RUN ln -sf /dev/stdout /var/log/nginx/access.log \
	&& ln -sf /dev/stderr /var/log/nginx/error.log
```
