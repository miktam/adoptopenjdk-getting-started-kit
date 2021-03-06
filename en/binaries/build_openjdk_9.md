# Build OpenJDK 9

Link to a detailed page on the Build step on the [Adopt OpenJDK wiki](https://java.net/projects/adoptopenjdk/pages/Build).

Prerequisite: supporting programs to build OpenJDK8 have been installed before attempting to perform the below instructions, [see site](https://java.net/projects/adoptopenjdk/pages/AdoptOpenJDKBuild). Follow the below instructions to build OpenJDK9 from the jdk9 forest:

```
$ cd $HOME/sources```


or 

```
$ cd $HOME/dev
```

```
$ hg clone http://hg.openjdk.java.net/jdk9/jdk9 jdk9

$ cd jdk9

$ chmod u+x get_source.sh 
$ ./get_source.sh 
```


```/usr/lib/jvm/jdk1.8.0``` - can differ in your case, please download JDK 8 at least from the [site](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html). It is recommended to use this JDK as it is better tested and free from any changes you might have made to the local copy of the OpenJDK8 sources & images.

It is possible to get Oracle JDK 1.8 on Ubuntu by adding the repository of the Web Update 8 project, [see instructions](http://tecadmin.net/install-oracle-java-8-jdk-8-ubuntu-via-ppa/).

```
$ bash configure --with-boot-jdk=/usr/lib/jvm/jdk1.8.0```


If you downloaded the virtual machine image then use this path:

```
$ bash configure --with-boot-jdk=/usr/lib/jvm/java-8-oracle
```


```
$ make clean images ```


or 

```
$ make clean images LOG=debug     
                 ## to display DEBUG information 
```

Check out the [Nashorn forest](http://hg.openjdk.java.net/jdk9/jdk9/nashorn) for JDK9.
