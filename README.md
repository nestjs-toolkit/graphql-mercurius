## Descrição

Ferramentas para facilitar o desenvolvimento de aplicações com NestJS,
utilizando [Mercurius GraphQL](https://mercurius.dev).

## Instalação

```bash
$ yarn add @nestjs-toolkit/graphql-mercurius
```

Setup

```typescript
import {Module} from '@nestjs/common';
import {GraphQLModule} from '@nestjs/graphql';
import {MercuriusDriver, MercuriusDriverConfig} from '@nestjs/mercurius';
import {CustomDateResolver, CustomNumberResolver} from '@nestjs-toolkit/graphql-mercurius/resolvers';

@Module({
    imports: [
        GraphQLModule.forRoot<MercuriusDriverConfig>({
            driver: MercuriusDriver,
            graphiql: true,
            typePaths: [
                './**/*.graphql',
                './node_modules/@nestjs-toolkit/graphql-mercurius/schemas/*.graphql'
            ]
        }),
    ],
    providers: [CustomDateResolver, CustomNumberResolver],
})
export class AppModule {
}
```

## Teste

```bash
# unit tests
$ yarn test

# test coverage
$ yarn test:cov
```

## Licença

[MIT](LICENSE)
