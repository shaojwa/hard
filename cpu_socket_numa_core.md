#### chip
The resources of a processor chip have a hierarchy. 
The largest unit is a socket. A socket can contain one or more NUMA nodes with its cores and memory. 
A NUMA node will contain a set of cores and threads and memory which is local to the NUMA node.

#### socket
A socket refers to the physical location where a processor package plugs into a motherboard. 
The processor that plugs into the motherboard is also known as a socket. The socket can contain one or more NUMA nodes.
so, a socket equals a processor in most cases.

#### NUMA node

#### core
A core is an individual execution unit within a processor that can independently execute a software execution thread
and maintains its execution state separate from the execution state of any other cores within a processor.

#### threads
A thread refers to a hardware-based thread execution capability. For example, the Intel Xeon 7560 has eight cores,
each of which has hardware that can effectively execute two software execution threads simultaneously, yielding 16 threads.

#### commands
```
numactl --hardware
```
or
```
numastat
```
