# rpi-rt

raspberry os preempt rt compiled patch

--------------------------------

I have noticed [4.19.y-rt](https://github.com/raspberrypi/linux/tree/rpi-4.19.y-rt) of raspberry/linux has not been updated for a long time, and no one has reviewed the submission. It seems that Tiejun Chen has no time and no one can replace this task.  
[lemariva/RT-Tools-RPi](https://github.com/lemariva/RT-Tools-RPi) is very useful, but only updated to 4.19.59_rt23. In [raspberry/linux](https://github.com/raspberrypi/linux/tree/rpi-4.19.y-rt) its 4.19.71_rt24  

I found that SR4ven did an rt patch on a fork. I downloaded it and compiled it, and it worked fine.Its 4.19.127_rt55.  
For the convenience, I will publish it as a separate package. But please don't forget to thank [SR4ven](https://github.com/SR4ven/linux).  
In addition, I found [this post](https://forum.linuxcnc.org/9-installing-linuxcnc/39779-rpi4-raspbian-64-bit-linuxcnc?start=10#181585) on the linuxcnc forum that provides a 64-bit preempt-rt patched kernel 5.4.61_rt37 package.  
Great Thanks for these guy.

### For download please visit [release page](https://github.com/feecat/rpi-rt/releases)
For how-to-use please visit [lemariva's tutorial](https://lemariva.com/blog/2019/09/raspberry-pi-4b-preempt-rt-kernel-419y-performance-test) at Installing the Kernel Image, Modules & Device Tree Overlays.  

NOTE: For now this two package only support rpi4(bcm2711).

--------------------------------

## real-time test tool

The code for testing real-time performance from [Realtime Linux](https://medium.com/@patdhlk/realtime-linux-e97628b51d5d) and [mklatencyplot.bash](https://www.osadl.org/uploads/media/mklatencyplot.bash).  
I did not successfully install png support, So I changed it to export SVG and simply tested it. Sources code see [here](https://github.com/feecat/rpi-rt/blob/main/docs/mklatencyplot.bash).  
The following is the test situation with 4.19.127_rt55:  

IDLE:  
![](https://github.com/feecat/rpi-rt/blob/main/docs/idle.svg)

Mid Use:  
![](https://github.com/feecat/rpi-rt/blob/main/docs/mid.svg)

CPU0 Full Use:  
![](https://github.com/feecat/rpi-rt/blob/main/docs/high.svg)

--------------------------------

## Useful links

https://github.com/raspberrypi/linux/issues/3172  
https://github.com/raspberrypi/linux/pull/3736  


