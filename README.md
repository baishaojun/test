first git

我会使用git了

解决:第一次git push -u origin master 失败
To git@github.com:yangchao0718/cocos2d.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'git@github.com:yangchao0718/cocos2d.git
hint: Updates were rejected because the tip of your current branch is behin
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

第一步,先git pull --rebase origin master

第二步,git push -u origin master

问题就解决了



问题二:
git push -u origin master 出现The authenticity of host 'github.com ' can't be established解决方案
原创 2016年11月02日 10:26:25

git push -u origin master提交代码到github时

报错：

The authenticity of host 'github.com (192.30.253.112)' can't be established.RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.Are you sure you want to continue connecting (yes/no)? yesWarning: Permanently added 'github.com,192.30.253.112' (RSA) to the list of known hosts.Permission denied (publickey).fatal: Could not read from remote repository.Please make sure you have the correct access rightsand the repository exists.


原因：1.github上没有与本地仓库相关联（重新remot）

             2.ssh不对（多数情况）


ssh解决：

1.  cat ~/.ssh/id_rsa.pub 查看ssh是否是自己的，不是说明是ssh问题，是的就是远程关联问题

2. 如果是ssh问题则在git仓库同目录 删除.ssh文件夹 （隐藏文件夹）

判断删除成功： cat ~/.ssh/id_rsa.pub
出现cat: /c/Users/ZhangLin/.ssh/id_rsa.pub: No such file or directory


3.重新创建ssh  ssh-keygen -t rsa -C "your_email@example.com“

一路回车


4.在ssh文件夹下pub文件中的内容复制  github上新建一个ssh链接




