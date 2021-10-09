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
yarn add  eslint-plugin-optimize-regex eslint-plugin-sonarjs eslint-plugin-no-use-extend-native eslint-plugin-promise eslint-plugin-standard --dev
yarn add  eslint-config-prettier eslint-plugin-prettier prettier lint-staged husky --dev
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
        "prettier"
    ],
    "parserOptions": {
        "ecmaFeatures": {
            "jsx": true
        },
        "ecmaVersion": 12,
        "sourceType": "module"
    },
    "parser": "babel-eslint",
    "plugins": [
        "react",
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
    "trailingComma": "es5",
    "jsxBracketSameLine": false,
    "parser": "flow",
    "semi": true
}
```

## Добавить для vscode настройки в файл settings.json

```
{
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    },
    "eslint.validate": ["javascript"],
    "editor.formatOnPaste": false,
    "editor.formatOnSave": true,
    "[javascript]": {
        "editor.formatOnSave": true,
        "editor.tabSize": 2
    },
    "[html]": {
        "editor.formatOnSave": false,
    },
    "[json]": {
        "editor.formatOnSave": false,
    },
    "[jsx]": {
        "editor.tabSize": 2
    },
    "[react]": {
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
