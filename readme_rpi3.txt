jamvm
https://www.cnblogs.com/gonzo/articles/15268632.html
https://gitee.com/Gonzo/jamvm-annotade
buildroot
https://blog.csdn.net/hceng_linux/article/details/103159220/
https://download.csdn.net/download/huangzhang_/10159753?utm_source=iteye_new
JamVM是一个开源的Java虚拟机，遵从GPL2.0协议发布，它符合最新的Java虚拟机规范。它的主要特点是其大小非常小，在PowerPC上仅有大约200KB，而在Intel处理器上仅有180KB。不像其他的小型虚拟机（如Jelatine JVM、SableVM等），JamVM支持完整的Java虚拟机规范
-1, 预装java8, jdk1.8.0_291, jdk-8u291-linux-arm32-vfp-hflt.tar.gz
sudo apt install libgconf2-dev
-2, cd classpath-0.99
./configure --prefix=/home/pi/work_jamvm --with-antlr-jar=/home/pi/work_jamvm/antlr-4.7.1-complete.jar
make
CFLAGS="-Wno-error=stringop-truncation" ./configure --prefix=/home/pi/work_jamvm --with-antlr-jar=/home/pi/work_jamvm/antlr-4.7.1-complete.jar
CFLAGS="-Wno-error=stringop-truncation" ./configure --prefix=/home/pi/work_jamvm --with-antlr-jar=/home/pi/work_jamvm/antlr-4.7.1-complete.jar --disable-jni --disable-core-jni --disable-gtk-peer
CFLAGS="-Wno-error=stringop-truncation" ./configure --prefix=/home/pi/work_jamvm --with-antlr-jar=/home/pi/work_jamvm/antlr-complete-3.5.2.jar --disable-jni --disable-core-jni --disable-gtk-peer
CFLAGS="-Wno-error=stringop-truncation -Wno-error=cast-function-type" ./configure --prefix=/home/pi/work_jamvm --with-antlr-jar=/home/pi/work_jamvm/antlr-complete-3.5.2.jar --disable-gtk-peer
（一定要编译jni的so文件，输出到/home/pi/work_jamvm/lib/classpath/一堆的so文件）
（可以通过jamvm -version查看这个jni路径，参考http://www.blogjava.net/tingfeng/articles/432484.html）
https://www.zhihu.com/question/37798639
LD_LIBRARY_PATH=/home/pi/work_jamvm/lib ./jamvm -Xbootclasspath:/home/pi/work_jamvm/share/jamvm/classes.zip:/home/pi/work_jamvm/share/classpath/glibj.zip Main
http://www.blogjava.net/tingfeng/articles/432484.html
-3 cd jamvm; ./configure --prefix=/home/pi/work_jamvm --with-classpath-install-dir=/home/pi/work_jamvm



