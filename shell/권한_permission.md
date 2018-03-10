# 권한 문제(Permission Problem)

가끔 리눅스를 쓰다보면 실행할 수 있는 권한이 없다면서 실행이 안되는 경우가 있는데, 이럴때 사용할 수 있는 명령어가 바로 _chmod_다.  
실행방법은 다음과 같다.  

```
prompt> chmod -x [absolutePath|relativePath]
prompt> [absolutePath|relativePath]
```

* chmod 명령어가 안먹히면 sudo를 쓰거나 sudo su로 루트권한을 얻은 다음 시도하면 될 것이다. 
* 자세한 사항은 [askubuntu - how do i run sh files](https://askubuntu.com/questions/38661/how-do-i-run-sh-files)을 참고하라.
