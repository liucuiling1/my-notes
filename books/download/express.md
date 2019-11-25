#### express框架

(1) node环境下
> npm install -g express-generator    
> express -e project   （project文件夹名）

(2) 进入项目文件根目录安装依赖模块
> npm install
> DEBUG=node-blog:* npm start

```
app.js：启动文件，或者说入口文件
package.json：存储着工程的信息及模块依赖，
node_modules：存放 package.json 中安装的模块，当你在 package.json 添加依赖的模块并安装后，存放在这个文件夹下
public：存放 image、css、js 等文件
routes：存放路由文件
views：存放视图文件或者说模版文件
bin：存放可执行文件
```

(3) 路由规则    
express 封装了多种 http 请求方式，我们主要只使用 get 和  post 两种，即  app.get() 和 app.post() 。    
app.get() 和  app.post() 的第一个参数都为请求的路径，第二个参数为处理请求的回调函数，回调函数有两个参数分别是 req 和 res，代表请求信息和响应信息 。路径请求及对应的获取路径有以下几种形式：
* req.query ： 处理 get 请求，获取 get 请求参数
* req.params ： 处理 /:xxx 形式的 get 或 post 请求，获取请求参数
* req.body ： 处理 post 请求，获取 post 请求体
* req.param() ： 处理 get 和 post 请求，但查找优先级由高到低为 req.params→req.body→req.query

(4) 运行express   
> node ./bin/www


 