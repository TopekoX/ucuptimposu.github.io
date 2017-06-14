---
layout: article
title: Cara Membuat Project Java Dengan Maven
modified:
categories: jee
excerpt:
tags: [maven, jee, java, maven]
comments: true
ads: true
image:
  feature:
  teaser: maven.png
  thumb: maven.png
date: 2017-04-27T09:17:44-04:00
---

![Maven Logo](../images/maven.png)

Pada tutorial kali ini kita akan membuat project Java dengan menggunakan depedency injection maven yang akan di import dengan Eclipse IDE. Pada tutorial sebelumnya kita sudah [kenalan sama maven](/apache-maven/).

Tool yang saya digunakan

```
1. JDK 1.8
2. Maven 3.5.0
3. Eclipse IDE Luna
4. Koneksi Internet
```
**Info:** Cara [install maven disini](https://maven.apache.org/install.html).
{: .notice-info}

### Membuat Project

Masuk di terminal ketik, perintah dibawah ini untuk membuat project:

```
mvn archetype:generate -DgroupId={project-packaging}
   -DartifactId={project-name}
   -DarchetypeArtifactId=maven-archetype-quickstart
   -DinteractiveMode=false
```

Contoh nama project **AplikasiSpring**:

```
mvn archetype:generate -DgroupId=com.timposu
-DartifactId=AplikasiSpring
-DarchetypeArtifactId=maven-archetype-quickstart
-DinteractiveMode=false

```

Maven akan mendownload depedency project

```
$ mvn archetype:generate -DgroupId=com.timposu
-DartifactId=AplikasiSpring -DarchetypeArtifactId=maven-archetype-quickstart
-DinteractiveMode=false

[INFO] Scanning for projects...
[INFO]
[INFO] ------------------------------------------------------------------------
[INFO] Building Maven Stub Project (No POM) 1
[INFO] ------------------------------------------------------------------------
[INFO]
[INFO] >>> maven-archetype-plugin:3.0.1:generate (default-cli) > generate-sources @ standalone-pom >>>
[INFO]
[INFO] <<< maven-archetype-plugin:3.0.1:generate (default-cli) < generate-sources @ standalone-pom <<<
[INFO]
[INFO]
[INFO] --- maven-archetype-plugin:3.0.1:generate (default-cli) @ standalone-pom ---
[INFO] Generating project in Batch mode
[WARNING] No archetype found in remote catalog. Defaulting to internal catalog
[INFO] ----------------------------------------------------------------------------
[INFO] Using following parameters for creating project from Old (1.x) Archetype: maven-archetype-quickstart:1.0
[INFO] ----------------------------------------------------------------------------
[INFO] Parameter: basedir, Value: /home/ucup/workspace/latihan
[INFO] Parameter: package, Value: com.timposu
[INFO] Parameter: groupId, Value: com.timposu
[INFO] Parameter: artifactId, Value: AplikasiSpring
[INFO] Parameter: packageName, Value: com.timposu
[INFO] Parameter: version, Value: 1.0-SNAPSHOT
[INFO] project created from Old (1.x) Archetype in dir: /home/ucup/workspace/latihan/AplikasiSpring
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 32.299 s
[INFO] Finished at: 2017-04-27T09:48:33-04:00
[INFO] Final Memory: 17M/107M
[INFO] ------------------------------------------------------------------------
```

### Struktur direktori Maven

```
AplikasiSpring
   |-src
   |---main
   |-----java
   |-------com
   |---------timposu
   |-----------App.java
   |---test
   |-----java
   |-------com
   |---------timposu
   |-----------AppTest.java
   |-pom.xml
```

Selanjutnya tinggal load projectnya lewat IDE Eclipse, Netbeans atau Intllij IDEA, caranya bisa liat di [sini](/apache-maven/)
