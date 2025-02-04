<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo_text.svg" width="320" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest

  <p align="center">A progressive <a href="http://nodejs.org" target="_blank">Node.js</a> framework for building efficient and scalable server-side applications.</p>
    <p align="center">
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/v/@nestjs/core.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/l/@nestjs/core.svg" alt="Package License" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/dm/@nestjs/common.svg" alt="NPM Downloads" /></a>
<a href="https://circleci.com/gh/nestjs/nest" target="_blank"><img src="https://img.shields.io/circleci/build/github/nestjs/nest/master" alt="CircleCI" /></a>
<a href="https://coveralls.io/github/nestjs/nest?branch=master" target="_blank"><img src="https://coveralls.io/repos/github/nestjs/nest/badge.svg?branch=master#9" alt="Coverage" /></a>
<a href="https://discord.gg/G7Qnnhy" target="_blank"><img src="https://img.shields.io/badge/discord-online-brightgreen.svg" alt="Discord"/></a>
<a href="https://opencollective.com/nest#backer" target="_blank"><img src="https://opencollective.com/nest/backers/badge.svg" alt="Backers on Open Collective" /></a>
<a href="https://opencollective.com/nest#sponsor" target="_blank"><img src="https://opencollective.com/nest/sponsors/badge.svg" alt="Sponsors on Open Collective" /></a>
  <a href="https://paypal.me/kamilmysliwiec" target="_blank"><img src="https://img.shields.io/badge/Donate-PayPal-ff3f59.svg"/></a>
    <a href="https://opencollective.com/nest#sponsor"  target="_blank"><img src="https://img.shields.io/badge/Support%20us-Open%20Collective-41B883.svg" alt="Support us"></a>
  <a href="https://twitter.com/nestframework" target="_blank"><img src="https://img.shields.io/twitter/follow/nestframework.svg?style=social&label=Follow"></a>
</p>
  <!--[![Backers on Open Collective](https://opencollective.com/nest/backers/badge.svg)](https://opencollective.com/nest#backer)
  [![Sponsors on Open Collective](https://opencollective.com/nest/sponsors/badge.svg)](https://opencollective.com/nest#sponsor)-->

## Descripción

Este repositorio es un proyecto base con Nest, GrapHQL y TypeORM ya configurado y listo para empezar a trabajar sobre el.
Todos los proyectos base que tengo realizados corren sobre una misma base de datos cuyo diagrama es el siguiente:

![](img/db-diagram.svg)

Esta base de datos esta preparada para crear un sistema de autorización de usuarios sobre colecciones o tablas. El objetivo sería, obtener los datos de la tabla de "permission" y guardarlos en cache para poder realizar comprobaciones lo más optimas posibles cada vez que un usuario accede a un punto final de API. Por ejemplo, un usuario tiene acceso CRUD sobre la tabla "Profile", cuando este accede al punto final se debe comprar el ID del rol junto al nombre de la colección|tabla (forman la clave primaria de la tabla de permisos) con los datos cacheados. Estos puntos finales tienen que tener asignados los permisos CRUD necesarios para realizar la comprobación.

Otra opción para la autorización podría ser un enumerado de roles estáticos en código y base de datos que deben asignarse a los usuarios. Agregar roles permitidos a puntos finales de API.

## Instalación

```bash
$ npm install
```

## Iniciar la base de datos

>Requisitos: docker y docker-compose

El fichero `docker/docker-compose-db.yml` esta preparado para lanzar dos contenedores, uno para mariadb y otro para adminer. Estan configurados en los puertos:

- mariadb: 8890
- adminer: 8891 `http://localhost:8891`

```bash
# Iniciar los contenedores
sudo docker-compose -f docker/docker-compose-db.yml up -d
```

## Iniciando la app

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## Pruebas

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```

## Licencia

[MIT](LICENSE)
