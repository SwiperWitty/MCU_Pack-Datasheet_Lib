# MDK

J link下载相关						2023.06.08





### J link下载

1. 问题在于可以识别到芯片，但是不能下载，也不能擦除。这个时候大概率是芯片锁了。

<img src="https://gitee.com/Swiper_witty/caven_img/raw/master/img/202306080921754.png" alt="image-20230608092132685" style="zoom: 80%;" />

这个时候可以使用J link的命令行，也可以在J link的GUI界面解除这个锁。

![image-20230608092255922](https://gitee.com/Swiper_witty/caven_img/raw/master/img/202306080922000.png)



当然，还有一种可能——芯片是假的，型号不对（FlyMCU读器件信息）。

![image-20230608092628552](https://gitee.com/Swiper_witty/caven_img/raw/master/img/202306080926585.png)

2. 如果连ID都识别不到，那么可能是芯片的程序禁用了JTAG/SWD，这个时候把BOOT0 拉高，再复位，进行串口下载模式，擦掉原有程序。如果还是不能下载，那就考虑降低下载速度。