ð `Java`ç¸å³èæ¬
====================================

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [ðº show-busy-java-threads](#-show-busy-java-threads)
    - [ç¨æ³](#%E7%94%A8%E6%B3%95)
    - [ç¤ºä¾](#%E7%A4%BA%E4%BE%8B)
    - [è´¡ç®è](#%E8%B4%A1%E7%8C%AE%E8%80%85)
- [ðº show-duplicate-java-classes](#-show-duplicate-java-classes)
    - [ç¨æ³](#%E7%94%A8%E6%B3%95-1)
        - [`JDK`å¼ååºæ¯ä½¿ç¨è¯´æ](#jdk%E5%BC%80%E5%8F%91%E5%9C%BA%E6%99%AF%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E)
            - [å¯¹äºä¸è¬çå·¥ç¨](#%E5%AF%B9%E4%BA%8E%E4%B8%80%E8%88%AC%E7%9A%84%E5%B7%A5%E7%A8%8B)
            - [å¯¹äº`Web`å·¥ç¨](#%E5%AF%B9%E4%BA%8Eweb%E5%B7%A5%E7%A8%8B)
        - [`Android`å¼ååºæ¯ä½¿ç¨è¯´æ](#android%E5%BC%80%E5%8F%91%E5%9C%BA%E6%99%AF%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E)
    - [ç¤ºä¾](#%E7%A4%BA%E4%BE%8B-1)
    - [è´¡ç®è](#%E8%B4%A1%E7%8C%AE%E8%80%85-1)
- [ðº find-in-jars](#-find-in-jars)
    - [ç¨æ³](#%E7%94%A8%E6%B3%95-2)
    - [ç¤ºä¾](#%E7%A4%BA%E4%BE%8B-2)
    - [è¿è¡ææ](#%E8%BF%90%E8%A1%8C%E6%95%88%E6%9E%9C)
    - [åèèµæ](#%E5%8F%82%E8%80%83%E8%B5%84%E6%96%99)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

-------------------------------

å³äº`Java`æéä¸è¯æ­ï¼åèï¸`Arthas`ï¼ â¤ï¸

- `Arthas`ç¨æ·ææ¡£ï¼ https://arthas.aliyun.com/doc/quick-start.html
- GitHub Repoï¼ [alibaba/arthas: Alibaba Javaè¯æ­å©å¨](https://github.com/alibaba/arthas)

`Arthas`åè½å¼å¸¸(ð)å¼ºå²ï¼ä¸å¨é¿éå·´å·´çº¿ä¸æ¯æä½¿ç¨å¤å¹´ãæèªå·±ä¹å¸¸ç¨ï¼ä¸å®è¦ççç¨ç¨ï¼

`Arthas`æ¯éè¿`Agent`æ¹å¼æ¥è¿æ¥è¿è¡ç`Java`è¿ç¨ãä¸»è¦éè¿äº¤äºå¼æ¥å®æåè½ï¼ä¸ä¹å¯¹åºçèæ¬æ¹å¼ä¹æå¶ä¼å¿ï¼å¦ï¼

1. å¯ä»¥å¨è¿ç¨ä¸è½å¯å¨çæåµä¸å®æè¯æ­ï¼å¦ä¾èµä¸­çéå¤ç±»åæã`ClassPath`ä¸çèµæºæç±»æ¥æ¾ï¼
1. å¼éå°ï¼ç®åå°ä¾èµï¼å°±çº¯ææ¬çä¸ä¸ªèæ¬æä»¶ï¼
1. æ¹ä¾¿ä¸ï¼å·²æçï¼å·¥å·ï¼å¦`awk`ã`sed`ã`cron`ï¼ãæµç¨æè®¾æ½éæï¼è¿ä¸æ­¥ç¼ç¨/èªå¨å

è¯·æéæåºæ¯éç¨ã

-------------------------------

<a id="beer-show-busy-java-threadssh"></a>
<a id="beer-show-busy-java-threads"></a>

ðº [show-busy-java-threads](../bin/show-busy-java-threads)
----------------------

ç¨äºå¿«éææ¥`Java`ç`CPU`æ§è½é®é¢(`top us`å¼è¿é«)ï¼èªå¨æ¥åºè¿è¡ç`Java`è¿ç¨ä¸­æ¶è`CPU`å¤ççº¿ç¨ï¼å¹¶æå°åºå¶çº¿ç¨æ ï¼ä»èç¡®å®å¯¼è´æ§è½é®é¢çæ¹æ³è°ç¨ã  
ç®ååªæ¯æ`Linux`ãåå æ¯`Mac`ã`Windows`ç`ps`å½ä»¤ä¸æ¯æååºè¿ç¨ççº¿ç¨`id`ï¼æ´å¤ä¿¡æ¯åè§ [#33](https://github.com/oldratlee/useful-scripts/issues/33)ï¼æ¬¢è¿æä¾è§£æ³ã

PSï¼å¦ä½æä½å¯ä»¥åè§[`@bluedavy`](http://weibo.com/bluedavy)ç[ãåå¸å¼Javaåºç¨ã](https://book.douban.com/subject/4848587/)çã5.1.1 `CPU`æ¶èåæãä¸èï¼è¯´å¾å¾è¯¦ç»ï¼

1. `top`å½ä»¤æ¾åºæ¶è`CPU`é«ç`Java`è¿ç¨åå¶çº¿ç¨`id`ï¼
    1. å¼å¯çº¿ç¨æ¾ç¤ºæ¨¡å¼ï¼`top -H`ï¼ææ¯æå¼`top`åæ`H`ï¼
    1. æ`CPU`ä½¿ç¨çæåºï¼`top`ç¼ºçæ¯æ`CPU`ä½¿ç¨éåºï¼å·²ç»åè¦æ±ï¼æå¼`top`åæ`P`å¯ä»¥æ¾å¼æå®æ`CPU`ä½¿ç¨éåºï¼
    1. è®°ä¸`Java`è¿ç¨`id`åå¶`CPU`é«ççº¿ç¨`id`
1. æ¥çæ¶è`CPU`é«ççº¿ç¨æ ï¼
    1. ç¨è¿ç¨`id`ä½ä¸ºåæ°ï¼`jstack`åºæé®é¢ç`Java`è¿ç¨
    1. æå¨è½¬æ¢çº¿ç¨`id`æåå­è¿å¶ï¼å¯ä»¥ç¨`printf %x 1234`ï¼
    1. å¨`jstack`è¾åºä¸­æ¥æ¾åå­è¿å¶ççº¿ç¨`id`ï¼å¯ä»¥ç¨`vim`çæ¥æ¾åè½`/0x1234`ï¼ææ¯`grep 0x1234 -A 20`ï¼
1. æ¥çå¯¹åºççº¿ç¨æ ï¼åæé®é¢

æ¥é®é¢æ¶ï¼ä¼è¦å¤æ¬¡ä¸é¢çæä½ä»¥åæç¡®å®é®é¢ï¼è¿ä¸ªè¿ç¨**å¤ªç¹çå¤ªæ¢äº**ã  
æææ´åä¸é¢çè¿ç¨æä¸ä¸ªèæ¬ï¼è¿æ ·ä¸è¡å½ä»¤å°±å¯ä»¥èªå¨åå°æå®ã

### ç¨æ³

```bash
show-busy-java-threads
# ä»ææè¿è¡çJavaè¿ç¨ä¸­æ¾åºææ¶èCPUççº¿ç¨ï¼ç¼ºç5ä¸ªï¼ï¼æå°åºå¶çº¿ç¨æ 

# ç¼ºçä¼èªå¨ä»ææçJavaè¿ç¨ä¸­æ¾åºææ¶èCPUççº¿ç¨ï¼è¿æ ·ç¨æ´æ¹ä¾¿
# å½ç¶ä½ å¯ä»¥éè¿ -p éé¡¹ æå¨æå®è¦åæçJavaè¿ç¨Idï¼ä»¥ä¿è¯åªä¼æ¾ç¤ºä½ å³å¿çé£ä¸ªJavaè¿ç¨çä¿¡æ¯
show-busy-java-threads -p <æå®çJavaè¿ç¨Id>
show-busy-java-threads -p 42
show-busy-java-threads -p 42,47

show-busy-java-threads -c <è¦å±ç¤ºç¤ºççº¿ç¨æ ä¸ªæ°>

show-busy-java-threads <éå¤æ§è¡çé´éç§æ°> [<éå¤æ§è¡çæ¬¡æ°>]
# å¤æ¬¡æ§è¡ï¼è¿2ä¸ªåæ°çä½¿ç¨æ¹å¼ç±»ä¼¼vmstatå½ä»¤

show-busy-java-threads -a <è¿è¡è¾åºçè®°å½å°çæä»¶>
# è®°å½å°æä»¶ä»¥æ¹ä¾¿åæº¯æ¥ç

show-busy-java-threads -S <å­å¨jstackè¾åºæä»¶çç®å½>
# æå®jstackè¾åºæä»¶çå­å¨ç®å½ï¼æ¹ä¾¿è®°å½ä»¥åç»­åæ

##############################
# æ³¨æï¼
##############################
# å¦æJavaè¿ç¨çç¨æ· ä¸ æ§è¡èæ¬çå½åç¨æ· ä¸åï¼åjstackä¸äºè¿ä¸ªJavaè¿ç¨
# ä¸ºäºè½åæ¢å°Javaè¿ç¨çç¨æ·ï¼éè¦å sudoæ¥æ§è¡ï¼å³å¯ä»¥è§£å³ï¼
sudo show-busy-java-threads

show-busy-java-threads -s <æå®jstackå½ä»¤çå¨è·¯å¾>
# å¯¹äºsudoæ¹å¼çè¿è¡ï¼JAVA_HOMEç¯å¢åéä¸è½ä¼ éç»rootï¼
# èrootç¨æ·å¾å¾æ²¡æéç½®JAVA_HOMEä¸ä¸æ¹ä¾¿éç½®ï¼ä¸è½æ¾å°jstackå½ä»¤ã
# è¿æ¶æ¾å¼æå®jstackå½ä»¤çè·¯å¾å°±åèæ¾å¾æ´æ¹ä¾¿äº

# -m éé¡¹ï¼æ§è¡jstackå½ä»¤æ¶å ä¸ -m éé¡¹ï¼æ¾ç¤ºä¸Nativeçæ å¸§ï¼ä¸è¬åºç¨ææ¥ä¸éè¦ä½¿ç¨
show-busy-java-threads -m
# -F éé¡¹ï¼æ§è¡jstackå½ä»¤æ¶å ä¸ -F éé¡¹ï¼å¦æç´æ¥jstackæ ååºæ¶ï¼ç¨äºå¼ºå¶jstackï¼ï¼ä¸è¬æåµä¸éè¦ä½¿ç¨
show-busy-java-threads -F
# -l éé¡¹ï¼æ§è¡jstackå½ä»¤æ¶å ä¸ -l éé¡¹ï¼æ¾ç¤ºä¸æ´å¤ç¸å³éçä¿¡æ¯ï¼ä¸è¬æåµä¸éè¦ä½¿ç¨
# æ³¨æï¼å -m -F éé¡¹ä¸èµ·ä½¿ç¨æ¶ï¼å¯è½ä¼å¤§å¤§å¢å jstackæä½çèæ¶
show-busy-java-threads -l

# å¸®å©ä¿¡æ¯
$ show-busy-java-threads -h
Usage: show-busy-java-threads [OPTION]... [delay [count]]
Find out the highest cpu consumed threads of java processes,
and print the stack of these threads.

Example:
  show-busy-java-threads       # show busy java threads info
  show-busy-java-threads 1     # update every 1 second, (stop by eg: CTRL+C)
  show-busy-java-threads 3 10  # update every 3 seconds, update 10 times

Output control:
  -p, --pid <java pid(s)>   find out the highest cpu consumed threads from
                            the specified java process.
                            support pid list(eg: 42,47).
                            default from all java process.
  -c, --count <num>         set the thread count to show, default is 5.
                            set count 0 to show all threads.
  -a, --append-file <file>  specifies the file to append output as log.
  -S, --store-dir <dir>     specifies the directory for storing
                            the intermediate files, and keep files.
                            default store intermediate files at tmp dir,
                            and auto remove after run. use this option to keep
                            files so as to review jstack/top/ps output later.
  delay                     the delay between updates in seconds.
  count                     the number of updates.
                            delay/count arguments imitates the style of
                            vmstat command.

jstack control:
  -s, --jstack-path <path>  specifies the path of jstack command.
  -F, --force               set jstack to force a thread dump.
                            use when jstack does not respond (process is hung).
  -m, --mix-native-frames   set jstack to print both java and
                            native frames (mixed mode).
  -l, --lock-info           set jstack with long listing.
                            prints additional information about locks.

CPU usage calculation control:
  -i, --cpu-sample-interval specifies the delay between cpu samples to get
                            thread cpu usage percentage during this interval.
                            default is 0.5 (second).
                            set interval 0 to get the percentage of time spent
                            running during the *entire lifetime* of a process.

Miscellaneous:
  -h, --help                display this help and exit.
  -V, --version             display version information and exit.
```

### ç¤ºä¾

```bash
$ show-busy-java-threads
[1] Busy(57.0%) thread(23355/0x5b3b) stack of java process(23269) under user(admin):
"pool-1-thread-1" prio=10 tid=0x000000005b5c5000 nid=0x5b3b runnable [0x000000004062c000]
   java.lang.Thread.State: RUNNABLE
    at java.text.DateFormat.format(DateFormat.java:316)
    at com.xxx.foo.services.common.DateFormatUtil.format(DateFormatUtil.java:41)
    at com.xxx.foo.shared.monitor.schedule.AppMonitorDataAvgScheduler.run(AppMonitorDataAvgScheduler.java:127)
    at com.xxx.foo.services.common.utils.AliTimer$2.run(AliTimer.java:128)
    at java.util.concurrent.ThreadPoolExecutor$Worker.runTask(ThreadPoolExecutor.java:886)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:908)
    at java.lang.Thread.run(Thread.java:662)

[2] Busy(26.1%) thread(24018/0x5dd2) stack of java process(23269) under user(admin):
"pool-1-thread-2" prio=10 tid=0x000000005a968800 nid=0x5dd2 runnable [0x00000000420e9000]
   java.lang.Thread.State: RUNNABLE
    at java.util.Arrays.copyOf(Arrays.java:2882)
    at java.lang.AbstractStringBuilder.expandCapacity(AbstractStringBuilder.java:100)
    at java.lang.AbstractStringBuilder.append(AbstractStringBuilder.java:572)
    at java.lang.StringBuffer.append(StringBuffer.java:320)
    - locked <0x00000007908d0030> (a java.lang.StringBuffer)
    at java.text.SimpleDateFormat.format(SimpleDateFormat.java:890)
    at java.text.SimpleDateFormat.format(SimpleDateFormat.java:869)
    at java.text.DateFormat.format(DateFormat.java:316)
    at com.xxx.foo.services.common.DateFormatUtil.format(DateFormatUtil.java:41)
    at com.xxx.foo.shared.monitor.schedule.AppMonitorDataAvgScheduler.run(AppMonitorDataAvgScheduler.java:126)
    at com.xxx.foo.services.common.utils.AliTimer$2.run(AliTimer.java:128)
    at java.util.concurrent.ThreadPoolExecutor$Worker.runTask(ThreadPoolExecutor.java:886)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:908)
    at java.lang.Thread.run(Thread.java:662)

......
```

ä¸é¢ççº¿ç¨æ å¯ä»¥çåºï¼`CPU`æ¶èæé«ç2ä¸ªçº¿ç¨é½å¨æ§è¡`java.text.DateFormat.format`ï¼ä¸å¡ä»£ç å¯¹åºçæ¹æ³æ¯`shared.monitor.schedule.AppMonitorDataAvgScheduler.run`ãå¯ä»¥åºæ¬ç¡®å®ï¼

- `AppMonitorDataAvgScheduler.run`è°ç¨`DateFormat.format`æ¬¡æ°æ¯è¾é¢ç¹ã
- `DateFormat.format`æ¯è¾æ¢ãï¼è¿ä¸ªå¯ä»¥ç±`DateFormat.format`çå®ç°ç¡®å®ãï¼

å¤æ§è¡å æ¬¡`show-busy-java-threads`ï¼å¦æä¸é¢æåµé«æ¦çåºç°ï¼åå¯ä»¥ç¡®å®ä¸é¢çå¤å®ã  
å ä¸ºè°ç¨è¶å°ä»£ç æ§è¡è¶å¿«ï¼ååºç°å¨çº¿ç¨æ çæ¦çå°±è¶ä½ã  
èæ¬æèªå¨å¤æ¬¡æ§è¡çåè½ï¼æå® éå¤æ§è¡çé´éç§æ°/éå¤æ§è¡çæ¬¡æ° åæ°ã

åæ`shared.monitor.schedule.AppMonitorDataAvgScheduler.run`å®ç°é»è¾åè°ç¨æ¹å¼ï¼ä»¥ä¼åå®ç°è§£å³é®é¢ã

### è´¡ç®è

- [silentforce](https://github.com/silentforce) æ¹è¿æ­¤èæ¬ï¼å¢å å¯¹ç¯å¢åé`JAVA_HOME`çå¤æ­ã [#15](https://github.com/oldratlee/useful-scripts/pull/15)
- [liuyangc3](https://github.com/liuyangc3)
    - åç°å¹¶è§£å³`jstack`éå½åç¨æ·`Java`è¿ç¨çé®é¢ã [#50](https://github.com/oldratlee/useful-scripts/pull/50)
    - ä¼åæ§è½ï¼éè¿`read -a`ç®ååå¤ç`awk`æä½ã [#51](https://github.com/oldratlee/useful-scripts/pull/51)
- [superhj1987](https://github.com/superhj1987) / [lirenzuo](https://github.com/lirenzuo)
    - æåº/å®ç°äºå¤æ¬¡æ§è¡çåè½ [superhj1987/awesome-scripts#1](https://github.com/superhj1987/awesome-scripts/issues/1)
- [xiongchen2012](https://github.com/xiongchen2012) æåºå¹¶è§£å³äºé¿ç¨æ·åæªæ­çBug [#62](https://github.com/oldratlee/useful-scripts/pull/62)
- [qsLI](https://github.com/qsLI) / [sdslnmd](https://github.com/sdslnmd)
    - åç°å¹¶æäº¤Issueï¼show-busy-java-threadsæ¯ætopæ¥è·åcpuå ç¨çï¼psçcpuå ç¨çéå®æ¶ [#67](https://github.com/oldratlee/useful-scripts/issues/67)
- [geekMessi](https://github.com/geekMessi)
    - åç°å¹¶æäº¤Issueï¼å¨`top v3.2`ä¸æåä¸æ­£ç¡®çBug [#71](https://github.com/oldratlee/useful-scripts/issues/71)
    - åç°å¹¶æäº¤Issueï¼support command name jsvc to find java process [#72](https://github.com/oldratlee/useful-scripts/issues/72)

ðº [show-duplicate-java-classes](../bin/show-duplicate-java-classes)
----------------------

æ¾åº`Java Lib`ï¼`Java`åºï¼å³`Jar`æä»¶ï¼æ`Class`ç®å½ï¼ç±»ç®å½ï¼ä¸­çéå¤ç±»ã  
å¨ç³»ç»æ¯æï¼`Python 3`å®ç°ï¼å®è£`Python 3`å³å¯ï¼ï¼å¦`Linux`ã`Mac`ã`Windows`ã

`Java`å¼åçä¸ä¸ªéº»ç¦çé®é¢æ¯`Jar`å²çªï¼å³å¤ä¸ªçæ¬ç`Jar`ï¼ï¼æèè¯´éå¤ç±»ãä¼åº`NoSuchMethod`ç­çé®é¢ï¼è¿ä¸è§å¾å½æ¶åºé®é¢ãæ¾åºæéå¤ç±»ç`Jar`ï¼å¯ä»¥é²æ£æªç¶ã

### ç¨æ³

- éè¿èæ¬åæ° æå® `Libs`ç®å½ï¼æ¥æ¾ç®å½ä¸`Jar`æä»¶ï¼æ¶é`Jar`æä»¶ä¸­`Class`æä»¶ä»¥åæéå¤ç±»ãå¯ä»¥æå®å¤ä¸ª`Libs`ç®å½ã
    - ç¼ºçåªä¼æ¥æ¾æå®`Lib`ç®å½ä¸`Jar`æä»¶ï¼ä¸ä¼æ¶é`Lib`ç®å½çå­ç®å½ä¸`Jar`æä»¶ã
        - å ä¸º`Libs`ç®å½ä¸è¬ä¸ä¼ç¨å­ç®å½åæ¾`Jar`ï¼ä¹é¿åæå»æ¥æ¾ä¸ææç`Jar`æä»¶ã
        - å¯ä»¥éè¿ `-L`éé¡¹ è®¾ç½® æ¶é`Lib`å­ç®å½ä¸ç`Jar`æä»¶ï¼è¿æ ·å¯ä»¥ç®å`Lib`ç®å½çè®¾ç½®ï¼ä¸éè¦æå®å®æ´ç`Lib`ç®å½è·¯å¾ã
    - å¯¹äºæ¾å°ç`Jar`æä»¶ï¼ç¼ºçä¸ä¼è¿ä¸æ­¥æ¶éåå«å¨`Jar`æä»¶ä¸­ç`Jar`ã
        - å³`FatJar`/`UberJar`çåºæ¯ï¼éçå`SpringBoot`çå¹¿æ³ä½¿ç¨ï¼`FatJar`/`UberJar`ä¹æ¯è¾å¸¸è§ã
        - å¯ä»¥éè¿ `-J`éé¡¹ è®¾ç½® æ¶éåå«å¨`Jar`æä»¶ä¸­ç`Jar`ã
- éè¿`-c`éé¡¹ æå® `Class`ç®å½ï¼ç´æ¥æ¶éè¿ä¸ªç®å½ä¸ç`Class`æä»¶ä»¥åæéå¤ç±»ãå¯ä»¥å¤æ¬¡æå®å¤ä¸ª`Class`ç®å½ã

```bash
# æ¥æ¾å½åç®å½ä¸ææJarä¸­çéå¤ç±»
show-duplicate-java-classes

# æ¥æ¾å¤ä¸ªæå®ç®å½ä¸ææJarä¸­çéå¤ç±»
show-duplicate-java-classes path/to/lib_dir1 /path/to/lib_dir2
# éè¿ -L éé¡¹ï¼æ¶éå­ç®å½ä¸­çJaræä»¶
show-duplicate-java-classes -L path/to/lib_dir1
# éè¿ -J éé¡¹ï¼æ¶éåå«å¨Jaræä»¶ä¸­çJaræä»¶ï¼å³ æ¶éåå«å¨FatJar/UberJarä¸­çJarï¼
show-duplicate-java-classes -J path/to/lib_dir1

# æ¥æ¾å¤ä¸ªæå®Classç®å½ä¸çéå¤ç±»ã Classç®å½ éè¿ -c éé¡¹æå®
show-duplicate-java-classes -c path/to/class_dir1 -c /path/to/class_dir2

# æ¥æ¾æå®Classç®å½åæå®ç®å½ä¸ææJarä¸­çéå¤ç±»çJar
show-duplicate-java-classes path/to/lib_dir1 /path/to/lib_dir2 -c path/to/class_dir1 -c path/to/class_dir2

# å¸®å©ä¿¡æ¯
$ show-duplicate-java-classes -h
Usage: show-duplicate-java-classes [OPTION]... [-c class-dir1 [-c class-dir2] ...] [lib-dir1|jar-file1 [lib-dir2|jar-file2] ...]
Find duplicate classes among java lib dirs and class dirs.

Examples:
  show-duplicate-java-classes  # search jars from current dir
  show-duplicate-java-classes path/to/lib_dir1 /path/to/lib_dir2
  show-duplicate-java-classes -c path/to/class_dir1 -c /path/to/class_dir2
  show-duplicate-java-classes -c path/to/class_dir1 path/to/lib_dir1
  show-duplicate-java-classes -L path/to/lib_dir1
  show-duplicate-java-classes -J path/to/lib_dir1

Options:
  --version             show program's version number and exit
  -h, --help            show this help message and exit
  -L, --recursive-lib   search jars in the sub-directories of lib dir
  -J, --recursive-jar   search jars in the jar file
  -c CLASS_DIRS, --class-dir=CLASS_DIRS
                        add class dir
  -R, --no-find-progress
                        do not display responsive find progress
```

#### `JDK`å¼ååºæ¯ä½¿ç¨è¯´æ

ä»¥`Maven`ä½ä¸ºæå»ºå·¥ç¨ç¤ºæè¿ç¨ã

##### å¯¹äºä¸è¬çå·¥ç¨

```sh
# å¨é¡¹ç®æ¨¡åç®å½ä¸æ§è¡ï¼æ·è´ä¾èµJarå°ç®å½target/dependencyä¸
$ mvn dependency:copy-dependencies -DincludeScope=runtime
...
# æ£æ¥éå¤ç±»
$ show-duplicate-java-classes target/dependency
...
```

##### å¯¹äº`Web`å·¥ç¨

å¯¹äº`Web`å·¥ç¨ï¼å³`war` `maven`æ¨¡åï¼ä¼æåçæ`war`æä»¶ã

```sh
# å¨waræ¨¡åç®å½ä¸æ§è¡ï¼çæwaræä»¶
$ mvn install
...
# è§£åwaræä»¶ï¼waræä»¶ä¸­åå«äºåºç¨çä¾èµçJaræä»¶
$ unzip target/*.war -d target/war
...
# æ£æ¥éå¤ç±»
$ show-duplicate-java-classes -c target/war/WEB-INF/classes target/war/WEB-INF/lib
...
```

#### `Android`å¼ååºæ¯ä½¿ç¨è¯´æ

`Android`å¼åï¼æéå¤ç±»å¨ç¼è¯æåæ¶ä¼æ¥`[Dex Loader] Unable to execute dex: Multiple dex files define Lorg/foo/xxx/Yyy`ã

ä½åªä¼ç»åºä¸ä¸ªéå¤ç±»åï¼å¦æéå¤ç±»æ¯è¾å¤æ¶ï¼ä¸é¢æå/æ¥é/ææ¥ä¼è¦è¿è¡å¤æ¬¡ï¼è`Android`çæåæ¯è¾è´¹æ¶ï¼è¿ä¸ªè¿ç¨æ¯è¾éº»ç¦ï¼å¸æå¯ä»¥ä¸æ¬¡æææéå¤ç±»é½ååºæ¥ï¼ä¸èµ·ææ¥æã

ä»¥`Gradle`ä½ä¸ºæå»ºå·¥ç¨ç¤ºæè¿ç¨ã

å¨`App`ç`build.gradle`ä¸­æ·»å æ·è´åºå°ç®å½`build/dependencies`ä¸ã

```groovy
task copyDependencies(type: Copy) {
    def dest = new File(buildDir, "dependencies")

    // clean dir
    dest.deleteDir()
    dest.mkdirs()

    // fill dir with dependencies
    from configurations.compile into dest
}
```

```sh
# æ·è´ä¾èµ
$ ./gradlew app:copyDependencies
...
# æ£æ¥éå¤ç±»
$ show-duplicate-java-classes app/build/dependencies
...
```

### ç¤ºä¾

```bash
$ show-duplicate-java-classes WEB-INF/lib
COOL! No duplicate classes found!

================================================================================
Find in 150 class paths:
================================================================================
  1: (contain   9 classes) WEB-INF/lib/aopalliance-1.0.jar
  2: (contain  25 classes) WEB-INF/lib/asm-5.0.4.jar
  3: (contain 313 classes) WEB-INF/lib/aviator-5.0.0.jar
  4: (contain 687 classes) WEB-INF/lib/cassandra-0.6.1.jar
...

$ show-duplicate-java-classes -c WEB-INF/classes WEB-INF/lib
Found 1272 duplicate classes in 345 class paths and 9 class path sets:
[1] found 188(100%) duplicate classes in 3 class paths:
    1: (contain 188 classes) WEB-INF/lib/jdom-2.0.2.jar
    2: (contain 195 classes) WEB-INF/lib/jdom2-2.0.6.jar
    3: (contain 195 classes) WEB-INF/lib/jdom2-2.0.8.jar
[2] found 150(33.8%) duplicate classes in 2 class paths:
    1: (contain 1385 classes) WEB-INF/lib/netty-all-4.0.35.Final.jar
    2: (contain  444 classes) WEB-INF/lib/netty-common-4.1.31.Final.jar
[3] found 148(55.4%) duplicate classes in 2 class paths:
    1: (contain 1385 classes) WEB-INF/lib/netty-all-4.0.35.Final.jar
    2: (contain  267 classes) WEB-INF/lib/netty-handler-4.1.31.Final.jar
[4] found 103(82.4%) duplicate classes in 2 class paths:
    1: (contain 125 classes) WEB-INF/lib/hessian-3.0.14.bugfix.jar
    2: (contain 275 classes) WEB-INF/lib/hessian-4.0.38.jar
...

================================================================================
Duplicate classes detail info:
================================================================================
[1] found 188 duplicate classes in 3 class paths WEB-INF/lib/jdom-2.0.2.jar WEB-INF/lib/jdom2-2.0.6.jar WEB-INF/lib/jdom2-2.0.8.jar :
      1: org/jdom2/Attribute.class
      2: org/jdom2/AttributeList$1.class
      3: org/jdom2/AttributeList$ALIterator.class
      4: org/jdom2/AttributeList.class
      5: org/jdom2/AttributeType.class
      ...
[2] found 150 duplicate classes in 2 class paths WEB-INF/lib/netty-all-4.0.35.Final.jar WEB-INF/lib/netty-common-4.1.31.Final.jar :
      1: io/netty/util/AbstractReferenceCounted.class
      2: io/netty/util/Attribute.class
      3: io/netty/util/AttributeKey.class
      4: io/netty/util/AttributeMap.class
      5: io/netty/util/CharsetUtil.class
      ...
...

================================================================================
Find in 232 class paths:
================================================================================
  1: (contain  42 classes) WEB-INF/classes
  2: (contain  70 classes) WEB-INF/lib/HikariCP-2.7.8.jar
  3: (contain  13 classes) WEB-INF/lib/accessors-smart-1.2.jar
  4: (contain   9 classes) WEB-INF/lib/aopalliance-1.0.jar
  5: (contain  25 classes) WEB-INF/lib/asm-5.0.4.jar
  6: (contain 313 classes) WEB-INF/lib/aviator-5.0.0.jar
...
```

### è´¡ç®è

[tgic](https://github.com/tg123) æä¾æ­¤èæ¬ãåæè´¡ç®èçé¾æ¥ [commandlinefu.cn](http://commandlinefu.cn/) | [å¾®ålinuxå½ä»¤è¡ç²¾é](http://weibo.com/u/2674868673)

<a id="beer-find-in-jarssh"></a>
<a id="beer-find-in-jars"></a>

ðº [find-in-jars](../bin/find-in-jars)
----------------------

å¨å½åç®å½ä¸ææ`jar`æä»¶éï¼æ¥æ¾ç±»æèµæºæä»¶ã  
æ¯æ`Linux`ã`Mac`ã`Windows`ï¼`cygwin`ã`MSSYS`ï¼ã

### ç¨æ³

```bash
# å¨å½åç®å½ä¸ææ`jar`æä»¶éï¼æ¥æ¾ç±»æèµæºæä»¶ã
find-in-jars 'log4j\.properties'
find-in-jars 'log4j\.xml$'
find-in-jars log4j\\.xml$ # åä¸é¢å½ä»¤ä¸æ ·ï¼Shellè½¬ä¹çä¸ååæ³èå·²
find-in-jars 'log4j\.(properties|xml)$'

# -déé¡¹ æå® æ¥æ¾ç®å½ï¼è¦çç¼ºççå½åç®å½ï¼
find-in-jars 'log4j\.properties$' -d /path/to/find/directory
# æ¯æå¤ä¸ªæ¥æ¾ç®å½ï¼å¤æ¬¡æå®è¿ä¸ªéé¡¹å³å¯
find-in-jars 'log4j\.properties' -d /path/to/find/directory1 -d /path/to/find/directory2

# -eéé¡¹ æå® æ¥æ¾`zip`æä»¶çæ©å±åï¼ç¼ºçæ¯`jar`
find-in-jars 'log4j\.properties' -e zip
# æ¯æå¤ç§æ¥æ¾æ©å±åï¼å¤æ¬¡æå®è¿ä¸ªéé¡¹å³å¯
find-in-jars 'log4j\.properties' -e jar -e zip

# -aéé¡¹ æå® æ¥æ¾ç»æä¸­çJaræä»¶ä½¿ç¨ç»å¯¹è·¯å¾
# åäº«ç»å«äººæ¶ï¼Jaræä»¶è·¯å¾æ¯å®æ´çï¼æ¹ä¾¿å«äººæ¾å°æä»¶
find-in-jars 'log4j\.properties' -a

# -séé¡¹ æå® æ¥æ¾ç»æä¸­çJaræä»¶åJaræä»¶éçæ¥æ¾Entryé´åéç¬¦ï¼ç¼ºçæ¯ã!ã
# æ¹ä¾¿ä½ åæ¬¢çäººç¼æ¥çï¼ææ¯ä¸å·¥å·èæ¬å¦`awk`çå¤ç
find-in-jars 'log4j\.properties' -s ' <-> '
find-in-jars 'log4j\.properties' -s ' ' | awk '{print $2}'

# -léé¡¹ æå® åªååºJaræä»¶ï¼ä¸æ¾ç¤ºJaræä»¶åå¹éçæä»¶åè¡¨
# ååº åå«log4j.xmlæä»¶çJaræä»¶ï¼
find-in-jars -l 'log4j\.xml$'

# å¸®å©ä¿¡æ¯
$ find-in-jars -h
Usage: find-in-jars [OPTION]... PATTERN

Find files in the jar files under specified directory,
search jar files recursively(include subdirectory).
The pattern default is *extended* regex.

Example:
  find-in-jars 'log4j\.properties'
  # search file log4j.properties/log4j.xml at zip root
  find-in-jars '^log4j\.(properties|xml)$'
  find-in-jars 'log4j\.properties$' -d /path/to/find/directory
  find-in-jars '\.properties$' -d /path/to/find/dir1 -d path/to/find/dir2
  find-in-jars 'Service\.class$' -e jar -e zip
  find-in-jars 'Mon[^$/]*Service\.class$' -s ' <-> '

Find control:
  -d, --dir              the directory that find jar files.
                         default is current directory. this option can specify
                         multiply times to find in multiply directories.
  -e, --extension        set find file extension, default is jar. this option
                         can specify multiply times to find multiply extension.
  -E, --extended-regexp  PATTERN is an extended regular expression (*default*)
  -F, --fixed-strings    PATTERN is a set of newline-separated strings
  -G, --basic-regexp     PATTERN is a basic regular expression
  -P, --perl-regexp      PATTERN is a Perl regular expression
  -i, --ignore-case      ignore case distinctions

Output control:
  -a, --absolute-path    always print absolute path of jar file
  -s, --separator        specify the separator between jar file and zip entry.
                         default is `!'.
  -L, --files-not-contained-found
                         print only names of JAR FILEs NOT contained found
  -l, --files-contained-found
                         print only names of JAR FILEs contained found
  -R, --no-find-progress do not display responsive find progress

Miscellaneous:
  -h, --help             display this help and exit
  -V, --version          display version information and exit
```

æ³¨æï¼Patternç¼ºçæ¯`grep`ç **æ©å±**æ­£åè¡¨è¾¾å¼ã

### ç¤ºä¾

```bash
# å¨å½åç®å½ä¸çææJaræä»¶ä¸­ï¼æ¥æ¾åº log4j.propertiesæä»¶
$ find-in-jars 'log4j\.properties$'
./hadoop-core-0.20.2-cdh3u3.jar!log4j.properties
......

# æ¥æ¾åº ä»¥Serviceç»å°¾çç±»ï¼Jaræä»¶è·¯å¾è¾åºæç»å¯¹è·¯å¾
$ find-in-jars 'Service.class$' -a
/home/foo/deploy/app/WEB-INF/libs/spring-2.5.6.SEC03.jar!org/springframework/stereotype/Service.class
/home/foo/deploy/app/WEB-INF/libs/rpc-hello-0.0.1-SNAPSHOT.jar!com/taobao/biz/HelloService.class
......

# å¨æå®çå¤ä¸ªç®å½çJaræä»¶ä¸­ï¼æ¥æ¾åº propertiesæä»¶
$ find-in-jars '\.properties$' -d WEB-INF/lib -d ../deploy/lib | grep -v '/pom\.properties$'
WEB-INF/lib/aspectjtools-1.6.2.jar!org/aspectj/ajdt/ajc/messages.properties
WEB-INF/lib/aspectjweaver-1.8.8.jar!org/aspectj/weaver/XlintDefault.properties
../deploy/lib/groovy-all-1.1-rc-1.jar!groovy/ui/InteractiveShell.properties
../deploy/lib/httpcore-4.3.3.jar!org/apache/http/version.properties
../deploy/lib/javax.servlet-api-3.0.1.jar!javax/servlet/http/LocalStrings_es.properties
......

# ååº åå«propertiesæä»¶çJaræä»¶
$ find-in-jars '\.properties$' -l -d WEB-INF/lib
WEB-INF/lib/aspectjtools-1.6.2.jar
WEB-INF/lib/aspectjweaver-1.8.8.jar
WEB-INF/lib/javax.servlet-api-3.0.1.jar
......
```

### è¿è¡ææ

æ¯æå½©è²è¾åºï¼æä»¶åä¸­çå¹éé¨åä»¥`grep`çé«äº®æ¹å¼æ¾ç¤ºã

![find-in-jar screenshot](https://user-images.githubusercontent.com/1063891/33545067-9eb66072-d8a2-11e7-8a77-d815c0979e5e.gif)

### åèèµæ

[å¨å¤ä¸ªJar(Zip)æä»¶æ¥æ¾Log4Jéç½®æä»¶çShellå½ä»¤è¡](http://oldratlee.github.io/458/tech/shell/find-file-in-jar-zip-files.html)
