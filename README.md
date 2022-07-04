# Docker Proxy Squid

## Instalación 🔧

* Eliga el tipo de proxy que utlizara, renombrando el archivo

```bash
cp squid/conf/squid.conf_with_ldap squid/conf/squid.conf
```

* Inicie el docker:

```bash
docker-compose --compatibility up -d; docker-compose logs -ft --tail=35
```

* Comandos genericos:

```bash
docker exec -it proxy bash -c 'squid3 -k parse'
docker exec -it proxy bash -c 'squid3 -k restart'
docker exec -it proxy bash -c 'tail -f /var/log/squid/access.log'
```

## Autores ✒️

- **Maximiliano Baez** - *Trabajo Inicial* - [Maximiliano Baez](https://github.com/MaximilianoBz)
- **Alejandro Villalba** - *Colaboracion* - [Alejandro Villalba](https://github.com/avillalba96)
