#### 缓存的MESI机制
MESI就是（Modified，Exclusive，Shared，invalid），用来内存一致性机制，缓存会有MESI的某个版本来实现一致性。
写的时候，设置Modified，如果我是Exclusive，不需要通知其他核，如果不是Exclusive，就需要并通知其他的cache line为Invalid。
读的时候，我标记当前cache line是shared，
