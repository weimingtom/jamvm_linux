$ sudo apt install libgtk2.0-dev
$ sudo apt install libgconf2-dev
wmt@wmt-VirtualBox:~/work_jamvm/classpath-0.99
$ CFLAGS="-Wno-error -Wno-error=deprecated-declarations -Wno-error=stringop-truncation" ./configure --prefix=/home/wmt/work_jamvm --with-antlr-jar=/home/wmt/work_jamvm/antlr-complete-3.5.2.jar
$ make clean all
wmt@wmt-VirtualBox:~/work_jamvm/jamvm-2.0.0$ 
$ ./configure --prefix=/home/wmt/work_jamvm --with-classpath-install-dir=/home/wmt/work_jamvm
$ make clean all

wmt@wmt-VirtualBox:~/work_jamvm/bin
$ ./jamvm -cp ../share/classpath/examples/examples.zip gnu.classpath.examples.swing.Demo
$ ./jamvm -cp ../share/classpath/examples/examples.zip gnu.classpath.examples.awt.Demo



