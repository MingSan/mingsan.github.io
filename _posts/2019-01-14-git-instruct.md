```
 git tag    //查看tag
 git tag test_tag c809ddbf83939a89659e51dc2a5fe183af384233  //在某个commit 上打tag
 git push origin test_tag   //!!!本地tag推送到线上
 git tag -d test_tag    //本地删除tag
 git push origin :refs/tags/test_tag    //本地tag删除了，再执行该句，删除线上tag
```