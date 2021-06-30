# Homebrew更换阿里云镜像源

### 使用阿里云Homebrew镜像源进行加速

- brew.git
- homebrew-core.git
- homebrew-bottles

建议将以上3个仓库全部换成阿里云提供的镜像源

#### 替换 brew.git

```bash
cd "$(brew --repo)"

git remote set-url origin https://mirrors.aliyun.com/homebrew/brew.git
```

#### 替换 homebrew-core.git

```bash
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"

git remote set-url origin https://mirrors.aliyun.com/homebrew/homebrew-core.git

brew update
```

### 查看配置信息 brew config

```java
HOMEBREW_VERSION: 2.1.5
ORIGIN: https://mirrors.aliyun.com/homebrew/brew.git
HEAD: db58b9f41b70a331dbe9b8371527a23e8ddcc718
Last commit: 2 days ago
Core tap ORIGIN: https://mirrors.aliyun.com/homebrew/homebrew-core.git
Core tap HEAD: 5e2a0aaa5fb49aeb4a820ab085f0e53f4de14371
Core tap last commit: 23 hours ago
HOMEBREW_PREFIX: /usr/local
CPU: dodeca-core 64-bit kabylake
Homebrew Ruby: 2.3.7 => /System/Library/Frameworks/Ruby.framework/Versions/2.3/usr/bin/ruby
Clang: 11.0 build 1100
Git: 2.21.0 => /usr/local/bin/git
Curl: 7.54.0 => /usr/bin/curl
Java: 1.8.0_211
macOS: 10.14.6-x86_64
CLT: 11.0.0.0.1.1559496560
Xcode: N/A
CLT headers: 11.0.0.0.1.1559496560
```

### 替换 homebrew-bottles

macOS中shell版本有zsh，bash两种版本，以下通过bash版本演示

```zsh
echo $SHELL
// zsh
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.aliyun.com/homebrew/homebrew-bottles' >> ~/.zshrc
source ~/.zshrc
```

```bash
// bash
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.aliyun.com/homebrew/homebrew-bottles' >> ~/.bash_profile

source ~/.bash_profile
```

以上就是更换brew三大组件的过程，接下来直接就使用 安装/卸载命令

- brew install  xx  --cask
- brew uninstall  xx  --cask
- brew install  xx
- brew uninstall  xx
