#### L1/L2/L3 在CPU芯片里么？
这是一个动态发展的过程，以前，L1在CPU核心中(Die)中，L2在主板上。
后来每个Core都有L1/L2，而L3开始被一个CPU中的Core共享。

#### L1/L2/L3 内存中么？
让然不是，L1，L2，L3是独立的。

#### L1/L2/L3的速度
L1一般是3个时钟周期，L2是12个左右，L3就是几十个。

#### L1/L2/L3占用占用内存地址空间么？
占用，以为内CPU都是通过逻辑地址来访问的，Cache模块接受到的地址也是有地址的。
所以，这部分地址其实是Cache覆盖掉了Memory，所以Cache某种意义上也是有地址映射的。
Cache分logical cache 和physical cache。

#### 为什么L1比L2快
L1容量小，也就面积小。L1中的DCache在load/store单元附近，ICache在Core的指令预取单元附近，而L2在CPU pipeline外面。
#### Write-Through模式
cache中更新马上同步到内存中。
