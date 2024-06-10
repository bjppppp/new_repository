# GitHub


## 关键字查询：

xx（python）awesome：查该标签下的xx（python）项目<br>
xx（python）tutorial：查询xx（python）资料、书籍、文档<br>
xx（socket）sample：查询对应技术（socket）的代码样本<br>

## GitHub三要素：

### Repository 仓库：
仓库是github项目管理存储基本单位一个仓库中存储一个项目，
一个用户可以拥有多个仓库，一般仓库分为public，private

### Commit 提交
程序员在整个开发周期，有大量的对代码资源的选代和修改，
都可以通过commit的方式进行记录,便于程序员回溯代码,
即使这些代码被删除。
提交便于使用者观察整个工程的开发流程以及设计流程

### Branch 分支
在仓库中可以包含多个分支，分支才是代码文件的第一存储单位，
默认的仓库主分支为master/main
* 不仅可以管理代码存储，而且便于多人协作开发

## 仓库内容

Code，资源存储，代码资源，二进制，项目管理脚本，许可证等等

issues，使用时遇到的bug或进行提交，等待反馈

README，使用markdown语言编写，工程自述文件，开发进度，，版本更新，使用介绍等等

LICENSE许可证:GPL2.0,3.0.Apahce 2.0，Mit，这些许可证，给使用者最大使用权限以及最少的限制

## Git软件，分布式版本控制系统
仓库管理软件，使用git管理私人代码或企业代码

## 设备认证

### 1、让网站的账户与设备绑定，后续完成代码的管理，上传下载

```bash
git init    // 创建本地仓库，后续对仓库的操作，都要在仓库位置（master）

```

```bash
git config -list    、、查看git配置文件

```

#### 修改或添加config配置项

```bash
git config --global user.name   //用户名
git config --global user.email  //注册邮箱

```

#### 生成本机设备密文

```bash
ssh-keygen -t rsa -C "注册邮箱"  # 创建本地密文，去对应的目录下查找密文文件

```
rsa.pub 复制密文，粘贴到setting->SSH key and GPG->new ssh key->粘贴

#### 测试关联是否完成

```bash
ssh -T git@github.com   # ssh远程登录 

```
### 2、为目标仓库起别名，定位目标仓库，后续上传

```bash
git remote add orgin(别名) SSH地址(云端仓库地址)

git remote remove origin  #删除地址别名

```
## 本地设备与云端仓库的交互逻辑

```bash
git add code.c

```

```bash
#将缓冲区数据提交到本地仓库
git commit   #提交到本地仓库

git commit -m "备注信息"     #生成提交记录

```
```bash
git push origin(云端仓库地址) master   #将本地仓库内容推到云端仓库

```

```bash
git status	#查看状态
```

```bash
git rm code.c	#删除本地文件及仓库文件
```
```bash
git restore code.c 	#复位误删除文件（仓库存在）
```

## 代码更新的依赖关系被破坏
本地内容要比云端新，完成更新替换，但是如果直接修改云端内容，
导致本地内容无法再次提交

### 先拉去git pull 云端内容 与 本地内容合并或操作，而后再次推即可
```bash
git pull --rebase origin master
```

```bash
git rebase --abort  	
#将引起冲突的commits丢弃掉

git rebase --skip	
#执行之后，本地内容会回到提交之间的状态，也就是回到以前提交但没有pull是的状态，简单来说就是撤销rebase
			
git rebase --continue 	
#合并冲突，结合"git add 文件"命令一起用与修复冲突，提示开发者，一步一步地有没有解决冲突。

```
## 下载开源代码
git clone "https仓库地址"	#下载开源项目code资源

## 分支Branch
关于分支的相关命令，创建分支，选择分支，合并分支等等

