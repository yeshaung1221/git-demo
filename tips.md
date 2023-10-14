## 将本地仓库推送到远程仓库（github）
    1：在命令行里面新建一个空的仓库推送到远程仓库
    2：从命令行里面推送一个已经存在的仓库到远程仓库中
    3：从其他仓库导入
## 我们现在用第二种推送
1：git push 远程仓库地址 分支名称（可能会有网络的问题--但是我现在变成了两个分支？？？）
    git remote add origin https://github.com/yeshaung1221/git-demo.git
这个指令的意思代表我们把远程仓库起了一个别名叫origin  


2：在第二次推送的时候我们发现不需要输入密码了，是系统里面储存了密码 
控制面板--凭据管理器--windows凭据-点击可以删除或者编辑

## git push -u远程仓库地址别名 分支名称 -u是记住推送的地址及分支，下次推送只需要输入git push即可
3在提交的时候输入 git push -u origin master
    那么在下一次输入的时候直接git push 就能提交到远程仓库

## 小tips  ：如何处理git连接不了的问题unable to access 'https://github.com/yeshaung1221/git-demo.git/': Failedto connect to github.com port 443 after 28351 ms: Couldn't connect to server

    （1）出现这种问题的原因1：DNS 解析出现问题
        解决方法：在 cmd 窗口输入 ipconfig/flushdns ，清除缓存后再重新进行 git 操作即可
    （2）出现问题的原因2：防火墙或代理设置
    
    查询：通过git配置文件查看是否使用代理：git config --global http.proxy
    通过查询系统环境有没有使用代理：env|grep -I proxy
        解决方法：取消代理
        git config --global --unset http.proxy
 
        git config --global --unset https.proxy
（提交的时候不要开梯子）
    （3）也可能是之前用过代理，清除之前的代理即可
    git config --global --unset http.proxy


## 我们克隆下载的源码做了修改之后是没有资格提交到远程仓库的，是可以暂存在本体仓库中（因为提交远程没有权限）
    解决：
    1：程序员a 要请程序员b来进行提交
    2：在程序员a的github界面有一个setting
    3：setting里面有一个collabortors合作者
    4：add people发出邀请之后
    程序员b在自己的github账号上面接收邀请
    5：在程序员b推送的时候记得把账号密码在控制面板里面的给删除，这样的话提交就会用b的账号提交而不是a的

# （github上面的默认分支是main  ）


## 现在程序员b把最新版本推送到远程后，程序员a组要拉取最新版本
    ：拉取命令
        1：git pull 远程仓库地址 分支命令
