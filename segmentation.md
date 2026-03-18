## 安装必要软件
  google 搜索并下载对应最新的安装包安装即可
  ```bash
  # 命令行工具
  git bash
  # 远程虚拟桌面工具
  Xpra
  ```

## 启动流程
  - 在本地命令行 `git bash`（或者其他的命令行工具）内，启动 Xpra 连接远程服务器虚拟桌面
    ```bash
    Xpra attach tcp:10.1.20.27:14500 --resize-display=no
    ```
    或者如果 Xpra 执行程序不在环境变量中，需要手动在指定 Xpra 可执行程序的路径，以 `C:\Program Files\Xpra\xpra.exe` 为例
    ```bash
    "C:\Program Files\Xpra\xpra.exe" attach tcp:10.1.20.27:14500 --resize-display=no
    ```
