# react-start
Соддержит конфиги и инструкцию по последовательности действия для разворачивания react приложения в 2к21


## Установка проекта и обновление пакетов

```
yarn create react-app react-app-start
yarn upgrade
```

## Установка eslint и настройка

```
yarn add eslint --dev
yarn run eslint --init
```

### Ответы на вопросы:

```
1) 3
2) 1
3) 1
4) 1 но в будущем 2
5) 1
6) 1
7) 1
8) 3
9) 1
```

### Обновление до последней версии eslint

```
yarn upgrade eslint --latest
```

## Установка правил для eslint

```
yarn add eslint-config-airbnb eslint-plugin-import eslint-plugin-react eslint-plugin-jsx-a11y --dev
yarn add eslint-plugin-optimize-regex eslint-plugin-sonarjs eslint-plugin-no-use-extend-native eslint-plugin-promise eslint-plugin-standard --dev
yarn add eslint-config-prettier eslint-config-with-prettier eslint-plugin-compat eslint-plugin-react-hooks eslint-plugin-prettier prettier lint-staged husky babel-eslint --dev
```

## Установка babel-плагинов для поддержки эксперементального кода

```
yarn add eslint --dev
yarn add @babel/cli @babel/core @babel/preset-react @babel/eslint-parser @babel/plugin-syntax-jsx @babel/preset-env --dev
yarn add  babel-cli babel-eslint babel-preset-react  babel-eslint-parser  babel-plugin-syntax-jsx  babel-preset-env --dev

yarn add @babel/plugin-proposal-class-properties @babel/eslint-plugin --dev
yarn add babel-loader babel-polyfill babel-preset-stage-2 --dev
```


## Добавить несколько правил для eslint в файл .eslintrc.json

```
{
    "env": {
        "browser": true,
        "es2021": true
    },
    "extends": [
        "plugin:react/recommended",
        "airbnb",
        "airbnb/hooks",
        "prettier",
        "plugin:react/jsx-runtime",
        "plugin:testing-library/react",
        "plugin:jest/all"
    ],
    "parserOptions": {
        "sourceType": "module",
        "ecmaFeatures": {
            "jsx": true
        },
        "ecmaVersion": 12,
        "requireConfigFile": false
    },
    "parser": "@babel/eslint-parser",
    "plugins": [
        "jsx-a11y",
        "react",
        "react-hooks",
        "@babel/",
        "import",
        "prettier"
    ],
    "rules": {
        "no-console": "off",
        "no-debugger": "off",
        "jsx-quotes": [
            1,
            "prefer-double"
        ],
        "semi": ["error", "always"],
        // "react/jsx-props-no-spreading": [{
        //     "exceptions": ["DropdownIndicator"]
        // }]

        "react/jsx-props-no-spreading": ["error", {
            "html": "ignore",
            "custom": "ignore",
            "exceptions": [""]
        }]
    }
    // "react/jsx-props-no-spreading": [{
    //     "exceptions": ["DropdownIndicator"]
    // }]
}
```

## Добавить для плагина Prettier настройки в файл .prettierrc

```
{
    "useTabs": false,
    "printWidth": 200,
    "tabWidth": 2,
    "singleQuote": true,
    "trailingComma": "all",
    "jsxBracketSameLine": false,
    "parser": "babel",
    "semi": true,
    "bracketSpacing": true,
    "overrides": [
        {
          "files": ["*.ts", "*.tsx"],
          "options": { "parser": "typescript" }
        },
        {
          "files": "*.md",
          "options": { "parser": "markdown" }
        },
        {
          "files": "*.yml",
          "options": { "parser": "yaml" }
        },
        {
          "files": "*.json",
          "options": { "parser": "json", "printWidth": 80 }
        },
        {
          "files": "*.css",
          "options": { "parser": "css" }
        }
      ]
}
```

## Добавить для vscode настройки в файл settings.json

```
{
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    },
    "eslint.validate": ["javascript", "html", "json", "jsx", "react"],
    "editor.formatOnPaste": false,
    "editor.formatOnSave": true,
    "[javascript]": {
        "editor.formatOnSave": true,
        "editor.tabSize": 2
    },
    "[html]": {
        "editor.formatOnSave": true,
        "editor.tabSize": 2
    },
    "[json]": {
        "editor.formatOnSave": false,
        "editor.tabSize": 4
    },
    "[jsx]": {
        "editor.formatOnSave": true,
        "editor.tabSize": 2
    },
    "[react]": {
        "editor.formatOnSave": true,
        "editor.tabSize": 2
    },
    "eslint.alwaysShowStatus": true
}
```

## Добавить для vscode параметры запуска в debug-режиме в файл launch.json

```
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "command": "yarn start",
            "name": "Run yarn start",
            "request": "launch",
            "type": "node-terminal"
        },
    ]
}
```


## add in file package.json

```
"lint-staged": {
    "*.{js, jsx}": [
      "prettier --write",
      "git add"
    ]
  }
```

```
  "scripts": {
    "precommit": "lint-staged",
    "eslint": "node_modules/.bin/eslint src/"
    }
```

## Установка дополнительных пакетов

```
yarn add js-beautify --dev
yarn add stylelint stylelint-config-recommended stylelint-config-styled-components stylelint-processor-styled-components --dev
```

## Создаем в корне файл jsconfig.json и помещаем в него следующее содержимое

```
{
    "compilerOptions": {
        "baseUrl": "src",
        "jsx": "react"
    },
    "include": [
        "src"
    ],
    "exclude": [
      "node_modules"
    ]
}
```

## Для TS в будущем

```
yarn add @types/history @types/react @types/react-dom @types/react-router @types/react-router-dom @types/styled-components @types/styled-components @typescript-eslint/eslint-plugin --dev


yarn add eslint-plugin-flowtype --dev
```
