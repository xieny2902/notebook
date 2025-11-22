# homebrew

homebrew 為 mac 的套件管理工具, 可以集中管理各式應用程式


## 1 安裝/卸載

### 1-1 安裝
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### 1-2 卸載
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/uninstall.sh)"
```

### 1-3 更新
```sh
brew update
```


## 2 套件管理

### 2-1 搜尋套件
```sh
brew search [套件名稱]
```

### 2-2 安裝套件
```sh
brew install [套件名稱]
```

### 2-3 卸載套件
```sh
brew uninstall [套件名稱]
```

### 2-4 更新已安裝套件
```sh
brew upgrade [套件名稱]
```

### 2-5 列出已安裝套件清單
```sh
brew list
```

### 2-6 清理過期暫存檔
```sh
brew cleanup
```

## 2-7 參考
- [官網](https://brew.sh/index_zh-tw)
