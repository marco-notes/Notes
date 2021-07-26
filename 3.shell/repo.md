windows 安装repo环境

参考网站：https://source.android.com/setup/develop

创建aosp目录
git bash下运行命令

1. 准备repo命令
mkdir ~/bin
//执行完此命令后，会创建如下目录/c/Users/admin/bin
curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
>chmod a+rx ~/bin/repo

2. 在/d/root/android/下创建如下目录：
>mkdir .\aosp_code
>cd aosp_code
>mkdir .repo
>cd .repo

3. 拉取repo仓库
git clone https://gerrit.googlesource.com/git-repo

有可能报如下错误：
Cloning into 'git-repo'...
fatal: unable to access 'https://gerrit.googlesource.com/git-repo/': Failed to connect to gerrit.googlesource.com port 443: Timed out
这有可能是连接的vpn端口号引起的问题

解决方法：
查看自己vpn的端口号设置，例如蓝灯的
设置->高级设置->HTTP(S)代理服务器：127.0.0.1:51663
执行如下命令：
 >git config --global http.proxy 127.0.0.1:51663

 重新尝试执行：
>git clone https://gerrit.googlesource.com/git-repo
然后执行
>mv git-repo repo
>cd ..

4. 拉取aosp code
回到aosp_code目录下
repo init -u https://android.googlesource.com/platform/manifest





