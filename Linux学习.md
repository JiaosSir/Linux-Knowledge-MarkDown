# Linux学习🫶❤️

## ✨ Linux小常识 ✨
+ __特殊路径符__
    - __\.__       表示当前目录
    - __\.\.__     表示上级目录
    - __~__        表示home目录

+ __通配符__
    - __\*__       表示通配符，匹配任何内容（包含空）
    - __\*test__   表示匹配任何以test结尾的内容
    - __test\*__   表示匹配任何以test开头的内容
    - __\*test\*__ 表示匹配任何包含test的内容

+ __管道符__
    - __|__        表示管道符，将左边的结果作为右边的输入

+ __反引号__
    - __\`__       表示反引号，被反引号包裹的文本将被当做命令执行

+ __重定向符__
    - __\>__       将符号左侧命令的结果 **覆盖** 写入符号右侧指定的文件
    - __\>\>__     将符号左侧命令的结果 **追加** 写入符号右侧指定的文件

+ __vim编辑器__
    ![vim编辑器工作模式](/images/vim编辑器工作模式.png "vim编辑器工作模式")  
    ![命令模式进入插入模式](/images/命令模式进入插入模式.png "命令模式进入插入模式")
    ![命令模式](/images/三种模式快捷键表格1.png "命令模式")
    ![命令模式](/images/三种模式快捷键表格2.png "命令模式")
    ![底线模式](/images/三种模式快捷键表格3.png "底线模式")

+ __权限的数字序号__
    ![权限的数字序号](/images/权限的数字序号.png "权限的数字序号")  

+ __快捷键小技巧__
    ![快捷键小技巧](/images/快捷键小技巧.png "快捷键小技巧")  


## ✨ Linux命令 ✨
+ __ls__
    **展示**文件和文件夹
    - _-a_ ：展示全部文件（包括隐藏文件）
    - _-l_ ：以列表形式平铺展开
    - _-h_ ：显示文件大小
```sh
ls [-a -l -h] Linux路径
```

+ __cd__ 
    切换路径 (Change Directory)
```sh
cd Linux路径
```

+ __pwd__ 
    **展示**当前工作目录 (Print Work Directory)
```sh
pwd
```

+ __mkdir__ 
    **创建**目录 (Make Directory)
    - _-p_ ：自动创建不存在的父级目录，用于多层级目录嵌套
```sh
mkdir [-p] Linux路径
```

+ __touch__ 
    **创建**文件
```sh
touch 文件路径
```

+ __cat__ 
    **查看**文件
```sh
cat 文件路径
```

+ __more__ 
    **查看**文件（大文件）(按下键盘q键退出查看)
```sh
more 文件路径
```

+ __cp__ 
    **复制**文件或文件夹(copy)
    - _-r_ ：用于复制文件夹，表示递归
    - 参数1： Linux路径，表示被复制的文件或文件夹
    - 参数2： Linux路径，表示复制的目标位置
```sh
cp [-r] 参数1 参数2
```

+ __mv__ 
    **移动**文件或文件夹(move)
    - 参数1： Linux路径，表示被移动的文件或文件夹
    - 参数2： Linux路径，表示移动的目标位置，若目标不存在则会进行重命名
```sh
mv 参数1 参数2
```

+ __rm__ 
    **删除**文件或文件夹(remove)
    - _-r_ ：用于删除文件夹，表示递归
    - _-f_ ：强制删除，不会弹确认信息
    - 参数1、参数2...参数n： Linux路径，表示删除的文件或文件夹
```sh
rm [-r -f] 参数1 参数2 ... 参数n
```

+ __which__ 
    查看命令程序的文件存放位置
```sh
which 命令
```

+ __find__ 
    **搜索**指定文件或文件夹
    - _+、-_  ：表示大于、小于
    - _n_  ：表示数字（文件大小数字）
    - _k、M、G_  ：表示文件大小单位，对应 kb、MB、GB
```sh
find 起始路径 -name 文件名
find 起始路径 -size +|-n[kMG]

