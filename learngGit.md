# 学习内容

第一步，注册 github
第二步，安装 git
建议 git 的连接，百度学习

## 如何克隆（拉 github 的代码仓库到本地）

### 连接 git 和 github

0、初始设置
第一步：配置全局信息
安装完成后，打开 Git Hash 终端界面
输入如下内容：$ git config --gobal user.name "googjob"
输入如下内容：$ git config --gobal user.email "php.lk@hotmail.com"
第二步：生成 SSH key
$ssh-keygen -t rsa -C "你的GitHub邮箱名"
  提示内容
  $指定目录：如不输入，直接回车。默认存在路径C:\User\.ssh
  $输入密码：可回车，不输入
  $确认密码：可回国，不输入
  如此，即可在.ssh文件夹生成ssh keys。包括两个文件rd_rsa和id_rsa.pub，第一个是私有密钥，第二个是仅有密钥。
第三步：添加公开密钥
  使用命令查看或直接打开.ssh方便夹中的id_rsa.pub文件。$ cat ~/.ssh/id_rsa.pub
点击 GitHub 中的 setting，找到 SSH and GPG keys 菜单，点击 New SSH key ，在 Title 中输入密钥名称（随便填），在 key 里面粘贴 id_rsa.pub 里面的内容，点击 Add SSH key。
第四步：通信验证
$ ssh -T git@github.com
提示： “Hi googjob! You've successfully authenticated, but GitHub does not provide shell acess.”

0、查下是否连接成功
在终端里输入 ssh -T git@github.com
会提示你输入 yes or no
此时一定要输入 yes 而不是输入回车！！

如果出现提示：
git@github.com: Permission denied (publickey)
（打开文件夹 C:\Users\Administrator\.ssh（Administrator 是当前用户名），（文件中没有 id.rsa.pub）, 在空白处点鼠标右键选择“Git Bush Here” ，打开 gitbush）
解决方法：
1、打开终端 输入： $ ssh-keygen -t rsa -b 4096 -C "php.lk@hotmail.com" 连按三次回车。
2、再次检查.ssh 文件夹。确认本地是否出现 SSH 密钥: id_rsa 和 id_rsa.pub
3、新增 SSH 密钥到 GitHub 账户。用记事本打开 id_rsa.pub 文件，复制里面的内容。
4、登录 GitHub 并打开设置(Setting)，
5、点击 SSH and GPG keys 菜单，点击 New SSH key ，自定义名称(title)，粘贴密钥，点击 Add SSH key。
6、在终端里输入 ssh -T git@github.com 提示 “Hi googjob! You've successfully authenticated, but GitHub does not provide shell acess.”

### 克隆 github 的项目

1、电脑本地新建一个空文件夹"myblog"。在文件夹内右键，选择 git bash here
2、初始化本地仓库 git init 会出现提示
Initialized empty Git repository in D:/Web-Projets/Github/myblog/.git/
3、在 GitHub 上找到需要克隆的地址
4、克隆项目 在初始化后，输入克隆地址 git clone https://github.com/googjob/myblog.git
如果报错提示：fatal: unable to access 'https://github.com/googjob/test-site.git/': SSL certificate problem: unable to get local issuer certificate
解决办法：执行下面命令： git config --global http.sslVerify false

提示：看保存的截图文件。

### 本地项目上传到 github

第一步：在本地新建文件夹或已经克隆的项目文件夹，更新后。在文件夹内右键 git bash here
第二步：在打开的终端中输入以下命令：
image.png

## 分支相关的内容

1、

## 删除文件

1、

## 多仓库

1、

## 查看和修改关联的仓库

如何修改本地项目关联的远程仓库地址
1、在文件夹内右键，选择 git bash here
2、git remote -v // 查看当前的远程仓库
3、git remote set-url origin https://where you want to put your repository to.git（例：https://git.huatonghh.com/11/micro-store-front-pc.git）
// 修改为想要设置的远程仓库
4、再次查看 git remote -v
5、初始化本地仓库 git init

