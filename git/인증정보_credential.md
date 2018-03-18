## credential

git을 쓰다보면 꽤 자주 아이디와 비밀번호를 요구한다. 이런 상황을 벗어나기 위해서는 어떻게 해야할까?

## 2018/03/19

```
fatal: unable to get credential storage lock: File exists
```

이 때는 이렇게 해보자.

```
git config credential.helper wincred
```

* 출처: https://stackoverflow.com/questions/37505843/fatal-unable-to-get-credential-storage-lock-file-exists
