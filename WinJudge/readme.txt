在Windows下实现实时系统，对代码进行高精度评测（争取做的比JudgeDuck更好？）
要解决的问题：如何


下面是ThFabba前辈给我的的hints
If you ran your code in the kernel at DISPATCH_LEVEL, you'd be sure you have a CPU to yourself
The two most important things you want to do are: run on real hardware, not a VM; and disable Turbo Boost
Well the basic concept is what I just said -- if you run at DISPATCH_LEVEL, nobody will unschedule you.
The trick is just to make it easy and extendable, e.g. by letting user mode apps create callbacks that get run in the kernel, and letting those callbacks do cool stuff like interface with devices
Though they did add a fun feature where you tell Windows to boot with fewer CPUs and the realtime driver will initialize and take over the other ones. That way you have even less overhead
Oh actually for this purpose you'd have to run at HIGH_LEVEL, since you also don't want to be interrupted by interrupts
Technically you could probably run at DISPATCH and disable interrupts, but I think some watchdog on another CPU might start complaining about that.

除此之外还要解决的问题是，内存命中的问题
考虑固定一块内存专门给评测？

考虑两种方案，
1: 魔改ReactOS（目前ROS是单核心的，可能有点麻烦。）

2: 在Windows上通过提供驱动等方式，单独拿走一个CPU和一个驱动来做这件事情。
怎么样tell Windows to boot with fewer CPUs甚至是fewer memory，以及是不是得自己加载exe可能是难点


https://kithara.com/en/solutions/real-time-for-windows
