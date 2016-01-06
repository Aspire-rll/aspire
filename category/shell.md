shell.md
##### shell命令的使用
* cat命令的用法：http://www.itbulu.com/linux-cat-detail.html
* /dev/null ：http://blog.csdn.net/kaiwii/article/details/7308729
* history -c :清除当前用户的输入
* 所以一个保证绝对清除当前shell命令行历史记录的命令

    cat /dev/null > ~/.bash_history && history -c && exit
