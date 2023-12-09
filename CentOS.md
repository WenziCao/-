
以下是按照分类整理的命令列表：

### 1. 关机、重启和登出命令

* 关机命令：
    
    1. `shutdown -h now` - 立即关闭系统 (选项1)
    2. `init 0` - 立即关闭系统 (选项2)
    3. `telinit 0` - 立即关闭系统 (选项3)
    4. `shutdown -h hours:minutes &` - 按预定时间关闭系统
    5. `shutdown -c` - 取消按预定时间关闭系统
* 重启命令：
    
    1. `shutdown -r now` - 立即重启系统 (选项1)
    2. `reboot` - 立即重启系统 (选项2)
* 登出命令：
    
    * `logout` - 注销

### 2. 查看系统信息命令

* 系统架构信息：
    
    1. `arch` - 显示机器的处理器架构 (选项1)
    2. `uname -m` - 显示机器的处理器架构 (选项2)
* 内核和硬件信息：
    
    1. `uname -r` - 显示正在使用的内核版本
    2. `dmidecode -q` - 显示硬件系统部件 (SMBIOS / DMI)
    3. `hdparm -i /dev/hda` - 罗列一个磁盘的架构特性
    4. `hdparm -tT /dev/sda` - 在磁盘上执行测试性读取操作
    5. `cat /proc/cpuinfo` - 显示CPU信息
    6. `cat /proc/interrupts` - 显示中断
    7. `cat /proc/meminfo` - 校验内存使用
    8. `cat /proc/swaps` - 显示哪些swap被使用
    9. `cat /proc/version` - 显示内核的版本
    10. `cat /proc/net/dev` - 显示网络适配器及统计
    11. `cat /proc/mounts` - 显示已加载的文件系统
    12. `lspci -tv` - 罗列PCI设备
    13. `lsusb -tv` - 显示USB设备
    14. `date` - 显示系统日期
    15. `cal 2007` - 显示2007年的日历表
    16. `date 041217002007.00` - 设置日期和时间

### 3. 文件和目录操作命令

* 目录导航和显示：
    1. `cd /home` - 进入'/home'目录
    2. `cd ..` - 返回上一级目录
    3. `cd ../..` - 返回上两级目录
    4. `cd` - 进入个人的主目录
    5. `cd ~user1` - 进入个人的主目录 (user1)
    6. `cd -` - 返回上次所在的目录
    7. `pwd` - 显示工作路径
    8. `ls` - 查看目录中的文件
    9. `ls -F` - 查看目录中的文件
    10. `ls -l` - 显示文件和目录的详细资料
    11. `ls -a` - 显示隐藏文件
    12. `mkdir dir1` - 创建一个叫做'dir1'的目录
    13. `mkdir dir1 dir2` - 同时创建两个目录
    14. `mkdir -p /tmp/dir1/dir2` - 创建一个目录树
    15. `rm -f file1` - 删除一个叫做'file1'的文件
    16. `rmdir dir1` - 删除一个叫做'dir1'的目录
    17. `rm -rf dir1` - 删除一个叫做'dir1'的目录及其内容
    18. `rm -rf dir1 dir2` - 同时删除两个目录及它们的内容
    19. `mv dir1 new_dir` - 重命名/移动一个目录
    20. `cp file1 file2` - 复制一个文件
    21. `cp dir/* .` - 复制一个目录下的所有文件到当前工作目录
    22. `cp -a /tmp/dir1 .` - 复制一个目录到当前工作目录
    23. `cp -a dir1 dir2` - 复制一个目录
    24. `ln -s file1 lnk1` - 创建一个指向文件或目录的软链接
    25. `ln file1 lnk1` - 创建一个指向文件或目录的物理链接
    26. `touch file1` - 创建一个文件

### 4. 文件搜索命令

* 文件搜索：
    1. `find / -name file1` - 从'/'开始进入根文件系统搜索文件和目录
    2. `find / -user user1` - 搜索属于用户'user1'的文件和目录
    3. `find /home/user1 -name \*.bin` - 在目录'/home/user1'中搜索带有'.bin'结尾的文件
    4. `find /usr/bin -type f -atime +100` - 搜索在过去100天内未被使用过的执行文件
    5. `find /usr/bin -type f -mtime -10` - 搜索在10天内被创建或修改过的文件
    6. `locate \*.ps` - 寻找以'.ps'结尾的文件 (先运行'updatedb'命令)
    7. `whereis file` - 显示一个二进制文件、源码或man的位置
    8. `which file` - 显示一个二进制文件或可执行文件的完整路径

### 5. 查看文件内容

