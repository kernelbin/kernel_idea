��ʹ���ڴ�ӳ���ļ��ڲ�ͬ���̼乲�����ݵ�ʱ������һ����ͷ������⣺�ڴ�ӳ���ļ�һ����������С�Ͳ��ɵ�����
ÿ����Ҫ������С��ò��ֻ�д���һ���µġ�
�� �� �� �� �� ɵ��
�����Ҿ��Ľ��������⡣
�����ҵ�һ�����룬��û����֤��������
MapViewOfFileEx �� MapViewOfFile���� ���һ�� LPVOID lpBaseAddress ����
�����������ָ��ӳ�䵽�Ļ���ַ��
����һ��������Ҫ�����ڴ�ӳ���ļ��Ĵ�С��ʱ��ֻ��Ҫ�½�һ���ڴ�ӳ���ļ����ҽ��䲢��ǰһ���ڴ�ӳ���ļ����ڵ�ַ�ĺ��棬�ڴ�����������ˡ�
˳�㣬���Բ���Vector�����ڴ�ķ�ʽ����������


When using FileMapping to share data between process, there's always a problem haunting me.
The size of FileMapping is fixed once you created it.
Every time you need to extend it, you have to create a new one, and copy the content.
THAT'S REALLY STUPID
So I determined to solve this problem.
Described below is one of my idea ( Haven't examined yet )

MapViewOfFileEx have one LPVOID lpBaseAddress Param more than MapViewOfFile
By using this, when extending the size, we can create a new filemap and align it at the end of the last filemap.
besides, every time doulbe the size may help (for example, first time 64kb, second time 64kb, and then 128, 256, 512, 1024kb....)