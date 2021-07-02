# macOS怎么重装Node.js

## 利用homebrew来管理nvm，然后再利用nvm管理node.js

### Uninstall

1. 删除 `/usr/local/lib` 下的任意 `node` 和 `node_modules` 的文件或目录

2. 删除 `/usr/local/include` 下的任意 `node` 和 `node_modules` 的文件或目录

3. 删除 `Home` 目录下的任意 `node` 和 `node_modules` 的文件或目录

4. 删除 `/usr/local/bin` 下的任意 `node` 的可执行文件

   可以使用一下命令代替以上繁琐的工作：

#### 第一种方式：

```ruby
$ sudo rm -rf /opt/local/bin/node /opt/local/include/node /opt/local/lib/node_modules
$ sudo rm -rf/usr/local/bin/npm/usr/local/share/man/man1/node.1/usr/local/lib/dtrace/node.d
```

#### 第二种方式：

```ruby
$ sudo rm -rf /usr/local/{bin/{node,npm},lib/node_modules/npm,lib/node,share/man/*/node.*}

```

#### 第三种方式：

```ruby
$ sudo rm -rf ~/.npm
$ sudo rm -rf ~/node_modules
$ sudo rm -rf ~/.node-gyp
$ sudo rm /usr/local/bin/node
$ sudo rm /usr/local/bin/npm
$ sudo rm /usr/local/lib/dtrace/node.d
```

以上三种任选其一，然后测试nvm，node，npm的命令是否依然存在。

```bash
brew uninstall node
```

### nvm

以前手动安装的nvm，可以通过以下的命令删除

```bash
$ rm -rf ~/.nvm
$ rm -rf ~/.npm
$ rm -rf ~/.bower
```

个人并不推荐使用官方安装包，手动控制版本太大

### homebrew安装

#### 1. 安装nvm，然后使用nvm控制node.js版本

```bash
brew install nvm
```

#### 2. 安装完成后，在`~/.bash_profile` 中添加以下内容，就可以在 bash 里面用 `nvm` 命令

```bash
// 安装 Node.js
source $(brew --prefix nvm)/nvm.sh
```

#### 3. 更新.bash_profile文件缓存，使修改生效

```bash
source ~/.bash.profile
```

#### 4. 通过nvm安装node.js

```bash
nvm install node
```

#### 5. 查看是否安装成功

```bash
$ nvm --version
0.34.0
$ nvm list
		v12.0.0
node -> stable (-> v12.0.0) (default)
stable -> 12.0 (-> v12.0.0) (default)
iojs -> N/A (default)
unstable -> N/A (default)
lts/* -> lts/dubnium (-> N/A)
lts/argon -> v4.9.1 (-> N/A)
lts/boron -> v6.17.1 (-> N/A)
lts/carbon -> v8.16.0 (-> N/A)
lts/dubnium -> v10.15.3 (-> N/A)
$ node -v
v12.0.0
$ npm -v
6.9.0
```

#### 6. 安装npm，推荐使用淘宝NPM镜像

```bash
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

### 注意：

通过 brew 管理 nvm，再通过 nvm 管理 node，如果安装过后提示 node 或 npm 命令找不到，应该是之前没删干净，尝试删除干净后，再重新安装 node 或 nvm即可。
