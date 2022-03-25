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
