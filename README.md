## 什么是SBDoc？
#### SBDoc是一个商业化开源产品，完全免费。无论你是前端工程师，还是后端工程师，接口永远都是两者交互的桥梁，所以SBDoc专为中小型团队量身打造，旨在解决接口的管理，测试与数据生成，实现真正的一体化解决方案。
## SBDoc有哪些功能
#### 1.团队协作，可以对不同的成员分配权限，有两种权限，管理员：可以增删改查项目和接口信息。观察者：可以查看，测试，mock接口数据，但是不能修改接口和项目的信息。
#### 2.编写接口文档，摒弃了传统的纯文本编写方式，采用可视化编写，随意拖拽，可以添加任意层次信息，并且实时预览文档编写结果。
#### 3.对接口进行测试，对于外网测试，没有跨域，后台采用的是proxy代理，对于内网，需要在本地安装node环境，然后下载系统内提示的net.js文档，在本地用node运行即可。net.js就是一个http，https的透明代理。
#### 4.自动生成接口，很多时候，我们的后端开发人员都是先将接口开发好，再去写接口文档的，或者是接口有比较大的改动，接口文档也要改动很多。对于这种情况，可以在测试接口后对接口的文档信息进行一键自动生成，接口的所有入参，出参，http头都会自动生成到文档，我们要做的就是简单的修修改改就可以啦
#### 5.对数据进行无缝mock，在大部分情况下，前端的开发人员都是要等待后端的开发者将接口开发调试好才能进行下一步开发，这样会耗费大量的时间精力，如果要本地生成数据那么成本也会比较高，所以SBDoc有独特的无缝mock技术，只需要在本地用node运行net.js ,加上mock server地址（每个项目都会自动生成自己的mock Server地址）和你需要请求的真实地址，当您的接口文档的状态为开发完成的时候，net.js不会去请求mock server地址而去请求真实地址（举例：node net.js http://sbdoc.cn:10000/mock/586b17545fa2d311c0915021 http://localhost:8081) ,然后将您开发工程下的根url替换为localhost:36742即可开启您的Mock之旅！
## 产品文档
#### http://sbdoc.cn
## SBDoc开源
#### 本次开源的是SBDoc的内网版本，可以直接部署到内网中，和线上版本在功能上是完全一样的，区别在于：
#### 1.线上的系统用了前端和后端两套工程，并且用nginx做了负载均衡，redis做缓存，而内网版本合并为一个工程，直接用node做静态服务器，取消了缓存，这样对于很多中小型团队来说很轻便而且也够用了。
#### 2.线上系统在安全性方面做了不少加固处理，而内网版本默认内网是安全的，也为了提高node作为服务器的效率，取消了很多加固处理，如果用户有需要可以自行添加。
## 如何部署
#### 1.首先本地要安装node环境，推荐6.10.0版本([下载页面](https://nodejs.org/en/))
#### 2.安装mongodb([下载页面](https://www.mongodb.com/))，可使用robomongo来作为mongodb的客户端工具([下载页面](https://robomongo.org/))，启动mongodb后（[如何启动](http://www.open-open.com/lib/view/open1435117403544.html)），用robomongo来连接，新建一个database作为SBDoc的数据库（名称随意）
#### 3.将SBDoc的源码down到本地，进入根目录，修改config.json 
{  
  "db":"mongodb://localhost:27017/SBDoc",  //这里为你的mongodb服务器的地址和库的名称  
  "filePath":"/Users/Shared/SBDoc",  //这里作为SBDoc文件上传的路径  
  "imgPath":"/Users/Shared/SBDoc/img",  //这里是SBDoc图片上传的路径  
  "tempPath":"/Users/Shared/SBDoc/temp",  //这里SBDoc临时文件上传的路径  
  "port":10000,  //SBDoc启动的端口号  
  "version":"1.0.0"  //SBDoc的版本号（无需修改）  
}  
#### 4.在命令行下运行node SBDoc的根目录/SBDoc/bin/www即可启动SBDoc（如果是windows环境下，请修改目录分隔符)，在浏览器里输入localhost:SBDoc启动的端口号,出现首页表示部署成功。
## 问题反馈
#### 如果你有任何问题和建议，请在issues里面指出，每个月的1号和15号会发布功能迭代版本，根据bug情况不定期的会发布bug迭代版本。如果你想加入开源的大家庭，欢迎加入qq群：611940610
## 注意
#### 本系统已申请专利著作权，请不要私自用于商业用途，如有发现，我们将保留对你的法律责任追究！