* 文件查看：
    1. `cat file1` - 从第一个字节开始正向查看文件的内容
    2. `tac file1` - 从最后一行开始反向查看一个文件的内容
    3. `more file1` - 查看一个长文件的内容
    4. `less file1` - 类似于'more'命令，但允许反向操作
    5. `head -2 file1` - 查看一个文件的前两行
    6. `tail -2 file1` - 查看一个文件的最后两行

### 6. 挂载命令

* 挂载和卸载：
    1. `mount /dev/hda2 /mnt/hda2` - 挂载一个叫做hda2的盘
    2. `umount /dev/hda2` - 卸载一个叫做hda2的盘
    3. `fuser -km /mnt/hda2` - 当设备繁忙时强制卸载
    4. `umount -n /mnt/hda2` - 运行卸载操作而不写入/etc/mtab文件
    5. `mount /dev/fd0 /mnt/floppy` - 挂载一个软盘
    6. `mount /dev/cdrom /mnt/cdrom` - 挂载一个光盘
    7. `mount /dev/hdc /mnt/cdrecorder` - 挂载一个cdrw或dvdrom
    8. `mount /dev/hdb /mnt/cdrecorder` - 挂载一个cdrw或dvdrom
    9. `mount -o loop file.iso /mnt/cdrom` - 挂载一个文件或ISO镜像文件
    10. `mount -t vfat /dev/hda5 /mnt/hda5` - 挂载一个Windows FAT32文件系统
    11. `mount /dev/sda1 /mnt/usbdisk` - 挂载一个USB捷盘或闪存设备
    12. `mount -t smbfs -o username=user,password=pass //WinClient/share /mnt/share` - 挂载一个Windows网络共享

### 7. 磁盘空间操作命令

* 磁盘空间查看和操作：
    1. `df -h` - 显示已经挂载的分区列表
    2. `ls -lSr |more` - 以尺寸大小排列文件和目录
    3. `du -sh dir1` - 估算目录'dir1'已经使用的磁盘空间
    4. `du -sk * | sort -rn` - 以容量大小为依据依次显示文件和目录的大小

### 8. 用户和群组相关命令

* 用户和群组管理：
    1. `groupadd group_name` - 创建一个新用户组
    2. `groupdel group_name` - 删除一个用户组
    3. `groupmod -n new_group_name old_group_name` - 重命名一个用户组
    4. `useradd -c "Name Surname " -g admin -d /home/user1 -s /bin/bash user1` - 创建一个属于 "admin" 用户组的用户
    5. `useradd user1` - 创建一个新用户
    6. `userdel -r user1` - 删除一个用户 ('-r' 同时删除除主目录之外的文件)
    7. `passwd user1` - 修改一个用户的口令 (只允许root执行)
    8. `chage -E 2005-12-31 user1` - 设置用户口令的失效期限
    9. `ls -lh` - 显示权限
    10. `chmod 777 directory1` - 设置目录的所有人(u)、群组(g)以及其他人(o)以读（r）、写(w)和执行(x)的权限
    11. `chmod 700 directory1` - 删除群组(g)与其他人(o)对目录的读写执行权限
    12. `chown user1 file1` - 改变一个文件的所有人属性，为user1。
    13. `chown -R user1 directory1` - 改变一个目录的所有人属性并同时改变改目录下所有文件的属性都为user1所有
    14. `chgrp group1 file1` - 改变文件的群组为group1
    15. `chown user1:group1 file1` - 改变一个文件的所有人和群组属性，所属组为group1，用户为user1。
    16. `find / -perm -u+s` - 罗列一个系统中所有使用了SUID控制的文件
    17. `chmod u+s /bin/file1` - 设置一个二进制文件的 SUID 位 - 运行该文件的用户也被赋予和所有者同样的权限
    18. `chmod u-s /bin/file1` - 禁用一个二进制文件的 SUID位
    19. `chmod g+s /home/public` - 设置一个目录的SGID 位 - 类似SUID ，不过这是针对目录的
    20. `chmod g-s /home/public` - 禁用一个目录的 SGID 位
    21. `chmod o+t /home/public` - 设置一个文件的 STIKY 位 - 只允许合法所有人删除文件
    22. `chmod o-t /home/public` - 禁用一个目录的 STIKY 位

### 9. 打包和解压缩文件的命令

