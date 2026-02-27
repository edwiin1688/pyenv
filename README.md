# 🐍 pyenv-win: 輕鬆駕馭 Python 版本切換

在使用 Python 開發時，不同的專案往往需要特定的 Python 版本。`pyenv-win` 是 Windows 環境下管理多個 Python 版本的最佳利器！讓您能隨心所欲地在多個版本間快速切換。🚀

---

## 📥 使用 git clone 安裝 pyenv 

首先，將 `pyenv-win` 複製到您的家目錄下：

```shell
git clone https://github.com/pyenv-win/pyenv-win.git "$HOME/.pyenv"
```

## ⚙️ 設定環境變數 (只需執行一次)

請使用 **PowerShell** 執行以下指令，這會自動完成環境變數配置，讓系統能正確識別 `pyenv`：

```powershell
[System.Environment]::SetEnvironmentVariable('PYENV',$env:USERPROFILE + "\.pyenv\pyenv-win\","User")
[System.Environment]::SetEnvironmentVariable('PYENV_HOME',$env:USERPROFILE + "\.pyenv\pyenv-win\","User")
[System.Environment]::SetEnvironmentVariable('path', $env:USERPROFILE + "\.pyenv\pyenv-win\bin;" + $env:USERPROFILE + "\.pyenv\pyenv-win\shims;" + [System.Environment]::GetEnvironmentVariable('path', "User"),"User")
```

> [!TIP]
> 設定完成後，請**重新啟動**您的終端機（如 PowerShell 或 cmd）以套用變更。✨

## 🔍 確認安裝狀態

檢查 `pyenv` 是否安裝成功及查看目前的版本資訊：

```shell
pyenv --version
```

---

## 🛠️ 常用指令指南

### 📋 檢視版本資訊
*   **檢視目前已安裝的所有版本**：  
    ```shell
    pyenv versions
    ```
*   **列出網路上所有可供安裝的版本**：  
    ```shell
    pyenv install -l
    ```

### 📥 安裝與切換版本
*   **安裝特定版本的 Python** (例如 3.10.11)：
    ```shell
    pyenv install 3.10.11
    ```
*   **設定全域版本** (作為系統預設使用的版本)：
    ```shell
    pyenv global 3.10.11
    ```
*   **設定專案區域版本** (僅對當前目錄及其子目錄生效)：
    ```shell
    pyenv local 3.10.11
    ```

### 🔄 環境刷新 (rehash)
當您使用 `pip` 安裝或卸載程式庫，或是手動更改了特定的 Python 版本資料夾內容時，必須執行 `rehash` 指令來通知 `pyenv` 更新連結：

```shell
pyenv rehash
```

---
💡 **溫馨提示**：養成使用 `pyenv` 管理版本的習慣，能有效避免開發環境衝突帶來的困擾喔！☕
