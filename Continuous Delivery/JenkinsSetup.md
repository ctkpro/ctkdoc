## AWS setting
- aaa
```
$ sudo -su jenkins

//check jenkins-role iam accesskey and secretid
$ curl http://169.254.169.254/latest/meta-data/iam/security-credentials/jenkins-role
```

## Udemy的筆記
- 要設定Poll SCM，每段時間polling，有變化才build
![Jenkins-Poll-SCM](https://cloud.githubusercontent.com/assets/6972644/11199518/2c2b5756-8d09-11e5-8049-d4ae67f2c886.png)  
- **todo** find js related (maven, checkstyle, pmd, findbugs, junit)
- 