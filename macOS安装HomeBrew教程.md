# macOS安装HomeBrew教程
### 一. Homebrew国内如何自动安装（国内地址）
##### 1. 全部安装国内地址的版本
```
/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"
```
##### 2. 精简版本
```
/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)" speed
```
##### 3. 卸载
```
/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/HomebrewUninstall.sh)"
```
### 二. Homebrew国内镜像配置(针对于在官方安装homebrew的童鞋)
- Bash终端
```
# 替换brew.git:
cd "$(brew --repo)"
git remote set-url origin https://mirrors.aliyun.com/homebrew/brew.git
# 替换homebrew-core.git:
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.aliyun.com/homebrew/homebrew-core.git
# 应用生效
brew update
# 替换homebrew-bottles:
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.aliyun.com/homebrew/homebrew-bottles' >> ~/.bash_profile
source ~/.bash_profile
```
- Zsh终端
```
# 替换brew.git:
cd "$(brew --repo)"
git remote set-url origin https://mirrors.aliyun.com/homebrew/brew.git
# 替换homebrew-core.git:
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.aliyun.com/homebrew/homebrew-core.git
# 应用生效
brew update
# 替换homebrew-bottles:
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.aliyun.com/homebrew/homebrew-bottles' >> ~/.zshrc
source ~/.zshrc
```
- 恢复默认官网配置
```
# 替换brew.git:
cd "$(brew --repo)"
git remote set-url origin https://mirrors.aliyun.com/homebrew/brew.git
# 替换homebrew-core.git:
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.aliyun.com/homebrew/homebrew-core.git
# 应用生效
brew update
# 替换homebrew-bottles:
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.aliyun.com/homebrew/homebrew-bottles' >> ~/.zshrc
source ~/.zshrc
```
- 删掉 HOMEBREW_BOTTLE_DOMAIN 环境变量
```
~/.bash_profile  // bash终端
~/.zshrc         // zsh终端
HOMEBREW_BOTTLE_DOMAIN 这一行删掉
执行 source ~/.bash_profile || source ~/.zshrc9
```
### homebrew cask
[Homebrew Cask](https://formulae.brew.sh/cask/)

### 应用升级
首先执行brew update命令，可以看到那些需要更新的命令
```java
$ brew upgrade              # 更新所有
$ brew upgrade <package>    # 更新指定软件
```
然后执行brew upgrade xxx 执行需要更新的包，例如更新iterm2就是
```bash
brew upgrade iterm2
```
### 应用安装卸载
```bash
$ brew install <package>
$ brew install  <package> --cask
```
以上搜索命令，可以看到搜索关键词 google，结果会出现 Formulae 和 Casks 两种分类，有何区别？
```bash
「Formulae」一般是那些命令行工具、开发库、字体、插件等不含 GUI 界面的软件。
「Cask」是指那些含有 GUI 图形化界面的软件，如 Google Chrome、FireFox 、Atom 等。
```

