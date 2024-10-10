# Anaconda-Install

下面是从头开始安装 Anaconda 的详细步骤，适用于 Windows、macOS 和 Linux 操作系统。我们以 Windows 为例，其他系统的步骤也大同小异。

### 1. 下载 Anaconda

- 打开 [Anaconda 官方下载页面](https://www.anaconda.com/products/distribution)。
- 选择与你的操作系统（Windows、macOS 或 Linux）相对应的安装包，并选择 Python 版本（通常建议下载最新版本的 Python）。
  - 对于 Windows 用户，下载 `.exe` 安装文件。
  - 对于 macOS 和 Linux 用户，下载相应的 `.pkg` 或 `.sh` 文件。

### 2. 安装 Anaconda

#### **Windows 安装步骤**：

1. **运行安装程序**：找到下载的 `.exe` 文件，并双击它开始安装。
2. **安装选项**：
   - 在安装向导中点击 "Next"。
   - 阅读并接受许可协议。
   - 选择安装用户：
     - 选择 “Just Me” (推荐) 或 "All Users"。
   - 选择安装路径：可以使用默认路径，也可以自定义安装位置（建议保持默认设置）。
3. **设置 PATH 选项**：
   - 安装过程中会出现两个复选框：
     - *Add Anaconda3 to my PATH environment variable*：建议 **不勾选**。这可以避免与系统中的其他 Python 安装发生冲突。
     - *Register Anaconda3 as my default Python 3.8*（或其他版本）：建议 **勾选**，这将 Anaconda 的 Python 设为默认 Python 版本。
4. **点击 Install** 开始安装。
   - 安装过程需要几分钟。
5. 安装完成后，可以选择是否安装微软的 VS Code 编辑器（可选）。如果你已经有合适的 IDE，可以跳过这个步骤。

#### **macOS / Linux 安装步骤**：

- 打开终端，并使用 `bash` 命令运行安装脚本，例如：

  ```bash
  bash Anaconda3-2024.XX-MacOSX-x86_64.sh
  ```

  或者 Linux 上类似的 `.sh` 文件。

- 按照终端提示的步骤，阅读并接受许可协议，然后选择安装路径。

- 安装完成后，可以根据提示运行以下命令来激活 Conda：

  ```bash
  source ~/.bashrc
  ```

### 3. 添加环境变量

设置系统变量是使 Anaconda 的 Python 和 `conda` 命令在命令行（如 Windows 的 CMD 或 PowerShell）中可用的一步。如果在安装过程中没有勾选“Add Anaconda3 to my PATH environment variable”选项，可以手动设置系统变量。

#### **在 Windows 中设置系统变量**

1. **打开系统属性**：

   - 右键点击 "此电脑"（或者 "计算机"）图标，然后选择 "属性"。
   - 点击左侧的 "高级系统设置"，进入 "系统属性" 窗口。
   - 在 "系统属性" 窗口的 "高级" 标签下，点击 "环境变量" 按钮。

2. **编辑 PATH 变量**：

   - 在 "环境变量" 窗口中，找到 “系统变量” 下的 `Path` 变量，然后点击 “编辑”。
   - 在 "编辑环境变量" 窗口中，点击 "新建"，然后将 Anaconda 的安装路径添加到 PATH 变量中。

3. **添加路径**：
   根据你的安装位置，添加以下两条路径：

   - Anaconda 主目录路径，比如：

     ```bash
     D:\Anaconda3
     ```

   - 以及 Anaconda 的 `Scripts` 目录，比如：

     ```bash
     D:\Anaconda3\Scripts
     ```

     如果你还想让系统默认使用 `conda` 的 Python，可以添加：

   - Anaconda 的 `bin` 目录，比如：

     ```bash
     D:\Anaconda3\Library\bin
     ```

4. **保存设置**：

   - 点击 "确定" 保存对 `Path` 变量的修改。
   - 在所有窗口中点击 "确定" 完成系统变量的设置。

5. **验证设置**：

   - 重新打开命令行（如 CMD 或 PowerShell），输入 `conda --version` 和 `python --version`，验证是否可以全局调用 `conda` 和 Anaconda 的 Python。如果看到版本信息说明配置成功。

#### **在 macOS / Linux 中设置系统变量**

1. **编辑 shell 配置文件**：
   打开终端，编辑你的 `.bashrc` 或 `.zshrc` 文件（取决于你使用的 shell）：

   ```bash
   nano ~/.bashrc
   ```

   或者：

   ```bash
   nano ~/.zshrc
   ```

2. **添加 Anaconda 路径**：
   在文件末尾添加以下内容：

   ```bash
   export PATH="/home/your_username/anaconda3/bin:$PATH"
   ```

   这里的路径应该替换为你实际安装 Anaconda 的路径。

3. **保存并生效**：
   保存文件后，运行以下命令使其生效：

   ```bash
   source ~/.bashrc
   ```

   或者对于 `zsh`：

   ```bash
   source ~/.zshrc
   ```

4. **验证**：
   输入 `conda --version` 和 `python --version`，验证是否可以正确调用 `conda` 和 Anaconda 的 Python。

这样，系统变量就设置好了，`conda` 和 Anaconda 的 Python 都可以在全局环境中使用了。如果过程中遇到任何问题，随时可以问我！

### 4. 验证 Anaconda 安装

在安装完成后，你可以通过以下方式验证安装是否成功。

#### **在 Windows 上**：

- 打开 “Anaconda Navigator”：

  - 安装完成后，在开始菜单中搜索并打开 `Anaconda Navigator`。这是 Anaconda 的图形界面管理器，方便管理环境和安装包。

- **命令行方式**：

  - 打开 “Anaconda Prompt” 或 Windows 命令行，输入以下命令查看安装的 Python 版本：

    ```bash
    python --version
    ```

    你应该看到 Anaconda 自带的 Python 版本号，比如 `Python 3.X.X :: Anaconda, Inc.`。

#### **在 macOS / Linux 上**：

- 打开终端，输入以下命令来激活 `base` 环境并查看 Python 版本：

  ```bash
  conda activate
  python --version
  ```

  应该显示 Anaconda 自带的 Python 版本。

### 5. 基本 Conda 使用

你现在已经成功安装了 Anaconda。下面是一些基础命令，用于创建虚拟环境和安装包。

- **查看已安装的 Conda 版本**：

在任何时候，你可以检查 Conda 的版本，以确保你正在使用正确的版本。打开命令行（如 `Anaconda Prompt`、`CMD` 或 `PowerShell`），然后输入：

  ```bash
  conda --version
  ```

- **创建虚拟环境**：

使用虚拟环境可以隔离不同项目所依赖的包，避免依赖冲突。创建一个新的 Conda 虚拟环境并指定 Python 版本（可以不指定，默认使用 Conda 自带的 Python 版本）：

  ```bash
  conda create -n myenv python=3.9
  ```

  - `myenv` 是虚拟环境的名字，可以根据你的需求进行更改。
  - `python=3.9` 指定安装 Python 3.9 版本，也可以根据需要选择其他版本。

- **激活虚拟环境**：

  在创建虚拟环境之后，你需要激活它才能使用该环境中的包和 Python 版本。使用以下命令激活环境：
  
  ```bash
  conda activate myenv
  ```
  
  激活后，命令行提示符通常会显示当前激活的环境名称（例如 `(myenv)`），表示你现在处于该虚拟环境中。

- **安装包**：

  在虚拟环境中，你可以使用 `conda install` 或 `pip install` 来安装包。  
  使用 `conda install` 来安装包（如安装 `numpy`）：

  ```bash
  conda install numpy
  ```

  这会从 Conda 的官方仓库下载并安装该包。如果某个包在 Conda 仓库中找不到，你可以使用 `pip install`：

  ```bash
  pip install some_package
  ```
  
- **安装特定版本的包**：

  如果你需要安装某个包的特定版本，可以使用以下命令：

  ```bash
  conda install numpy=1.19
  ```
  
- **查看已安装的包**：

  要查看当前虚拟环境中安装了哪些包，可以使用以下命令：

  ```bash
  conda list
  ```

- **更新包**：

  如果想更新已安装的包到最新版本，可以使用 `conda update`。例如，更新 `numpy`：
  
  ```bash
  conda update numpy
  ```
  
  Conda 会检查是否有新版本，并提供更新提示。

- **删除包**：

  如果想从环境中删除某个包，可以使用 `conda remove` 命令。例如，删除 `numpy`：
  
  ```bash
  conda remove numpy
  ```

- **查看已创建的虚拟环境**：

  要查看所有已创建的虚拟环境，可以使用以下命令：
  
  ```bash
  conda env list
  ```
  
  这会列出所有 Conda 管理的虚拟环境，以及它们对应的路径。

- **切换环境**：

  要切换到另一个已经创建的虚拟环境，只需使用 `conda activate`，例如：
  
  ```bash
  conda activate another_env
  ```
  
  这会切换到名为 `another_env` 的环境。

- **退出虚拟环境**：

  如果你完成了当前环境中的操作，可以使用以下命令退出虚拟环境，返回到默认的 `base` 环境或全局环境：
  
  ```bash
  conda deactivate
  ```

- **删除虚拟环境**：

  如果你不再需要某个虚拟环境，可以使用 `conda env remove` 命令来删除它：
  
  ```bash
  conda env remove -n myenv
  ```
  
  `myenv` 是你想要删除的环境的名字。删除后，该环境及其包都会被移除。
