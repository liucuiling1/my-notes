#### php和nginx启动（项目配置）

一、php启动：  
> brew services restart php71

二、nginx启动：  
> sudo nginx -s reload
> sudo chmod -R 777 vendor/storage/   
(vendor/storage/要解压)

三、项目配置环境：
1、cd /usr/local/etc/nginx/servers/      
2、vim blog (新建/打开文件夹名)  
   删除文件夹命令 ： rm blog(文件夹名)
3、复制下面的内容到新建的文件夹blog(文件夹名)
```
server {
  listen           80;
  server_name  frogmp.com; 
  root          /Users/limin/frogmp/public;
  location / {
    try_files $uri $uri/ /index.php?$query_string;
    index  index.php;
    include      /usr/local/etc/nginx/conf.d/php-fpm;
  }
}
```
```
注意：其中root中的路经，可以通过 cd blog/public/ —> pwd 命令查找出来
     a/A切换编辑模式  ESC退出编辑模式，shift+ :wq (保存退出) ,enter回车
```

4、cd退出 sudo vim /etc/hosts   
   添加 127.0.0.1  wechat.fg.com （访问网址名）    
   a/A切换编辑模式  ESC退出编辑模式，shift+ :wq ,(保存退出)

5、nginx服务器重起：sudo nginx -s reload

添加权限 ：chmod -R 777 vendor/ storage/ bootstrap/

![avatar](/images/php&nginx.png)




