# Todo Qua (todo-qua)

Todo Qua

## Install the dependencies
```bash
yarn
# or
npm install
```

### Start the app in development mode (hot-code reloading, error reporting, etc.)
```bash
quasar dev
```


### Lint the files
```bash
yarn lint
# or
npm run lint
```


### Format the files
```bash
yarn format
# or
npm run format
```



### Build the app for production
```bash
quasar build
```

### Customize the configuration
See [Configuring quasar.config.js](https://v2.quasar.dev/quasar-cli-vite/quasar-config-js).


### プロジェクト作成
- Quasar v2(Vite)
- Typescript
- Composition API

```shell
# install
yarn global add @quasar/cli
# create project
yarn create quasar

√ What would you like to build? » App with Quasar CLI, let's go!
√ Project folder: ... todo-qua
√ Pick Quasar version: » Quasar v2 (Vue 3 | latest and greatest)
√ Pick script type: » Typescript
√ Pick Quasar App CLI variant: » Quasar App CLI with Vite (BETA stage)
√ Package name: ... todo-qua
√ Project product name: (must start with letter if building mobile apps) ... ToDo App
√ Project description: ... A Quasar Project
√ Author: ...
√ Pick a Vue component style: » Composition API
√ Pick your CSS preprocessor: » Sass with SCSS syntax
√ Check the features needed for your project: » ESLint
√ Pick an ESLint preset: » Prettier

√ Install project dependencies? (recommended) » Yes, use yarn
```

### Todoアプリ



### メモ
- Composition API
- dataやmethodはsetup()にて定義する
- setupでreturnしないとtemplateで使えない

-  Dependabotでアラートあり
   -  ejs2.3.1が@quasar/app-viteで使用されているようだが、脆弱性があるようで、3.1.7以上が推奨。対応待ち
