# swappiness 过大
##  表现

开辟 swap 分区后系统反而更加卡顿

## 原因

现代计算机性能的一大瓶颈就是硬盘，swap 分区虽然比普通分区(ext4 分区)读写快，但相比 RAM 还是非常慢的，尤其是我的电脑只是普通的机械硬盘而且性能差，频繁读写 swap 分区反而拖慢系统。Arch 默认 swappiness 大小为 60，即当内存消耗超过 40% 就开始使用 swap 分区，对大内存差硬盘的机器非常糟糕。

## 解决

使用如下命令，可以即时修改。

`# sysctl vm.swappiness=10`

若要永久修改，可以写入`/etc/sysctl.d/99-sysctl.conf`文件

> \# /etc/sysctl.d/99-sysctl.conf
>
> vm.swappiness=10