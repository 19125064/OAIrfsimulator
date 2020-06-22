这篇文章讲述了如何正确运行OAI rfsimulator，从而可以利用仿真的形式展示下行信道的信息，本次运行是在同一台主机上运行gNB和nrUE。安装并正确编译好OAI rfsimulator之后便可以按照本教程操作。



***\*第一步：\****

打开一个窗口按照如下图所示运行如下指令

![img](file:///C:\Users\ybb\AppData\Local\Temp\ksohtml16484\wps1.jpg) 

等待nr-softmodem和nr-uesoftmodem以及其他依赖项编译成功，运行成功需要一点时间。

备注：script的作用请自行查找

运行成功我们会看到如下图所示的提示

![img](file:///C:\Users\ybb\AppData\Local\Temp\ksohtml16484\wps2.jpg) 

 



***\*第二步：\****

再打开一个运行gNB的窗口，运行如下图所示指令：

![img](file:///C:\Users\ybb\AppData\Local\Temp\ksohtml16484\wps3.jpg) 

 

运行结果如下图所示

![img](file:///C:\Users\ybb\AppData\Local\Temp\ksohtml16484\wps4.jpg) 

 

 

***\*第三步：\****

打开第三个窗口，用于运行nrUE，运行如下图所示指令：

![img](file:///C:\Users\ybb\AppData\Local\Temp\ksohtml16484\wps5.jpg) 

 

备注：由于我们是在同一台主机上运行的gNB和nrUE，所以目标gNB地址采用默认的127.0.0.1，如果gNB和nrUE不是在同一台机器运行的，只需将127.0.0.1改为运行gNB的主机地址。

备注：-d只添加在nrUE窗口的命令行，用于获得softscope

 

运行之后会有一个NR DL SCOPE UE窗口自动打开，结果如下图所示

 

![img](file:///C:\Users\ybb\AppData\Local\Temp\ksohtml16484\wps6.jpg) 

显然此时的运行结果出现了问题，不要慌张，我们只需按ctrl+c退出gNB窗口，gNB停止运行此时nrUE也会自动退出。此时，我们只需在刚刚打开的gNB窗口运行如下图所示指令![img](file:///C:\Users\ybb\AppData\Local\Temp\ksohtml16484\wps7.jpg)

在刚刚打开的nrUE窗口运行如下如所示指令

![img](file:///C:\Users\ybb\AppData\Local\Temp\ksohtml16484\wps8.jpg) 



我们就会看到下图的结果：

![img](file:///C:\Users\ybb\AppData\Local\Temp\ksohtml16484\wps9.jpg) 

 

 

***\*第四步：\****

利用iperf进行网络测试：

打开第四个窗口（此时的测试是gNB和nrUE运行在相同的主机下进行的网络测试，如果gNB和nrUE运行在不同的主机上只需将127.0.0.1改成对应主机的IP地址即可），运行如下图所示指令（如果gNB和nrUE运行在不同的主机上，那么第四个窗口就是在nrUE主机上运行的）

![img](file:///C:\Users\ybb\AppData\Local\Temp\ksohtml16484\wps10.jpg) 

打开第五个窗口（此时的测试是gNB和nrUE运行在相同的主机下进行的网络测试，如果gNB和nrUE运行在不同的主机上只需将127.0.0.1改成对应主机的IP地址即可），运行如下图所示指令（如果gNB和nrUE运行在不同的主机上，那么第四个窗口就是在gNB主机上运行的）

![img](file:///C:\Users\ybb\AppData\Local\Temp\ksohtml16484\wps11.jpg) 

 

运行结果如下图所示：

![img](file:///C:\Users\ybb\AppData\Local\Temp\ksohtml16484\wps12.jpg) 