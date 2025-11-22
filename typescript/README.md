# Typescript 開發環境


## 1 專案結構
```
/project
    |- /node_modules
    |- /dist
    |- /src
        |- index.ts
    |
    |- project.json
    |- tsconfig.json
```



## 2 配置專案的 project.json

### 2-1 建立 project.json
1. 終端機輸入
    ```sh
    npm init -y
    ```

### 2-2 添加套件
1. 終端機輸入
    ```sh
    npm install typescript @ts-node --dev-sav
    ```

### 2-3 添加腳本
1. 在 pakage.json內的 scripts 添加
    ```json
    {
        "scripts": {
            "build": "npx tsc",
            "start": "node ./dist/index.js",
            "init": "npx tsc --init",
            "test": "echo \"Error: no test specified\" && exit 1"
        }
    }
    ```


## 3 配置專案的 tsconfig.json

### 3-1 建立 tsconfig.json

1. 在專案的根目錄建立檔案 tsconfig.json
    1. vim tsconfig.json
    1. npx tsc --init

1. 複製以下配置並貼入 tsconfig.json
    ```json
    {
        "compilerOptions": {
            "rootDir": "./src",
            "outDir": "./dist",
            "module": "commonjs",
            "target": "esnext",
            "types": [],
            "noUncheckedIndexedAccess": true,
            "exactOptionalPropertyTypes": true,

            // Style Options
            "noImplicitReturns": true,
            "noImplicitOverride": true,
            "noUnusedLocals": true,
            "noUnusedParameters": true,
            "noFallthroughCasesInSwitch": true,
            "noPropertyAccessFromIndexSignature": true,

            // Recommended Options
            "strict": true,
            "verbatimModuleSyntax": true,
            "isolatedModules": true,
            "noUncheckedSideEffectImports": true,
            "moduleDetection": "force",
            "skipLibCheck": true,
        }
    }

    ```




## 4 開發

