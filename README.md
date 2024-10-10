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

- **创建虚拟环境**：

  ```bash
  conda create -n myenv python=3.9
  ```

  这会创建一个名为 `myenv` 的虚拟环境，并安装 Python 3.9。

- **激活环境**：

  ```bash
  conda activate myenv
  ```

  激活该环境后，你可以在其中安装和管理包。

- **安装包**：
  在激活的虚拟环境中，你可以使用 `conda install` 或 `pip install` 安装所需的库，例如安装 NumPy：

  ```bash
  conda install numpy
  ```

- **退出虚拟环境**：
  完成工作后，退出虚拟环境：

  ```bash
  conda deactivate
  ```
