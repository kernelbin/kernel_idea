我的桌面总是很乱，所以我有了这个灵感。
我经常随意的在桌面上创建文件，用完了就忘记删除
如果可以在临时文件创建之初就设定这个文件被删除的时间点，比如某个具体日期，或者在另一个文件删除时一并删除
这个问题就解决了。
 
大致思路是监视桌面的文件创建（也可以手动添加想监视的文件夹啦），并且在文件创建时弹窗询问用户是否设置删除时间。在删除时提醒用户询问是否仍要删除。
也可以将设置文件删除时间的功能添加到系统右键菜单中
删除文件等操作最好不要直接调用API而是走Explorer.exe，这样可以支持删除后撤销删除什么的

My desktop is always a mess.
I always creating temp files on desktop casually and never delete them.
If I can set a delete timestamp when I create this file.... ? such as a certain date or delete along with another file and so on...

The idea is roughly like this:
Monitor the file created on desktop (or any directory you want), and popup a window to ask user whether to set a timestamp.
When deleting the file, ask user again in case it's still useful.
Also this function can be added to system menu(right click the file)
