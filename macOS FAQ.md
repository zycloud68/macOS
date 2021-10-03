### 当程序已损坏无法打开，你应该把它移到垃圾篓
#### 解决办法:
1. 打开macOS Mojave终端

2. 输入一下命令,回车:

   ```bash
   sudo xattr -d com.apple.quarantine /Applications/xxxx.app
   # 注意：/Applications/xxxx.app 换成你的App路径（推荐打开访达，点击应用程序，找到打不开的程序，然后直     接将.app文件拖入终端中自动生成路径，以防空格等转义字符手动复制或输入出现错误。
   ```
3. 重启app
