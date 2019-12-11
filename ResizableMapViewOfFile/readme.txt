在使用内存映射文件在不同进程间共享数据的时候，总有一个很头大的问题：内存映射文件一经创建，大小就不可调整。
每次需要调整大小，貌似只有创建一个新的。
但 这 真 的 很 傻！
于是我决心解决这个问题。
这是我的一个设想，并没有验证过可行性
MapViewOfFileEx 比 MapViewOfFile函数 多出一个 LPVOID lpBaseAddress 参数
这个参数可以指定映射到的基地址。
这样一来，当需要增加内存映射文件的大小的时候，只需要新建一个内存映射文件并且将其并在前一个内存映射文件所在地址的后面，内存就是连续的了。
顺便，可以采用Vector管理内存的方式。（倍增）


When using FileMapping to share data between process, there's always a problem haunting me.
The size of FileMapping is fixed once you created it.
Every time you need to extend it, you have to create a new one, and copy the content.
THAT'S REALLY STUPID
So I determined to solve this problem.
Described below is one of my idea ( Haven't examined yet )

MapViewOfFileEx have one LPVOID lpBaseAddress Param more than MapViewOfFile
By using this, when extending the size, we can create a new filemap and align it at the end of the last filemap.
besides, every time doulbe the size may help (for example, first time 64kb, second time 64kb, and then 128, 256, 512, 1024kb....)