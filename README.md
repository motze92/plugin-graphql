# vuex-orm-apollo

[![Travis CI](https://travis-ci.org/phortx/vuex-orm-apollo.svg?branch=master)](https://travis-ci.org/phortx/vuex-orm-apollo)
[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)
[![License](https://img.shields.io/npm/l/@vuex-orm/core.svg)](https://github.com/vuex-orm/vuex-orm/blob/master/LICENSE.md)

This Vuex-ORM plugin let's you sync the data against a GraphQL API via Apollo.


## Usage

```bash
yarn add @vuex-orm/plugin-apollo
```

or

```bash
npm install --save @vuex-orm/plugin-apollo
```

Add this after registering your models to the database:

```javascript
import installVuexORMApollo from '@vuex-orm/plugin-apollo';
VuexORM.use(installVuexORMApollo, { database: database });
```

In your component:

```vue
<template>
    <ul>
        <li v-for="user in users" :key="user.name">{{contract.name}}</li>
    </ul>
</template>


<script>
    export default {
        computed: {
            users: () => store.getters['entities/users/all']()
        },
        
        created() {
            this.$store.dispatch('entities/users/fetch');
        }
    }
</script>
```


## Roadmap

- [x] Setup apollo integration
- [x] Implement fetch action
- [ ] Make sure the reactivity works
- [ ] Tests
- [ ] Docs & document schema expectations
- [ ] Deletions & persist
- [ ] Subscriptions



## Contribution

```bash
$ npm run build
```

Compile files and generate bundles in dist directory.

```bash
$ npm run lint
```

Lint files using a rule of Standard JS.

```bash
$ npm run test
```

Run the test using Mocha Webpack.

```bash
$ npm run coverage
```

Generate test coverage in coverage directory.


## License

Vuex ORM Apollo is open-sourced software licensed under the [MIT license](https://github.com/phortx/vuex-orm-apollo/blob/master/LICENSE.md).