## 常见 git 命令

1、清屏
clear //
history -c //
reset //
2、退出
exit //
3、返回上一格
cd ..
4、查看有什么谁的
dir
ls

# 简易流程

## 打开 git hash

在放项目的文件夹右键，打开 Git Hash 终端

## 初始化

使用 git 命令：git init

## 添加到 git 本地库

使用 git 命令：git add .
将整个文件夹添加到本地库。
如何只添加变动的文件？如果只想添加单个文件使用命令：git add 文件名 ,这种方式 ,例如：git add test.txt.

## 查看是加入本地库

使用 git 命令：git status
绿色，已加入本地库；红色，未加入本地库。//绿色为显示添加到 git 中，但提示未 commit。

## 提交本地库

使用 git 命令：git commit -m "注释修改内容" //现在已添加到本地库。

## 使用 SSH\*\*连接本仓库和 github 远程仓库

git 本地文件和远程仓库之间的同步,使用的是 SSH 加密,所以如果是首次同步本地文件到 github,此时是没有 ssh 加密文件的,需要我们手动添加,首先使用命令: $ ssh-keygen -t rsa -C "youremail@example.com"
执行后一路回车（3 次）。可以在 C 盘自己用户名下.ssh 文件夹中有 id_rsa 和 id_rsa.pub

## 在 github 维护密钥

打开 github 个人中心 Settings，找到 SSH and GPG keys，点击 New SSH key,然后把刚才的公开密钥:id_rsa.pub 中的代码复制到 key 中，title 可以自定义。最后点击 Add SSH key。

## 创建 github 仓库

    接下来在github上创建一个新项目,在Clone or download中复制该项目的SSH地址，例git@github.com:yourname/filename.git(git@github.com:googjob/lovdx.git)

## 关联本地库和 github 库

使用 git 命令：git remote add origin git@github.com:googjob/lovdx.git

## 将本地项目上传到 github 远程仓库

### 远程仓库为空

第一次，使用 git 命令：git push -u origin master
非 1 次，使用 git 命令：git push origin master
-u 仅在第一次上传时加上，以后都不需要了。

### 远程仓库非空

如果你的远程仓库不是空的（初始化了一个 readme.md 文件）(//也可以理解成原来仓库中是有内容的)，而本地仓库没有，则必须有先把远程文件同步到本地，使用命令：git pull --rebase origin master，然后再上传（或者直接讲远程仓库克隆下来，往里面放文件也行，使用命令：git clone git@github.com:googjob/lovdx.git)，在使用推送命令：git push origin master .完成同步.

补充：
1、第一步，检查全局变量配置
git config --global --list
是否显示名称和邮箱。否，执行以下
git config --global username "googjob"
git config --global useremail "php.lk@hotmail"
2、检查连接
ssh -T git@github.com
若，未连接,检查是否没有 id_rsa_hub 文件。是，执行以下
生成 SSH key,并维护到 Github。
3、上传
git status 检查文件状态
git add . 全量重新上传
(git add 文件名.扩展名) 上传指定文件（如何上传多个，且非全量）
git commit -m "注释" 上传修改说明
git push origin master

# 全栈理念
1、解决用户需求，使用数据和功能。
2、步骤：分析用户需求》做产品设计》梳理数据和功能。
3、用户：我；用户需求：解决常用收藏网站问题。
对照测试 数据 用户调研 产品页面的合理设计 对真实世界的数据抽象 定义产品功能的使用逻辑  》》初级产品经理
》》中级PM能力：用户调研/数据分析/竞品分析/ab测试/合理结合/用户痛点和实际产品情况/跨学科思维深入思考需求  》中大型产品页面的拆解  》》 大量数据模型和函数功能梳理。
方案一：使用第三方的工具。数据账号第三方托管。

git remote -v
git pull
git status
git