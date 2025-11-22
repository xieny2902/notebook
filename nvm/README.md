# nvm

1. Node Version Manager，用於管理 node 版本。
1. 不要使用 homebrew 安裝


## 1 安裝

1. 在終端機輸入安裝指令

    ```sh
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
    ```

1. 安裝完畢後 .nvm目錄 與 .zshrc 尚未添加路徑，因此執行 nvm 會報錯

1. 在 ~/.zshrc 檔案內添加代碼

    ```sh
    export NVM_DIR="$HOME/.nvm"
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
    [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
    ```

1. 執行指令確認 nvm 是否安裝成功

    ```sh
    nvm -v
    nvm --version
    ```


## 2 操作

### 2-1 安裝最新版本 node

    ```
    nvm install latest
    ```

### 2-2 列出已安裝 node 清單

    ```
    nvm ls
    nvm list
    ```

### 2-3 列出遠端可安裝 node 清單

    ```
    nvm ls-remote
    nvm list-remote
    ```

### 2-4 安裝指定版本的 node

    ```
    nvm install [node版本]
    nvm install 20
    ```

### 2-5 刪除指定版本的 node

    ```
    nvm uninstall [node版本]
    nvm uninstall 20
    ```

### 2-6 使用指定版本的 node

    ```
    nvm use [node版本]
    nvm use 20
    ```

### 2-7 指定命令列預設的 node 版本

    ```
    nvm alias default [node版本]
    nvm alias default 10
    ```

### 2-8 查詢當前使用 node 版本

    ```
    nvm use node
    ```


## 參考
- [安裝 nvm 環境，Node.js 開發者必學（Windows、Mac 均適用）](https://www.casper.tw/development/2022/01/10/install-nvm/)
- [macOS 安裝 NVM 與 Node.js](https://echocarrie.com/tools/20230327/3371717253/)
