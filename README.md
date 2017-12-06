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