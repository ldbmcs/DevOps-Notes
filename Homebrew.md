## 1. 清华镜像：[https://mirrors.tuna.tsinghua.edu.cn/help/homebrew/](https://mirrors.tuna.tsinghua.edu.cn/help/homebrew/)

### **首次安装 Homebrew**

首先，下载安装脚本的镜像（也可以直接从官方下载，即 `https://raw.githubusercontent.com/Homebrew/install/master/install.sh` ）：

```bash
git clone https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/install.git
cd install
```

并编辑其中的 `install.sh`：

```bash
BREW_REPO="https://github.com/Homebrew/brew"
# 改成：
BREW_REPO="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git"
```

接着，运行 `install.sh` 以安装 Homebrew：

```bash
HOMEBREW_CORE_GIT_REMOTE=https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git bash install.sh
```

这样在首次安装的时候也可以使用镜像。

### **替换现有上游**

```bash
# brew 程序本身，Homebrew/Linuxbrew 相同
git -C "$(brew --repo)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git

# 以下针对 mac OS 系统上的 Homebrew
git -C "$(brew --repo homebrew/core)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git
git -C "$(brew --repo homebrew/cask)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-cask.git
git -C "$(brew --repo homebrew/cask-fonts)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-cask-fonts.git
git -C "$(brew --repo homebrew/cask-drivers)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-cask-drivers.git

# 以下针对 Linux 系统上的 Linuxbrew
git -C "$(brew --repo homebrew/core)" remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/linuxbrew-core.git

# 更换后测试工作是否正常
brew update
```

### **复原**

*(感谢Snowonion Lee提供说明)*

```bash
# brew 程序本身，Homebrew/Linuxbrew 相同
git -C "$(brew --repo)" remote set-url origin https://github.com/Homebrew/brew.git

# 以下针对 mac OS 系统上的 Homebrew
git -C "$(brew --repo homebrew/core)" remote set-url origin https://github.com/Homebrew/homebrew-core.git
git -C "$(brew --repo homebrew/cask)" remote set-url origin https://github.com/Homebrew/homebrew-cask.git
git -C "$(brew --repo homebrew/cask-fonts)" remote set-url origin https://github.com/Homebrew/homebrew-cask-fonts.git
git -C "$(brew --repo homebrew/cask-drivers)" remote set-url origin https://github.com/Homebrew/homebrew-cask-drivers.git

# 以下针对 Linux 系统上的 Linuxbrew
git -C "$(brew --repo homebrew/core)" remote set-url origin https://github.com/Homebrew/linuxbrew-core.git

# 更换后测试工作是否正常
brew update
```

## 2. 中科大镜像：[https://mirrors.ustc.edu.cn/help/homebrew-core.git.html](https://mirrors.ustc.edu.cn/help/homebrew-core.git.html)

1. Homebrew Bottles 源使用帮助：[https://mirrors.ustc.edu.cn/help/homebrew-bottles.html](https://mirrors.ustc.edu.cn/help/homebrew-bottles.html)
2. Homebrew Core 源使用帮助：[https://mirrors.ustc.edu.cn/help/homebrew-core.git.html](https://mirrors.ustc.edu.cn/help/homebrew-core.git.html)
3. Homebrew Cask 源使用帮助：[https://mirrors.ustc.edu.cn/help/homebrew-cask.git.html](https://mirrors.ustc.edu.cn/help/homebrew-cask.git.html)
4. Homebrew Cask Versions 源使用帮助：[https://mirrors.ustc.edu.cn/help/homebrew-cask-versions.git.html](https://mirrors.ustc.edu.cn/help/homebrew-cask-versions.git.html)