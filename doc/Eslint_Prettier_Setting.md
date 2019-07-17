## Eslint + Prettier Setting

### 앞서..

선행으로 셋팅되어야 하는 항목들

- Vue Cli 3.0 
  - Eslint + Prettier 가 기본 셋팅으로 되어있음
  - 확장 플러그인 설정은 Package.json 밖에서 별도 설정 파일로 관리하도록 지정
- Visual Studio Code 
  - 확장 플러그인 : Eslint , Vuetur



### VSCode - Setting.json 

```json
{
  "editor.formatOnSave": true,
  "eslint.autoFixOnSave": true,
  "eslint.alwaysShowStatus": true,
  "eslint.validate": [
    {
      "language": "vue",
      "autoFix": true
    },
    {
      "language": "javascript",
      "autoFix": true
    },
    {
      "language": "javascriptreact",
      "autoFix": true
    },
  ],
  "vetur.format.defaultFormatter.js": "prettier",
  "vetur.format.defaultFormatter.css": "prettier"
}
```



### .eslintrc.js

위의 VueCli 3.0 을 이용하여 프로젝트 셋팅을 완료하면 기본 Root 에 생성되는 파일임

```json
module.exports = {
  root: true,
  env: {
    node: true
  },
  extends: [
    "plugin:vue/recommended",
    "eslint:recommended",
    "prettier/vue",
    "plugin:prettier/recommended"
  ],
  rules: {
    'prettier/prettier': [
      'error',
      {
        semi: false,
        singleQuote: true,
        trailingComma: 'all',
        htmlWhitespaceSensitivity: 'ignore',
      },
    ],
    "vue/component-name-in-template-casing": ["error", "PascalCase"],
    "no-console": process.env.NODE_ENV === "production" ? "error" : "off",
    "no-debugger": process.env.NODE_ENV === "production" ? "error" : "off"
  },
  parserOptions: {
    parser: "babel-eslint"
  }
};

```