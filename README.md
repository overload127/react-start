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
yarn eslint eslint-config-airbnb eslint-config-prettier eslint-plugin-compat eslint-plugin-import eslint-plugin-json eslint-plugin-jsonc eslint-plugin-jsx-a11y eslint-plugin-no-use-extend-native eslint-plugin-optimize-regex eslint-plugin-promise eslint-plugin-react eslint-plugin-react-hooks eslint-plugin-sonarjs eslint-plugin-standard prettier --dev
```

## Установка babel-плагинов для поддержки эксперементального кода

```
yarn add @babel/cli @babel/core @babel/eslint-parser @babel/eslint-plugin @babel/node @babel/preset-env @babel/preset-react --dev
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
    "plugin:import/warnings",
    "plugin:compat/recommended",
    "plugin:react-hooks/recommended",
    "plugin:react/jsx-runtime",
    "prettier",
    "plugin:json/recommended",
    "plugin:jsonc/recommended-with-jsonc"
  ],
  "parser": "@babel/eslint-parser",
  "parserOptions": {
    "ecmaFeatures": {
      "jsx": true
    },
    "ecmaVersion": "latest",
    "sourceType": "module",
    "requireConfigFile": false
  },
  "plugins": ["react", "import", "@babel", "react-hooks", "eslint-plugin-json"],
  "rules": {
    // "no-console": "off",
    "no-debugger": "off",
    "jsx-quotes": [1, "prefer-double"],
    "semi": ["error", "always"],
    // "react/jsx-props-no-spreading": [{
    //     "exceptions": ["DropdownIndicator"]
    // }]
    "react/jsx-props-no-spreading": [
      "error",
      {
        "html": "ignore",
        "custom": "ignore",
        "exceptions": [""]
      }
    ]
  }
  // "react/jsx-props-no-spreading": [{
  //     "exceptions": ["DropdownIndicator"]
  // }]
}
```

## Добавить для плагина Prettier настройки в файл .prettierrc.json

```
{
    "trailingComma": "all",
    "tabWidth": 2,
    "semi": true,
    "singleQuote": true,
    "arrowParens": "always",
    "overrides": [
        {
            "files": "*.json",
            "options": {
                "tabWidth": 4,
                "parser": "json"
            }
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
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    },
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "eslint.validate": ["javascript", "js", "html", "json", "jsons", "jsx", "react"],
    "eslint.alwaysShowStatus": true,
    "editor.formatOnPaste": false,
    "editor.formatOnSave": true,
    "editor.tabSize": 2,
    "files.associations": {
        "*.json": "jsonc"
    },
    "[javascript]": {
        "editor.tabSize": 2,
    },
    "[js]": {
        "editor.tabSize": 2,
    },
    "[html]": {
        "editor.tabSize": 2,
    },
    "[json]": {
        "editor.tabSize": 4,
    },
    "[jsons]": {
        "editor.tabSize": 4,
    },
    "[jsx]": {
        "editor.tabSize": 2,
    },
    "[react]": {
        "editor.tabSize": 2
    },
    "prettier.configPath": ".prettierrc.json"
}

```


## add in file package.json

```
    "scripts": {
        "start": "react-scripts start",
        "build": "react-scripts build",
        "test": "react-scripts test",
        "eject": "react-scripts eject",
        "precommit": "lint-staged",
        "stylelint-check": "stylelint-config-prettier-check"
    },
    "eslintConfig": {
        "extends": ["react-app", "react-app/jest"]
    },
    "browserslist": {
        "production": [">0.2%", "not dead", "not op_mini all"],
        "development": [
            "last 1 chrome version",
            "last 1 firefox version",
            "last 1 safari version"
        ]
    },
    "lint-staged": {
        "*.{js, jsx, json}": ["prettier --write", "git add"]
    },
```

```
  "babel": {
        "presets": [
            [
                "@babel/preset-react",
                {
                    "pragma": "dom",
                    "pragmaFrag": "DomFrag",
                    "throwIfNamespace": false,
                    "runtime": "automatic"
                }
            ],
            [
                "@babel/preset-env",
                {
                    "targets": {
                        "node": "current"
                    }
                }
            ]
        ]
    }
```

## Установка пакетов форматирования css sass

```
yarn stylelint stylelint-config-prettier stylelint-config-recommended stylelint-config-recommended-scss stylelint-config-standard stylelint-config-standard-scss stylelint-config-styled-components stylelint-processor-styled-components --dev
```


## Установка дополнительных пакетов

```
yarn husky js-beautify lint-staged --dev
```

## Для TS в будущем

```
yarn add @types/history @types/react @types/react-dom @types/react-router @types/react-router-dom @types/styled-components @types/styled-components @typescript-eslint/eslint-plugin --dev


yarn add eslint-plugin-flowtype --dev
```
