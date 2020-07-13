# mac下unix网络编程环境搭建

---

1. 下载安装unpv13e的包

   下载地址：[链接](http://www.unpbook.com/src.html)

2. 解压后再终端通过命令进入unpv13e文件

   ~~~
   ./config
   
   cd lib
   
   make
   
   cd ../libfree
   
   make
   ~~~

   这时，会报错，只需要在unpv13e/libfree下找到inet_ntop.c文件把#include <arpa/inet.h>注释掉

   然后在unpv13e文件夹中成功生成libunp.a文件

3. **将生成的libunp.a文件复制到usr/lib文件夹中，并且将unpv13e下的config.h和修改后的unpv13e/lib中的unp.h复制到usr/include文件夹中**

   * 首先将unp.h中的#include "…/config.h"修改为#include “config.h” ，因为unp.h和config.h都放入usr/include中

   * 执行命令：（都是在unpv13e文件夹中）

     ~~~
     sudo cp libunp.a /usr/lib
     sudo cp lib/unp.h /usr/include   
     sudo cp config.h /usr/include
     ~~~

4. 若前面都已经成功，确认**libunp.a**,**unp.h**,**config.h**都已经拷贝到相应文件夹下，开始编译第一个例子daytimetcpcli.c；在unpv13e文件夹下，依次执行相应命令：

   ~~~
   cd  intro
   gcc daytimetcpcli.c -lunp
   ~~~

   注意：编译时必须加上静态链接库：-l 参数加上 libunp.a 去掉lib和后面的.a。最后得到参数-lunp
   成功则在intro文件夹下生成了可执行文件a.out,测试：

   ~~~
   ./a.out 127.0.0.1
   ~~~

   这时会有错误，该错误表示 daytime 服务程序没开，解决方法：
   新建一个终端窗口在unpv13e/intro下编译daytimetcp服务器程序并已管理员身份运行

   ~~~
   gcc daytimetcpsrv.c -o daytimetcpsrv -lunp
   sudo ./daytimetcpsrv
   ~~~

   再执行，成功。