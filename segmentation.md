## 安装必要软件
    google 搜索并下载对应最新的安装包安装即可
    ```bash
    # 命令行工具
    git bash
    # 远程虚拟桌面工具
    Xpra
    ```

## 启动流程
  - 在本地命令行 `git bash`（或者其他的命令行工具）内，启动 Xpra 连接远程服务器虚拟桌面，`10.1.20.27` 为实验室 A100 服务器内网地址
    ```bash
    Xpra attach tcp:10.1.20.27:14500 --resize-display=no
    ```
    或者如果 Xpra 执行程序不在环境变量中，需要手动在指定 Xpra 可执行程序的路径，以 `C:\Program Files\Xpra\Xpra.exe` 为例
    ```bash
    "C:\Program Files\Xpra\Xpra.exe" attach tcp:10.1.20.27:14500 --resize-display=no
    ```

  - 启动服务器虚拟桌面后，在桌面上右键，选择 `open terminal here` 打开一个服务器终端，启动 cellpose 运行环境并运行 cellpose GUI 界面

    激活 cellpose4 虚拟环境
    ```bash
    conda activate cellpose4
    ```
    查看 GPU 使用情况，单节点服务器共 8 张 GPU，编号 0-7
    ```bash
    nvidia-smi
    ```
    在终端内启动 cellpose GUI
    ```bash
    # 默认使用第一张 GPU
    python -m cellpose
    # 手动指定使用第 4 张 GPU （编号3）
    CUDA_VISIBLE_DEVICES=3 python -m cellpose
    ```

  - 数据位于 `/data/W00xx` 路径下
