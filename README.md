ð useful scripts for making developer's everyday life easier and happier, involved java, shell etc.  
ð å¹³æ¶æç¨çæå¨æä½åæèæ¬ï¼ä»¥ä¾¿æ·å°ä½¿ç¨ï¼è®©å¼åçæ¥å¸¸çæ´»æ´è½»æ¾äºã ð

æ¬¢è¿ ð ð

- æé®ï¼[æäº¤ Issue](https://github.com/oldratlee/useful-scripts/issues/new)
- åäº«å¹³æ¶èªå·±å¸¸ç¨ä½æ²¡æåæèæ¬çåè½ï¼å³éæ±ãæ³æ³ï¼ï¼[æäº¤Issue](https://github.com/oldratlee/useful-scripts/issues/new)
- ä¼åæ¹è¿ï¼[Fork åæéè¿ Pull Request è´¡ç®ä»£ç ](https://github.com/oldratlee/useful-scripts/fork)
- æä¾çèªå·±å¥½ç¨èæ¬å®ç°ï¼[Fork åæéè¿ Pull Request æä¾](https://github.com/oldratlee/useful-scripts/fork)

æ¬ä»åºçèæ¬ï¼å¦`Java`ç¸å³èæ¬ï¼å¨é¿éç­å¬å¸ï¼å¦éèº«äºï¼è§[`awesome-scripts`ä»åº](https://github.com/Suishenyun/awesome-scripts)è¯´æï¼ççº¿ä¸çäº§ç¯å¢é¨ç½²ä½¿ç¨ã

å¦æä½ çå¬å¸æé¨ç½²ä½¿ç¨ï¼æ¬¢è¿ä½¿ç¨éè¿ [Issueï¼who's using | ç¨æ·åé¦æ¶é](https://github.com/oldratlee/useful-scripts/issues/96) åç¥ï¼æ¹ä¾¿äºç¸äº¤æµåé¦ï½ ð

----------------------

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [ð° å¿«éä¸è½½&ä½¿ç¨](#-%E5%BF%AB%E9%80%9F%E4%B8%8B%E8%BD%BD%E4%BD%BF%E7%94%A8)
- [ð ä½¿ç¨ææ¡£](#-%E4%BD%BF%E7%94%A8%E6%96%87%E6%A1%A3)
    - [â `Java`ç¸å³èæ¬](#-java%E7%9B%B8%E5%85%B3%E8%84%9A%E6%9C%AC)
    - [ð `Shell`ç¸å³èæ¬](#-shell%E7%9B%B8%E5%85%B3%E8%84%9A%E6%9C%AC)
    - [â `VCS`ç¸å³èæ¬](#-vcs%E7%9B%B8%E5%85%B3%E8%84%9A%E6%9C%AC)
- [ð Developer Guide](#-developer-guide)
    - [ð¯ é¢åå¼åèçç®æ ](#-%E9%9D%A2%E5%90%91%E5%BC%80%E5%8F%91%E8%80%85%E7%9A%84%E7%9B%AE%E6%A0%87)
        - [å³äº`Shell`èæ¬](#%E5%85%B3%E4%BA%8Eshell%E8%84%9A%E6%9C%AC)
    - [ð¦ å¼åçº¦å®](#-%E5%BC%80%E5%8F%91%E7%BA%A6%E5%AE%9A)
    - [ð `Shell`å­¦ä¹ ä¸å¼åçèµæ](#-shell%E5%AD%A6%E4%B9%A0%E4%B8%8E%E5%BC%80%E5%8F%91%E7%9A%84%E8%B5%84%E6%96%99)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

----------------------

ð° å¿«éä¸è½½&ä½¿ç¨
----------------------

```bash
source <(curl -fsSL https://raw.githubusercontent.com/oldratlee/useful-scripts/release-2.x/test-cases/self-installer.sh)
```

æ´å¤ä¸è½½&ä½¿ç¨æ¹å¼ï¼åè§[ä¸è½½ä½¿ç¨](docs/install.md)ã

ð ä½¿ç¨ææ¡£
----------------------

### â [`Java`ç¸å³èæ¬](docs/java.md)

1. [show-busy-java-threads](docs/java.md#-show-busy-java-threads)  
    ç¨äºå¿«éææ¥`Java`ç`CPU`æ§è½é®é¢(`top us`å¼è¿é«)ï¼èªå¨æ¥åºè¿è¡ç`Java`è¿ç¨ä¸­æ¶è`CPU`å¤ççº¿ç¨ï¼å¹¶æå°åºå¶çº¿ç¨æ ï¼ä»èç¡®å®å¯¼è´æ§è½é®é¢çæ¹æ³è°ç¨ã
1. [show-duplicate-java-classes](docs/java.md#-show-duplicate-java-classes)  
    æ¾åº`jar`æä»¶å`class`ç®å½ä¸­çéå¤ç±»ãç¨äºææ¥`Java`ç±»å²çªé®é¢ã
1. [find-in-jars](docs/java.md#-find-in-jars)  
    å¨ç®å½ä¸ææ`jar`æä»¶éï¼æ¥æ¾ç±»æèµæºæä»¶ã

### ð [`Shell`ç¸å³èæ¬](docs/shell.md)

`Shell`ä½¿ç¨å å¼ºï¼

1. [c](docs/shell.md#-c)  
    åæ ·å½ä»¤è¡è¾åºï¼å¹¶æ·è´æ åè¾åºå°ç³»ç»åªè´´æ¿ï¼çå»`CTRL+C`æä½ï¼ä¼åå½ä»¤è¡ä¸å¶å®åºç¨ä¹é´çæä½æµã
1. [coat](docs/shell.md#-coat)  
    å½©è²`cat`åºæä»¶è¡ï¼æ¹ä¾¿äººç¼åºåä¸åçè¡ã
1. [a2l](docs/shell.md#-a2l)  
    æè¡å½©è²è¾åºåæ°ï¼æ¹ä¾¿äººç¼æ¥çã
1. [uq](docs/shell.md#-uq)  
    ä¸éæåºè¾å¥å®ææ´ä¸ªè¾å¥è¡çå»éãç¸æ¯ç³»ç»ç`uniq`å½ä»¤å å¼ºçæ¯å¯ä»¥è·¨è¡å»éï¼ä¸éè¦æåºè¾å¥ã
1. [ap and rp](docs/shell.md#-ap-and-rp)  
    æ¹éè½¬æ¢æä»¶è·¯å¾ä¸ºç»å¯¹è·¯å¾/ç¸å¯¹è·¯å¾ï¼ä¼èªå¨è·è¸ªé¾æ¥å¹¶è§èåè·¯å¾ã
1. [cp-into-docker-run](docs/shell.md#-cp-into-docker-run)  
    ä¸ä¸ª`Docker`ä½¿ç¨çä¾¿å©èæ¬ãæ·è´æ¬æºçæ§è¡æä»¶å°æå®ç`docker container`ä¸­å¹¶å¨`docker container`ä¸­æ§è¡ã
1. [tcp-connection-state-counter](docs/shell.md#-tcp-connection-state-counter)  
    ç»è®¡åä¸ª`TCP`è¿æ¥ç¶æçä¸ªæ°ãç¨äºæ¹ä¾¿ææ¥ç³»ç»è¿æ¥è´è·é®é¢ã
1. [xpl and xpf](docs/shell.md#-xpl-and-xpf)  
    å¨å½ä»¤è¡ä¸­å¿«éå®æ å¨æä»¶æµè§å¨ä¸­ æå¼/éä¸­ æå®çæä»¶ææä»¶å¤¹çæä½ï¼ä¼åå½ä»¤è¡ä¸å¶å®åºç¨ä¹é´çæä½æµã

`Shell`å¼å/æµè¯å å¼ºï¼

1. [echo-args](docs/shell.md#-echo-args)  
    è¾åºèæ¬æ¶å°çåæ°ï¼å¨æ§å¶å°è¿è¡æ¶ï¼æåæ°å¼æ¬èµ·çæ¬å·æ¾ç¤ºæ **çº¢è²**ï¼æ¹ä¾¿äººç¼æ¥çãç¨äºè°è¯èæ¬åæ°è¾å¥ã
1. [console-text-color-themes.sh](docs/shell.md#-console-text-color-themessh)  
    æ¾ç¤º`Terminator`çå¨é¨æå­å½©è²ç»åçææåå¶æå°æ¹å¼ï¼ç¨äºå¼å`Shell`çå½©è²è¾åºã
1. [parseOpts.sh](docs/shell.md#-parseoptssh)  
    å½ä»¤è¡éé¡¹è§£æåºï¼å å¼ºæ¯æéé¡¹æå¤ä¸ªå¼ï¼å³æ°ç»ï¼ã

### â [`VCS`ç¸å³èæ¬](docs/vcs.md)

ç®å`VCS`çèæ¬é½æ¯`svn`åæ¯ç¸å³çæä½ãä½¿ç¨æ´ç°ä»£ç`Git`å§ï¼ ð¥

å ä¸ºä¸æ¨èä½¿ç¨`svn`ï¼è¿éä¸åååºæåªäºèæ¬äºï¼å¦æä½ æå´è¶£å¯ä»¥ç¹ä¸é¢é¾æ¥å»çã

## ð Developer Guide

ä¸ºç¨æ·æä¾æç¨çåè½ï¼å½ç¶æ¯è¿ä¸ªåºçé¦è¦çä»·å¼ä½ç°åå­å¨çç±ã

ä½ä½ä¸ºä¸ä¸ª**å¼æº**é¡¹ç®ï¼æ¯ä¸ªäººé½å¯ä»¥çå°æºç å®ç°ï¼è¿ä¸ªåºæè®¸è½åå¾æ´å¤ã

### ð¯ é¢åå¼åèçç®æ 

- å°`Shell/Bash`ä½ä¸ºçº¿ä¸çäº§ç¯å¢ä½¿ç¨çä¸ä¸ç¼ç¨è¯­è¨ã
- ææä½ç°`Shell/Bash`èæ¬ çäº§ç¯å¢çº§çä¸¥è°¨å¼åæ¹å¼ä¸æä½³å®è·µï¼è¿èæå¯è½ç¤ºä¾ä¸æ¹åå¨çäº§ç¯å¢ä¸­`Shell`èæ¬çè´¨éç¶åµã

PSï¼

- è½ç¶ä¸é¢æ¯èªå·±ææçç®æ ï¼ä½èªå·±å¨`Shell`è¯­è¨ä¸ä¸å®ä¼æå¾å¤çè§£åä½¿ç¨ä¸çé®é¢ãå¨è¿äºå®ç°èæ¬ä¸­ä¹ä¼å¾å¤éè¦çæ¹è¿ï¼å¯ä»¥ä¸èµ·å­¦ä¹ ãè®¨è®ºä¸å®è·µï½ ð
- è¿ä¸ªåºä¸­èæ¬çå®ç°ä¹æä½¿ç¨`Python`ã

#### å³äº`Shell`èæ¬

å½ä»¤è¡ï¼`CLI`ï¼å ä¹æ¯æ¯ä¸ªç¨åºåæ¯å¤©é½å¨ä½¿ç¨çå·¥å·ãç¸æ¯å¾å½¢çé¢å·¥å·ï¼`GUI`ï¼ï¼å½ä»¤è¡æçèªå·±ä¸å¯æ¿ä»£çä¾¿å©æ§åä¼è¶æ§ã

å½ä»¤è¡éååºæ¥å¶å®å°±æ¯`Shell`èæ¬ï¼å¯ä»¥è¯´æ¯ä¸ªå¼åèä¼å`Shell`èæ¬ï¼æå¤æå°ï¼ãå¨çäº§ç¯å¢çåè½å®ç°ä¸­ï¼ä¹å¸¸ä¼çå°`Shell`èæ¬ï¼è½ç¶ä¸å¦ä¸»æµè¯­è¨é£ä¹å¸¸è§ï¼ã

å¯è½æ­£å ä¸ºä¸é¢æè¯´ç`Shell`èæ¬çä¾¿å©æ§åå¤§ä¼æ§ï¼

- `Shell`èæ¬æä¸å°æ¯é¡ºæå®ç°çï¼åæ¬çäº§ç¯å¢ç¨ç`Shell`èæ¬ï¼ï¼
- `Shell`èæ¬çå®ç°å¸¸å¸¸å¯è½è´¨éä¸é«ï¼ä¼å¼åçº¿ä¸ä¸¥éçæéã

### ð¦ å¼åçº¦å®

å¨è¿ä¸ªåºä¸­ç`Shell`èæ¬ï¼

- ç»ä¸ä½¿ç¨`Bash 3+`ï¼
- é¢åçäº§ç¯å¢ï¼å°½å¯è½ä½¿ç¨ä¸¥è°¨å®å¨çå¼åæ¹å¼ã

`Shell`ç¨`Bash`çåå æ¯ï¼

- ç®åä»ç¶æ¯ä¸»æµç`Shell`ï¼å¹¶ä¸å¨ä¸åç¯å¢åºæ¬ä¸é½ç¼ºçé¨ç½²äºã
- å¨[`Google`ç`Shell`é£æ ¼æå](https://zh-google-styleguide.readthedocs.io/en/latest/google-shell-styleguide/background/)ä¸­ï¼æç¡®è¯´æäºï¼`Bash`æ¯**å¯ä¸**è¢«åè®¸æ§è¡ç`shell`èæ¬è¯­è¨ã
    - æå¤§éç`Shell`å®ç°ï¼`sh`ã`bash`ã`zsh`ã`fish`ã`csh`ã`tcsh`ã`ksh`ã`ash`ã`dash`â¦â¦
    - ä¸åç`Shell`æåç§å·®å¼ï¼æ·±åå¿å¥ã
    - ç»ä¸ç¨`Bash`ï¼å¯ä»¥é¿åå·®å¼å¸¦æ¥çé£é©ä¸æ²¡ææ¶ççå¤ææ§ã
- ä¸ªäººç³»ç»å­¦ä¹ è¿çæ¯`Bash`ï¼æ¯è¾çè§£çæã

PS: è½ç¶äº¤äº`Shell`ä¸ªäººå·²ç»ä½¿ç¨`Zsh` + [`oh-my-zsh`](https://ohmyz.sh/)ï¼ä½å¨ä¸¥è°¨ç`Shell`èæ¬å¼åæ¶è¿æ¯ä½¿ç¨`Bash`ã

### ð `Shell`å­¦ä¹ ä¸å¼åçèµæ

> æ´å¤èµæåè§ [å­ææ¡£](docs/developer-guide.md)ã

- ð· **`Bash/Shell`æä½³å®è·µä¸å®å¨ç¼ç¨**
    - [**_`Google Shell Style Guide`_**](https://google.github.io/styleguide/shell.xml) | [ä¸­æç](https://zh-google-styleguide.readthedocs.io/en/latest/google-shell-styleguide/background/)
    - [`koalaman/shellcheck`](https://github.com/koalaman/shellcheck): ShellCheck, a static analysis tool for shell scripts
    - [Use the Unofficial Bash Strict Mode (Unless You Looove Debugging)](http://redsymbol.net/articles/unofficial-bash-strict-mode/)
    - Bash Pitfalls: ç¼ç¨æç¯çéè¯¯ - å¢å­çå°çªï¼[Part 1](http://kodango.com/bash-pitfalls-part-1) | [Part 2](http://kodango.com/bash-pitfalls-part-2) | [Part 3](http://kodango.com/bash-pitfalls-part-3) | [Part 4](http://kodango.com/bash-pitfalls-part-4)
    - [ä¸è¦èªå·±å»æå®shçæ¹å¼å»æ§è¡èæ¬](https://github.com/oldratlee/useful-scripts/issues/57#issuecomment-326485965)
- ð¶ **Tips**
    - [è®©ä½ æåå½ä»¤è¡æçç Bash å¿«æ·é® ãå®æ´çã](https://linuxtoy.org/archives/bash-shortcuts.html)  
        è¡¥åï¼`ctrl + x, ctrl + e` å°±å°æå¼ææ¬ç¼è¾å¨æ¥ç¼è¾å½åå½ä»¤è¡ï¼å¯¹äºå¤æå½ä»¤è¡ç¹å«æç¨
    - [åºè¯¥ç¥éçLinuxæå·§ | é· å£³ - CoolShell](https://coolshell.cn/articles/8883.html)
    - ç®æ´ç Bash Programming æå·§ - å¢å­çå°çªï¼[Part 1](http://kodango.com/simple-bash-programming-skills) | [Part 2](http://kodango.com/simple-bash-programming-skills-2) | [Part 3](http://kodango.com/simple-bash-programming-skills-3)
- ð **ç³»ç»å­¦ä¹ **  
    çæç« ãäºè§£Tipså®å¨ä¸è½æ¿ä»£ç³»ç»å­¦ä¹ æè½çæ­£çè§£å¹¶ä¸ä¸å¼åï¼
    - [ãBash Pocket Referenceã](https://book.douban.com/subject/26738258/)  
        åèï¼è¯´æç®åç´æ¥ç»æä½ç³»çä½³ä½ï¼ä¸ä¸`Bash`ç¼ç¨å¿å¤ï¼ä¸16å¹´çç¬¬äºçæ´æ°å°äºæ°çç`Bash 4`
    - [ãå­¦ä¹ bashã](https://book.douban.com/subject/1241361/) ä¸é¢é£æ¬çå±å¼ç
    - å®æ¹èµæ
        - [`bash man`](https://linux.die.net/man/1/bash) | [ä¸­æç](http://ahei.info/chinese-bash-man.htm)
        - [Bash Reference Manual - gnu.org](http://www.gnu.org/software/bash/manual/) | [ä¸­æç](https://yiyibooks.cn/Phiix/bash_reference_manual/bash%E5%8F%82%E8%80%83%E6%96%87%E6%A1%A3.html)  
        Bashåèæåï¼è®²å¾å¨é¢ä¸ææ·±åº¦ï¼æ¯å¦ä¼å¨é¢å°è®²è§£ä¸åè½¬ä¹çåºå«ãå½ä»¤çè§£æè¿ç¨ï¼è¿æå©ç»ä¸æ·±å¥çæ¹å¼è®¤è¯Bashæ´ä¸ªæ§è¡æ¹å¼åè¿ç¨ãè¿äºåå®¹å¨å¶å®ä¹¦ä¸­å¾å¾ä¸ä¼è®²ï¼å ä¸ºå¤æé¾äºæ·±å¥æµåºçè®²è§£ï¼ï¼ä½å´ä¸éç¾éçå³é®ã
    - [å½ä»¤è¡çèºæ¯ - `jlevy/the-art-of-command-line`](https://github.com/jlevy/the-art-of-command-line/blob/master/README-zh.md)
    - [`alebcay/awesome-shell`](https://github.com/alebcay/awesome-shell): A curated list of awesome command-line frameworks, toolkits, guides and gizmos.
    - æ´å¤ä¹¦ç±åè§ä¸ªäººæ´çç[ä¹¦ç±è±å **_`Bash/Shell`_**](https://www.douban.com/doulist/1779379/)
