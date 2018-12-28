# routine-command  
存放常用linux命令  

查看当前登录用户：w  
查看显卡使用情况：nvidia-smi  
指定显卡：CUDA_VISIBLE_DEVICES=0    python  your_file.py  
挂起进程：nohup /root/start.sh > output.txt &  

# basic operation  
查看隐藏文件：ls -la  
创建文件：touch file
修改文件：echo "test" >> file
查看文件夹大小：du -h 路径

# matlab command  
set(gcf,'position',[200,200,500,400]); 一张图片最佳宽为500，高为400


# git command  
Git初始化：
$ git config --global user.name "Scott Chacon"
$ git config --global user.email "schacon@gmail.com"
初始化新仓库  
mkdir project  
cd project  
git init  
查看git仓库状态  
git status  
把文件加入缓存区  
git add file  
使用git commit 提交修改, 文件会被提交到本地仓库  
git commit -m "add file"--> -m添加comment
