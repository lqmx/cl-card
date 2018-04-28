# free

> free命令可以显示当前系统未使用的和已使用的内存数目，还可以显示被内核使用的内存缓冲区。

## 语法

free(选项)

## 选项

+ -b：以Byte为单位显示内存使用情况；
+ -k：以KB为单位显示内存使用情况；
+ -m：以MB为单位显示内存使用情况；
+ -o：不显示缓冲区调节列；
+ -s<间隔秒数>：持续观察内存使用状况；
+ -t：显示内存总和列；
+ -V：显示版本信息。

## 实例

```
free -m
             total       used       free     shared    buffers     cached
Mem:          2016       1973         42          0        163       1497
-/+ buffers/cache:        312       1703
Swap:         4094          0       4094
```

+ Mem行 total = used + free
    - total：内存总数；
    - used：已经使用的内存数；
    - free：空闲的内存数；
    - shared：当前已经废弃不用；
    - buffers Buffer：缓存内存数；
    - cached Page：缓存内存数。
+ -/+ buffers/cache
    (-buffers/cache) used内存数：第一部分Mem行中的 used – buffers – cached 反映的是被程序实实在在吃掉的内存
    (+buffers/cache) free内存数: 第一部分Mem行中的 free + buffers + cached   反映的是可以挪用的内存总数
+ 交换分区Swap