#### react搭建运行环境的流程
1、安装node（安装node时会自带一个npm的包管理工具）

2、查看版本
> node -v 和 npm -v

3、淘宝镜像
> 安装npm源：npm install -g cnpm --registry=https://registry.npm.taobao.org;

> 更换npm源：npm config set registry https://registry.npm.taobao.org       

> 查看npm源：npm config get registry 

4、安装
> npm install create-react-app -g   (-g全局安装)

5、create-react-app demo  (demo创建的项目名称)

6、cd demo (进入项目)

7、npm start (启动项目)

```
注：如果是下载淘宝镜像，在下载依赖包时用：cnpm install
```