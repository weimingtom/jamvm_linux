# jamvm_linux
[WIP] My JamVM and GNU Classpath xubuntu and raspberry pi build, not good, just for fun

## Ref
* (for rpi3) https://gitee.com/Gonzo/jamvm-annotade
* https://www.cnblogs.com/gonzo/articles/15268632.html
* https://download.csdn.net/download/huangzhang_/10159753?utm_source=iteye_new
* http://www.blogjava.net/tingfeng/articles/432484.html
* https://www.zhihu.com/question/37798639

## For Xubuntu 20
* $ sudo apt install libgtk2.0-dev
* $ sudo apt install libgconf2-dev
* $ cd ~/work_jamvm/classpath-0.99
* $ CFLAGS="-Wno-error -Wno-error=deprecated-declarations -Wno-error=stringop-truncation" ./configure --prefix=/home/wmt/work_jamvm --with-antlr-jar=/home/wmt/work_jamvm/antlr-complete-3.5.2.jar
* $ make clean all
* $ cd ~/work_jamvm/jamvm-2.0.0$ 
* $ ./configure --prefix=/home/wmt/work_jamvm --with-classpath-install-dir=/home/wmt/work_jamvm
* $ make clean all
* $ cd ~/work_jamvm/bin
* $ ./jamvm -cp ../share/classpath/examples/examples.zip gnu.classpath.examples.swing.Demo
* $ ./jamvm -cp ../share/classpath/examples/examples.zip gnu.classpath.examples.awt.Demo

## For RPI3, Raspberry Pi 3 
* Install java8, jdk1.8.0_291, jdk-8u291-linux-arm32-vfp-hflt.tar.gz  
* $ sudo apt install libgconf2-dev
* $ cd classpath-0.99
* (not good) $ ./configure --prefix=/home/pi/work_jamvm --with-antlr-jar=/home/pi/work_jamvm/antlr-4.7.1-complete.jar
* (not good) $ CFLAGS="-Wno-error=stringop-truncation" ./configure --prefix=/home/pi/work_jamvm --with-antlr-jar=/home/pi/work_jamvm/antlr-4.7.1-complete.jar
* (not good) $ CFLAGS="-Wno-error=stringop-truncation" ./configure --prefix=/home/pi/work_jamvm --with-antlr-jar=/home/pi/work_jamvm/antlr-4.7.1-complete.jar --disable-jni --disable-core-jni --disable-gtk-peer
* (not good) $ CFLAGS="-Wno-error=stringop-truncation" ./configure --prefix=/home/pi/work_jamvm --with-antlr-jar=/home/pi/work_jamvm/antlr-complete-3.5.2.jar --disable-jni --disable-core-jni --disable-gtk-peer
* $ CFLAGS="-Wno-error=stringop-truncation -Wno-error=cast-function-type" ./configure --prefix=/home/pi/work_jamvm --with-antlr-jar=/home/pi/work_jamvm/antlr-complete-3.5.2.jar --disable-gtk-peer
* $ make
```
（一定要编译jni的so文件，输出到/home/pi/work_jamvm/lib/classpath/一堆的so文件）
（可以通过jamvm -version查看这个jni路径，参考http://www.blogjava.net/tingfeng/articles/432484.html）
https://www.zhihu.com/question/37798639
```
* $ cd ../jamvm
* $ ./configure --prefix=/home/pi/work_jamvm --with-classpath-install-dir=/home/pi/work_jamvm
* $ make
* $ LD_LIBRARY_PATH=/home/pi/work_jamvm/lib ./jamvm -Xbootclasspath:/home/pi/work_jamvm/share/jamvm/classes.zip:/home/pi/work_jamvm/share/classpath/glibj.zip Main
