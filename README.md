# learnGit
who? benleie?

## 使用多个账号
+ remote: Permission to UserA/life.git denied to UserB
+ 比如说电脑上有两个git账号，初始化一个项目，提示可能是这样：`git remote add origin https://github.com/awecg/life.git`,这样的远程仓库提交时可能会出现'remote: Permission to UserA/life.git denied to UserB'的问题。
那么最好在ssh中配置一下，然后将新仓库地址修改一下，`git remote set-url origin git@github-awecg:awecg/life.git`,这样ssh就能识别不同的git账号，从而完成提交
  + 配置方式 在Git的项目中，/etc/ssh/ssh_config,添加如下配置(SSH Keys需要自己去生成，并添加到github账号配置中)
  +  ```
      Host github-awecg
        HostName github.com
        PreferredAuthentications publickey
        IdentityFile  /d/englishversion/ssh-id/id_rsa_awecg
        User git
     ```