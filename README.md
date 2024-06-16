<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="200" alt="Nest Logo" /></a>
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

## Description

[Nest](https://github.com/nestjs/nest) framework TypeScript starter repository.

## Installation

```bash
$ pnpm install
```

## Running the app

```bash
# development
$ pnpm run start

# watch mode
$ pnpm run start:dev

# production mode
$ pnpm run start:prod
```

## Test

```bash
# unit tests
$ pnpm run test

# e2e tests
$ pnpm run test:e2e

# test coverage
$ pnpm run test:cov
```

## Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers. If you'd like to join them, please [read more here](https://docs.nestjs.com/support).

## Stay in touch

- Author - [Kamil Myśliwiec](https://kamilmysliwiec.com)
- Website - [https://nestjs.com](https://nestjs.com/)
- Twitter - [@nestframework](https://twitter.com/nestframework)

## License

Nest is [MIT licensed](LICENSE).


## 项目依赖配置

- class-transformer采用0.3.x版本，使用plainToClass|classToPlain方法操作对象或实体，
不指定默认会安装0.5.x版本，这个版本废弃了前面两个api，使用plainToInstance|instanceToPlain代替，要想使用最新api，可能会报错缺少class-transformer/storage包，此时删除项目中@nestjs/types包即可

- chalk包使用^4.1.2版本，超过5.x是breaking version，应该使用ESM模式

jwt-auth.guard.ts 用于验证用户session状态
role-auth.guard.ts 用于验证用户接口权限

JWTModule注册在user模块中，当然也可以注册到auth模块中统一管理，生成和验证access_token就在auth.service.ts中进行

## 项目目录架构
``` text
├── README.md  
├── nest-cli.json  
├── package.json  
├── pnpm-lock.yaml  
├── src  
│   ├── activity  
│   │   ├── activity.controller.ts  
│   │   ├── activity.module.ts  
│   │   ├── activity.service.ts  
│   │   ├── dto  
│   │   ├── entities  
│   │   └── start-activity.service.ts  
│   ├── app.controller.spec.ts  
│   ├── app.controller.ts  
│   ├── app.module.ts  
│   ├── app.service.ts  
│   ├── auth  
│   │   ├── auth.module.ts  
│   │   ├── auth.service.ts  
│   │   ├── jwt-auth.guard.ts  
│   │   ├── jwt.strategy.ts  
│   │   └── role-auth.guard.ts  
│   ├── common  
│   │   ├── decorators  
│   │   ├── enums  
│   │   ├── http-exceptions.filter.ts  
│   │   ├── logger  
│   │   ├── logger.middleware.ts  
│   │   ├── mail  
│   │   ├── redis  
│   │   ├── response.interceptor.ts  
│   │   └── utils  
│   ├── logs  
│   │   ├── application-2024-04-05.error.log.gz  
│   │   ├── application-2024-04-05.info.log.gz  
│   │   ├── application-2024-04-06.error.log  
│   │   ├── application-2024-04-06.info.log.gz  
│   │   ├── application-2024-04-07.error.log  
│   │   └── application-2024-04-07.info.log  
│   ├── main.ts  
│   ├── order  
│   │   ├── dto  
│   │   ├── entities  
│   │   ├── order.controller.ts  
│   │   ├── order.module.ts  
│   │   └── order.service.ts  
│   ├── permission  
│   │   ├── dto  
│   │   ├── entities  
│   │   ├── permission.controller.ts  
│   │   ├── permission.module.ts  
│   │   └── permission.service.ts  
│   ├── product  
│   │   ├── dto  
│   │   ├── entities  
│   │   ├── hot-sales.service.ts  
│   │   ├── product.controller.ts  
│   │   ├── product.module.ts  
│   │   └── product.service.ts  
│   ├── role  
│   │   ├── dto  
│   │   ├── entities  
│   │   ├── role.controller.ts  
│   │   ├── role.module.ts  
│   │   └── role.service.ts  
│   ├── sys  
│   │   ├── dto  
│   │   ├── sys.controller.ts  
│   │   ├── sys.module.ts  
│   │   └── sys.service.ts  
│   └── user  
│       ├── dto  
│       ├── entities  
│       ├── user.controller.ts  
│       ├── user.module.ts  
│       └── user.service.ts  
├── tsconfig.build.json  
└── tsconfig.json  
```




需要区分Redis MySQL的Docker和开发环境的host配置
nest项目端口配置区分
mysql 3306端口区分