* 文件打包和解压缩：
    1. `bunzip2 file1.bz2` - 解压一个叫做'file1.bz2'的文件
    2. `bzip2 file1` - 压缩一个叫做'file1'的文件
    3. `gunzip file1.gz` - 解压一个叫做'file1.gz'的文件
    4. `gzip file1` - 压缩一个叫做'file1'的文件
    5. `gzip -9 file1` - 最大程度压缩
    6. `rar a file1.rar test_file` - 创建一个叫做'file1.rar'的包
    7. `rar a file1.rar file1 file2 dir1` - 打包 'file1', 'file2' 以及目录 'dir1'
    8. `rar x file1.rar` - 解rar包
    9. `unrar x file1.rar` - 解rar包
    10. `tar -cvf archive.tar file1` - 创建一个非压缩的tar包
    11. `tar -cvf archive.tar file1 file2 dir1` - 创建一个包含了 'file1', 'file2' 'dir1'的包
    12. `tar -tf archive.tar` - 显示一个包中的内容
    13. `tar -xvf archive.tar` - 释放一个包
    14. `tar -xvf archive.tar -C /tmp` - 将压缩包释放到 /tmp目录下 （-c是指定目录）
    15. `tar -cvfj archive.tar.bz2 dir1` - 创建一个bzip2格式的压缩包
    16. `tar -xvfj archive.tar.bz2` - 解压一个bzip2格式的压缩包
    17. `tar -cvfz archive.tar.gz dir1` - 创建一个gzip格式的压缩包
    18. `tar -xvfz archive.tar.gz` - 解压一个gzip格式的压缩包
    19. `zip file1.zip file1` - 创建一个zip格式的压缩包
    20. `zip -r file1.zip file1 file2 dir1` - 将几个文件和目录同时压缩成一个zip格式的压缩包
    21. `unzip file1.zip` - 解压一个zip格式压缩包

### 10. RPM 包相关命令

* RPM 包管理：
    1. `rpm -ivh package.rpm` - 安装一个rpm包
    2. `rpm -ivh --nodeeps package.rpm` - 安装一个rpm包而忽略依赖关系警告
    3. `rpm -U package.rpm` - 更新一个rpm包但不改变其配置文件
    4. `rpm -F package.rpm` - 更新一个确定已经安装的rpm包
    5. `rpm -e package_name.rpm` - 删除一个rpm包
    6. `rpm -qa` - 显示系统中所有已经安装的rpm包
    7. `rpm -qa | grep httpd` - 显示所有名称中包含 "httpd" 字样的rpm包
    8. `rpm -qi package_name` - 获取一个已安装包的特殊信息
    9. `rpm -ql package_name` - 显示一个已经安装的rpm包提供的文件列表
    10. `rpm -qc package_name` - 显示一个已经安装的rpm包提供的配置文件列表
    11. `rpm -q package_name --whatrequires` - 显示与一个rpm包存在依赖关系的列表
    12. `rpm -q package_name --whatprovides` - 显示一个rpm包所占的体积
    13. `rpm -q package_name --scripts` - 显示在安装/删除期间所执行的脚本
    14. `rpm -q package_name --changelog` - 显示一个rpm包的修改历史
    15. `rpm -qf /etc/httpd/conf/httpd.conf` - 确认所给的文件由哪个rpm包所提供
    16. `rpm -qp package.rpm -l` - 显示由一个尚未安装的rpm包提供的文件列表
    17. `rpm --import /media/cdrom/RPM-GPG-KEY` - 导入公钥数字证书
    18. `rpm --checksig package.rpm` - 确认一个rpm包的完整性
    19. `rpm -qa gpg-pubkey` - 确认已安装的所有rpm包的完整性
    20. `rpm -V package_name` - 检查文件尺寸、许可、类型、所有者、群组、MD5检查以及最后修改时间
    21. `rpm -Va` - 检查系统中所有已安装的rpm包- 小心使用
    22. `rpm -Vp package.rpm` - 确认一个rpm包还未安装
    23. `rpm2cpio package.rpm | cpio --extract --make-directories *bin*` - 从一个rpm包运行可执行文件
    24. `rpm -ivh /usr/src/redhat/RPMS/`arch`/package.rpm` - 从一个rpm源码安装一个构建好的包
    25. `rpmbuild --rebuild package_name.src.rpm` - 从一个rpm源码构建一个rpm包

### 11. YUM 软件包升级器命令

* YUM 软件包管理：
    1. `yum install package_name` - 下载并安装一个rpm包
    2. `yum localinstall package_name.rpm` - 将安装一个rpm包，使用你自己的软件仓库为你解决所有依赖关系
    3. `yum update package_name.rpm` - 更新当前系统中所有安装的rpm包
    4. `yum update package_name` - 更新一个rpm包
    5. `yum remove package_name` - 删除一个rpm包
    6. `yum list` - 列出当前系统中安装的所有包
    7. `yum search package_name` - 在rpm仓库中搜寻软件包
    8. `yum clean packages` - 清理rpm缓存删除下载的包
    9. `yum clean headers` - 删除所有头文件
    10. `yum clean all` - 删除所有缓存的包和头文件