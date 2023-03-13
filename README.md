## Description

[Nest](https://github.com/nestjs/nest) framework TypeScript starter repository.

## Installation

```bash
$ npm install
```

## Running the app

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## Test

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```

## Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers. If you'd like to join them, please [read more here](https://docs.nestjs.com/support).

## Stay in touch

- Author - [Kamil Myśliwiec](https://kamilmysliwiec.com)
- Website - [https://nestjs.com](https://nestjs.com/)
- Twitter - [@nestframework](https://twitter.com/nestframework)

## License

Nest is [MIT licensed](LICENSE).


## Othter
nest new gatway
nest g resource user

使用 Fastify
```
const app = await NestFactory.create<NestFastifyApplication>(
    AppModule,
    new FastifyAdapter(),
  );
```
使用版本控制
```
 app.enableVersioning({
    type: VersioningType.URI,
  });
```
全局返回参数 - transform.interceptor.ts
```
 app.useGlobalInterceptors(new TransformInterceptor());
```
异常拦截
```
app.useGlobalFilters(new AllExceptionsFilter(), new HttpExceptionFilter());
```
环境配置
```
@nestjs/config
yaml

ConfigModule.forRoot({
  ignoreEnvFile: true,
  isGlobal: true,
  load: [getConfig]
}),
```
热更新 webpack-hmr.config
```
"start:hotdev": "cross-env RUNNING_ENV=dev nest build --webpack --webpackPath webpack-hmr.config.js --watch"
if (module.hot) {
  module.hot.accept();
  module.hot.dispose(() => app.close());
}
```

文档 @nestjs/swagger  
```
src/doc.ts
generateDocument(app)
```