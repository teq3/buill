ð `VCS`ç¸å³èæ¬
====================================

> ä½ ä¼åç°è¿äºèæ¬é½æ¯`svn`åæ¯ç¸å³çæä½ã
>
> ä¸ªäººå¨ä½¿ç¨`Git`çè¿ç¨ä¸­ï¼7å¹´+ï¼ï¼å¹¶æ²¡æåç°æå¯¹åºèæ¬çéæ±ï¼ä¾§é¢åæ åº`Git`çä¼ç§ï¼ã  
> åå ï¼`Git`çæ¦å¿µæ¨¡åä¸ç­å¬æ°æ¯æåæ¯ï¼åæ¢åæ¯æ¯ä»¶å¾ç®åä¸ç»ä¸çäºï¼è`svn`ä¸å¾ä¸æ¶åä»åºç`URL`ï¼ä¸ç»ä¸ç®åï¼ã
>
> æå·²ç»å¨èªå·±çå¼åæºä¸å¸è½½äº`svn`ï¼æ²¡æéæ±åºæ¯ä¹æ²¡çç±åç¨äºã ð
>
> ä½¿ç¨æ´ç°ä»£ç`Git`å§ï¼ ð¥

1. [swtrunk](#-swtrunk)  
    èªå¨`svn`å·¥ä½ç®å½ä»åæ¯ï¼`branches`ï¼åæ¢å°ä¸»å¹²ï¼`trunk`ï¼ã  
    PSï¼ `Git`å¯¹åºçæ¯`git checkout master`ï¼å¦æä½ ä½¿ç¨äº`oh-my-zsh`ï¼å·²ç»æå¯¹åºçå«åå éäºï¼`gcm`ã
1. [svn-merge-stop-on-copy](#-svn-merge-stop-on-copy)  
    ææå®çè¿ç¨åæ¯ä»åæ°å»ºåæ¯ä»¥æ¥çä¿®æ¹åå¹¶å°æ¬å°`svn`ç®å½ææ¯å¦ä¸ä¸ªè¿ç¨åæ¯ã  
    PSï¼`Git`çåå¹¶å¾ç´æ¥ç®åï¼`git merge branch-foo`ï¼ä¹æ´æºè½ï¼æ²¡ææ å²çªä¸è¯´ï¼ã
1. [cp-svn-url](#-cp-svn-url)  
    æ·è´å½å`svn`ç®å½å¯¹åºçè¿ç¨åæ¯å°ç³»ç»çç²è´´æ¿ï¼çå»`CTRL+C`æä½ã  
    PSï¼`Git`åæ¯ä¸éè¦`URL`æ¥å¼ç¨ï¼æ²¡æè¿ä¸ªèæ¬çéæ±ï¼ç´æ¥ç»ä¸ªåæ¯åå°±å¥½äºã

ðº [swtrunk](../legacy-bin/swtrunk)
----------------------

`svn`å·¥ä½ç®å½ä»åæ¯ï¼`branches`ï¼åæ¢å°ä¸»å¹²ï¼`trunk`ï¼ã  
æ¯æ`Linux`ã`Mac`ã`Windows`ï¼`cygwin`ã`MSSYS`ï¼ã

å½ä»¤ä»¥`svn`çæ åç®å½å½åçº¦å®æ¥è¯å«åæ¯åä¸»å¹²ã
å³ï¼åæ¯å¨ç®å½`branches`ä¸ï¼ä¸»å¹²å¨ç®å½`trunk`ä¸ã
ç¤ºä¾ï¼

- åæ¯ï¼ <http://www.foo.com/project1/branches/feature1>
- ä¸»å¹²ï¼ <http://www.foo.com/project1/trunk>

### ç¨æ³

```bash
swtrunk # ç¼ºçä½¿ç¨å½åç®å½ä½ä¸ºsvnå·¥ä½ç®å½
swtrunk path/to/svn/work/directory
swtrunk path/to/svn/work/directory1 /path/to/svn/work/directory2 # svnå·¥ä½ç®å½ä¸ªæ°ä¸éå¶
```

### ç¤ºä¾

```bash
$ swtrunk
# <svn sw output...>
svn work dir . switch from https://www.foo.com/project1/branches/feature1 to https://www.foo.com/project1/trunk !

$ swtrunk /path/to/svn/work/dir
# <svn sw output...>
svn work dir /path/to/svn/work/dir switch from https://www.foo.com/project1/branches/feature1 to https://www.foo.com/project1/trunk !

$ swtrunk /path/to/svn/work/dir1 /path/to/svn/work/dir2
# <svn sw output...>
svn work dir /path/to/svn/work/dir1 switch from https://www.foo.com/project1/branches/feature1 to https://www.foo.com/project1/trunk !
# <svn sw output...>
svn work dir /path/to/svn/work/dir2 switch from https://www.foo.com/project2/branches/feature1 to https://www.foo.com/project2/trunk !
```

ðº [svn-merge-stop-on-copy](../legacy-bin/svn-merge-stop-on-copy)
----------------------

ææå®çè¿ç¨åæ¯ä»åæ°å»ºåæ¯ä»¥æ¥çä¿®æ¹åå¹¶å°æ¬å°`svn`ç®å½ææ¯å¦ä¸ä¸ªè¿ç¨åæ¯ã  
æ¯æ`Linux`ã`Mac`ã`Windows`ï¼`cygwin`ã`MSSYS`ï¼ã

### ç¨æ³

```bash
svn-merge-stop-on-copy <æ¥æºçè¿ç¨åæ¯> # åå¹¶å½åæ¬å°svnç®å½
svn-merge-stop-on-copy <æ¥æºçè¿ç¨åæ¯> <ç®æ æ¬å°svnç®å½>
svn-merge-stop-on-copy <æ¥æºçè¿ç¨åæ¯> <ç®æ è¿ç¨åæ¯>
```

### ç¤ºä¾

```bash
svn-merge-stop-on-copy https://www.foo.com/project1/branches/feature1 # ç¼ºçä½¿ç¨å½åç®å½ä½ä¸ºsvnå·¥ä½ç®å½
svn-merge-stop-on-copy https://www.foo.com/project1/branches/feature1 /path/to/svn/work/directory
svn-merge-stop-on-copy https://www.foo.com/project1/branches/feature1 https://www.foo.com/project1/branches/feature2
```

### è´¡ç®è

[å§å¤ªå¬](https://github.com/jzwlqx)æä¾æ­¤èæ¬ã

ðº [cp-svn-url](../legacy-bin/cp-svn-url)
----------------------

æ·è´å½å`svn`ç®å½å¯¹åºçè¿ç¨åæ¯å°ç³»ç»çç²è´´æ¿ï¼çå»`CTRL+C`æä½ã  
æ¯æ`Linux`ã`Mac`ã`Windows`ï¼`cygwin`ã`MSSYS`ï¼ã

### ç¨æ³

```bash
cp-svn-url # ç¼ºçä½¿ç¨å½åç®å½ä½ä¸ºsvnå·¥ä½ç®å½
cp-svn-url /path/to/svn/work/directory
```

### ç¤ºä¾

```bash
$ cp-svn-url
https://www.foo.com/project1/branches/feature1 copied!
```

### è´¡ç®è

[ivanzhangwb](https://github.com/ivanzhangwb)æä¾æ­¤èæ¬ã

### åèèµæ

[æ·è´å¤å¶å½ä»¤è¡è¾åºæ¾å¨ç³»ç»åªè´´æ¿ä¸](http://oldratlee.github.io/post/2012-12-23/command-output-to-clip)ï¼ç»åºäºä¸åç³»ç»å¯ç¨å½ä»¤ã
