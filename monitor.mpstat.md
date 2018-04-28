# mpstat

> mpstat命令指令主要用于多CPU环境下，它显示各个可用CPU的状态。这些信息存放在/proc/stat文件中。
在多CPUs系统里，其不但能查看所有CPU的平均状况信息，而且能够查看特定CPU的信息。

## 语法

mpstat(选项)(参数)

## 选项

-P：指定CPU编号。

## 参数

+ 间隔时间：每次报告的间隔时间（秒）；
+ 次数：显示报告的次数。

## 实例

当mpstat不带参数时，输出为从系统启动以来的平均值。
```
mpstat
Linux 2.6.9-5.31AXsmp (builder.redflag-linux.com) 12/16/2005
09:38:46 AM CPU %user %nice %system %iowait %irq %soft %idle intr/s
09:38:48 AM all 23.28 0.00 1.75     0.50 0.00 0.00 74.47 1018.59
```

每2秒产生了2个处理器的统计数据报告
``` 
mpstat -P ALL 2 3
Linux 2.6.18-164.el5 (server.sys.com)    01/04/2010
09:34:20 PM CPU   %user   %nice    %sys %iowait    %irq   %soft %steal   %idle    intr/s
09:34:22 PM all    0.00    0.00    0.00    0.00    0.00    0.00    0.00 100.00   1001.49
09:34:22 PM    0    0.00    0.00    0.50    0.00    0.00    0.00    0.00   99.50   1001.00
09:34:22 PM    1    0.00    0.00    0.00    0.00    0.00    0.00    0.00 100.00      0.00
```
