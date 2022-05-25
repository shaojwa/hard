#### chip
The resources of a processor chip have a hierarchy. 
The largest unit is a socket. A socket can contain one or more NUMA nodes with its cores and memory. 
A NUMA node will contain a set of cores and threads and memory which is local to the NUMA node.

#### socket = physical CPU numbers
A socket refers to the physical location where a processor package plugs into a motherboard. 
The processor that plugs into the motherboard is also known as a socket. The socket can contain one or more NUMA nodes.
so, a socket equals a processor in most cases.
```
cat /proc/cpuinfo | grep "physical id" | sort | uniq
```
the physical id of the cpu package. in Xeon 6330 it is 2.

#### NUMA node

#### core
A core is an individual execution unit within a processor that can independently execute a software execution thread
and maintains its execution state separate from the execution state of any other cores within a processor.
```
cat /proc/cpuinfo | grep "cpu cores"
```
the vps in linode, cpu cores is 1 and in Xeon 6330, the cpu cores if 28.

#### threads = logical CPUs
A thread refers to a hardware-based thread execution capability. For example, the Intel Xeon 7560 has eight cores,
each of which has hardware that can effectively execute two software execution threads simultaneously, yielding 16 threads.
```
cat /proc/cpuinfo | grep "sublings"
```
if sublings equals cores, the hyper-thread is disabled, if sublings is twice of cores, the hyper-thread is enabled.
the vps in linode, cpu cores is 1 and in Xeon 6330, the cpu cores if 56. 

#### logical CPUS  = thread
```
cat /proc/cpuinfo | grep processor | wc -l
```


#### commands
```
numactl --hardware
```
or
```
numastat
```

#### some other details
```
processor       : 0
vendor_id       : GenuineIntel
cpu family      : 6
model           : 106
model name      : Intel(R) Xeon(R) Gold 6330 CPU @ 2.00GHz
stepping        : 6
microcode       : 0xd000311
cpu MHz         : 2600.000
cache size      : 43008 KB
physical id     : 0
siblings        : 56
core id         : 0
cpu cores       : 28
apicid          : 0
initial apicid  : 0
fpu             : yes
fpu_exception   : yes
cpuid level     : 27
wp              : yes
flags           : fpu vme de pse tsc msr pae mce ...
vmx flags       : vnmi preemption_timer posted_intr invvpid...
bugs            : spectre_v1 spectre_v2 spec_store_bypass swapgs
bogomips        : 4000.00
clflush size    : 64
cache_alignment : 64
address sizes   : 46 bits physical, 57 bits virtual
power management:
```

lscpu:
```
Architecture:          x86_64
CPU op-mode(s):        32-bit, 64-bit
Byte Order:            Little Endian
CPU(s):                112
On-line CPU(s) list:   0-111
Thread(s) per core:    2
Core(s) per socket:    28
Socket(s):             2
NUMA node(s):          2
Vendor ID:             GenuineIntel
CPU family:            6
Model:                 106
Model name:            Intel(R) Xeon(R) Gold 6330 CPU @ 2.00GHz
Stepping:              6
CPU MHz:               2600.000
CPU max MHz:           3100.0000
CPU min MHz:           800.0000
BogoMIPS:              4000.00
Virtualization:        VT-x
L1d cache:             48K
L1i cache:             32K
L2 cache:              1280K
L3 cache:              43008K
NUMA node0 CPU(s):     0-27,56-83
NUMA node1 CPU(s):     28-55,84-111
```
