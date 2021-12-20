# 如何使用burp抓app数据

## 一，使用模拟器

### 第一步，下载模拟器app

这边我就使用联想模拟器演示

### 第二步，burpsuite设置代理

打开计算机命令提示框cmd 输入ipconfig/all查看当前电脑的虚拟网卡VMware8的地址如下图所示

![image-20211220153219383](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220153219383.png)

查看联想模拟器网络

![image-20211220153440411](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220153440411.png)

**因为联想模拟器用的是NAT模式的虚拟网卡，所以burpsuite设置代理地址为 VMware8 的IP**

接下来我们打开Bp

![image-20211220153905058](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220153905058.png)

![image-20211220161125472](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220161125472.png)

### 第三步：安卓模拟器设置代理

![image-20211220154211994](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220154211994.png)



![image-20211220154615467](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220154615467.png)

![image-20211220160936472](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220160936472.png)

### 第四步：安卓模拟器安装证书

burpsuite如果抓取https的包，需要安装CA证书
打开浏览器，输入IP地址：169.254.39.138:8888 下载证书

![image-20211220155626470](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220155626470.png)

证书下载完之后，需要将下载的证书 cacert.der 修改为cacert.cer，否则无法安装证书

但是安卓模拟器是不可以直接修改的，需要在电脑上修改，可以选择安卓模拟器的 共享 下载共享路径，选中windows的图标

![image-20211220155818319](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220155818319.png)

![image-20211220160005099](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220160005099.png)

改完之后点击安卓标识

![image-20211220160040709](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220160040709.png)

![image-20211220160142881](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220160142881.png)

![image-20211220160150488](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220160150488.png)

设置名称后 点击确定

![image-20211220160330771](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220160330771.png)

自行设置PIN码后

![image-20211220160419289](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220160419289.png)

显示已安装后说明安装成功

### 第五步：burpsuite抓取APP数据包

![image-20211220160643183](C:\Users\86156\AppData\Roaming\Typora\typora-user-images\image-20211220160643183.png)