find / -name test*
find / -size +10GB
```

+ __grep__ 
    通过关键字**过滤**指定文件行
    - _-n_ ：显示匹配的行号
```sh
grep [-n] 关键字 文件路径
```

+ __wc__ 
    **统计**指定文件的行数、单词数量等（默认-lwc）
    - _-c_ ：统计bytes数量
    - _-m_ ：统计字符数量
    - _-l_ ：统计行数
    - _-w_ ：统计单词数量
```sh
wc [-c -m -l -w] 文件路径
```

+ __echo__ 
    在命令行**输出**指定内容
```sh
echo 输出内容
```

+ __tail__ 
    **查看**文件尾部内容、**追踪**文件的最新更改
    - _-f_ ：  追踪文件
    - _-num_ ：查看尾部多少行，默认10行
```sh
tail [-f -num] 文件路径
```

+ __vi/vim__ 
    **编辑**文件
```sh
vi|vim 文件路径
```

+ __su__ 
    **切换用户**(Switch User)
    省略用户名默认切换至root
```sh
su - [用户名]
```

+ __sudo__ 
    为普通用户的命令授权，具有临时root权限（需配置）
```sh
sudo 其它命令
```

+ __groupadd__ 
    创建用户组（需root用户执行）
```sh
groupadd 用户组名
```

+ __groupdel__ 
    删除用户组（需root用户执行）
```sh
groupdel 用户组名
```

+ __useradd__ 
    添加用户（需root用户执行）
    - _-g_ ：  指定用户的组，不填-g，会创建同名组并自动加入。如果已存在同名组，必须使用-g；使用-g需要组已经存在
    - _-d_ ：  指定用户HOME目录，不填则默认在：/home/用户名
```sh
useradd [-g 用户组] [-d Linux路径] 用户名
```

+ __userdel__ 
    删除用户（需root用户执行）
    - _-r_ ：  删除用户的HOME目录，不填则不删除
```sh
userdel [-r] 用户名
```

+ __id__ 
    查看用户所属组（需root用户执行）
    不提供用户名则是查看本身
```sh
id [用户名]
```

+ __usermod__ 
    修改用户所属组（需root用户执行）
    将指定用户加入指定用户组
```sh
usermod -aG 用户组 用户名
```

+ __getent__ 
    查看系统中有哪些**用户**（getent passwd）
    > root:x\:0:0:root:/root:/bin/bash
    > *用户名:密码:用户ID:用户组ID:描述信息:HOME目录:执行终端（默认bash）*

    查看系统中有哪些**组**（getent group）
    > root:x\:0
    > *组名:组认证:组ID*
```sh
getent passwd
getent group
```

+ __chmod__ 
    修改文件、文件夹的**权限信息**（只有文件、文件夹的所属用户或root用户可以修改）
    - _-R_ ：  对文件夹内的全部内容应用同样的操作
    u表示user所属用户权限，g表示组权限，o表示其它用户权限
```sh
chmod [-R] 权限 Linux路径

chmod -R u=rwx,g=rw,o=r test
chmod -R 764 test
```

+ __chown__ 
    修改文件、文件夹的所属**用户和用户组**（需root用户执行）
    - _-R_ ：  对文件夹内的全部内容应用同样的操作
    
```sh
chown [-R] [用户][:][用户组] Linux路径

chown root test
chown -R :root test
chown -R root:jiao test
```

+ __yum__ 
    RPM包管理器，用于自动化安装配置Linux软件，并可以自动解决依赖问题（需要root权限）
    - _-y_ ：  自动确认，无需手动确认安装或卸载过程
    
```sh
yum [-y] install|remove|search 软件名
```

+ __systemctl__ 
    linux很多软件支持使用systemctl命令控制：**启动、停止、开机自启**，能被systemctl管理的软件一般称为：**服务**
    - _start_ ：    启动服务
    - _stop_ ：     停止服务
    - _status_ ：   服务状态
    - _enable_ ：   启动开机自启
    - _disable_ ：  关闭开机自启
    
```sh
systemctl start|stop|status|enable|disable 服务名
```

+ __ln__ 
    **软链接**，将文件或文件夹链接到其它位置
```sh
ln -s 被链接文件或文件夹 链接去的目的地 
```

+ __date__ 
    查看系统时间
    - _-d_ ：  按照给定字符显示日期，一般用于日期计算
    - _%Y_ ：  年
    - _%y_ ：  年份后两位数字
    - _%m_ ：  月
    - _%d_ ：  日
    - _%H_ ：  时
    - _%M_ ：  分
    - _%S_ ：  秒
    - _%s_ ：  时间戳
    
```sh
date [-d] [+格式化字符串]

date "+%Y-%m-%d %H:%M:%S"
```

+ __hostname__ 
    **查看**主机名
```sh
hostname
```

+ __hostnamectl__ 
    **修改**主机名（需root用户执行）
```sh
hostnamectl set-hostname 主机名
```

+ __ping__ 
    检查指定的网络服务器是否是可联通状态
    - _-c_ ：    检查次数，不填-c则无限次检查
```sh
ping [-c num] ip或主机名

ping -c 5 bilibili.com
```

+ __curl__ 
    发起http网络请求，可用于获取信息或下载文件
    - _-O_ ：    用于下载文件
```sh
curl [-O] url

curl cip.cc
curl -O https://dlcdn.apache.org/hadoop/common/hadoop-3.4.0/hadoop-3.4.0-src.tar.gz
```


## ✨ Linux第三方命令 ✨
> wget
+ __wget__ 
    非交互式的文件下载器
    - _-b_ ：    后台下载，会将日志写入到当前工作目录的wget-log文件
```sh
wget [-b] url
```

> nmap
+ __nmap__ 
    查看端口占用情况
```sh
nmap IP地址
```

> net-tools
+ __netstat__ 
    查看指定端口占用情况
```sh
netstat -anp | grep 端口号
```