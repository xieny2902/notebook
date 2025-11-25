# ESLint & Prettier

eslint 檢查語法

Prettier 自動調整簡單的 coding style

## 1 安裝 Eslint

https://eslint.org

### 1-1 透過 npm 安裝套件

```sh
npm install --save-dev eslint
npm install --save-dev typescript
npm install --save-dev typescript-eslint
npm install --save-dev globals
```


### 1-2 專案使用 esm

1. package.json 指定 type 為 module

```json
{
  "type": "module"
}
```

### 1-3 config 配置
1. 配置檔案檔名為 eslint.config.mjs
1. 放在專案的根目錄
1. 以下提供範例，只提示，不修改代碼

```javascript
// eslint.config.mjs
import tseslint from 'typescript-eslint';
import globals from 'globals';

export default [
    {
        files: [
            'assets/**/*.ts'
        ],
    },

    ...tseslint.configs.recommended,

    {
        languageOptions: {
            globals: {
                ...globals.browser
            }
        },
        rules: {
            // eslint規則
            'prefer-arrow-callback': 'warn', // 建議使用箭頭函數作為callback
            'prefer-const': 'warn', // 建議使用const
            'no-var': 'warn', // 建議使用let或const
            'no-undef': 'warn', // 禁止使用未定義的變數
            // TypeScript規則
            '@typescript-eslint/no-unused-expressions': ['warn', { allowShortCircuit: true }], // 禁止無效的表達式
            '@typescript-eslint/no-unsafe-function-type': 'warn', // 禁止將 any 型別函數作為其他函數使用，避免不安全的函數操作
            '@typescript-eslint/no-unused-vars': 'warn', // 檢查未使用的變數或參數
            '@typescript-eslint/no-explicit-any': 'warn', // 禁止使用 any 型別
            '@typescript-eslint/no-empty-function': 'warn', // 禁止空函數
            '@typescript-eslint/ban-ts-comment': 'warn', // 禁止使用 @ts-ignore/@ts-expect-error 注解
            '@typescript-eslint/no-namespace': 'warn', // 禁止使用 TS 的 namespace/declare module，鼓勵使用 ES module
            // 命名規則
            '@typescript-eslint/naming-convention': [
                'warn',
                {
                    selector: 'default',
                    format: ['camelCase', 'PascalCase', 'UPPER_CASE'],
                    leadingUnderscore: 'allow',
                },
                {
                    selector: 'typeLike',
                    format: ['PascalCase'],
                },
                {
                    selector: 'interface',
                    format: ['PascalCase'],

                    custom: {
                        regex: '^I[A-Z]',
                        match: true,
                    },
                },
                {
                    selector: 'enumMember',
                    format: ['UPPER_CASE'],
                },
            ],
        },
    },

    {
        ignores: [
            'eslint.config.mjs', // 排除一下這份文件, 不然被命名規則標記了
            'library/',
            'temp/',
            'local/',
            'build/',
            'node_modules/',
        ],
  },
];

```

### 1-4 VSCode 安裝插件
1. ESLint (by Microsoft)
1. 可以嘗試將上面的文件中 warn 改為 error 看看效果，確認是否有吃到 eslint.config.mjs 的配置
```javascript
'@typescript-eslint/no-unused-vars' : 'error'
```

## 2 Prettier


### 2-1 透過 npm 安裝套件
```sh
npm install --save-dev prettier
npm install --save-dev eslint-config-prettier
```


### 2-2 VSCode 安裝插件
1. Prettier


### 2-3 編輯rc檔案
1. 配置檔案檔名為 .prettierrc
1. 放在根目錄
```json
// .prettierrc
{
    "printWidth": 120,
    "tabWidth": 4,
    "singleQuote": true,
    "semi": true,
    "bracketSpacing": true,
    "trailingComma": "es5",
    "arrowParens": "always",
    "endOfLine": "lf"
}

```

### 2-4 調整 VSCode 設定
1. editor.defaultFormatter 調整為 Prettier - Code Formatter (esbenp.prettier-vscode)
1. editor.formatOnSave 勾起 (true)


### 試著在 VSCode 中儲存檔案試試