https://www.techtarget.com/searchstorage/definition/SCSI

#### 什么是SCSI
小型计算机系统接口，这是一个协议名称

#### 解决什么问题
解决小型机（注意一开始不是PC）上，计算机和周边设备比如磁盘，打印机，扫描仪，CD机等设备的数据传输。这不是主板上的总线协议。

#### 新的解决方案
在PC上SCSI基本已经被USB代替，在服务器磁盘上，但当然还是在用。在银盘驱动器协议里实现SCSI协议。

#### SCSI组件之 Initiator
Initiator发送请求获取SCSI服务，并收取响应。一般集成在服务器系统版上，或者在主机总线适配器中，对于ISCSI来说，有一个软件Initiator。

#### SCSI组件之 Target
这个在iSCSI中一样存在，这就是一个存储设备，一般来说是一个物理存储设备，很显然软件形式的target也是有的，比如iSCSI中。

#### SCSI组件之 service delivery subsytem
Initiator 和 Target之间的传输系统，一般就是电缆。

#### SCSI组件之 Expander
扩展器，一般用在 serial-attached SCSI (SAS)上，允许多个SAS设备来共享一个initiator port。

#### SCSI standards
SCSI的最大传输速率达到640MB/s，速度在现在来看也不能算慢。

#### serial and parallel SCSI
serial and parallel SCSI are based on the SCSI command set. SCSI 有串行和并行的区别。
