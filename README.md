# my_blog
个人博客雏形

这是我依照learning_log的模版自己新建的一个个人博客，当然现在还是非常稚嫩的样子，下面主要记录一下在开发这个网站的过程
中遇到的一些问题和解决办法。

1.部署问题
  这真的是个蛮棘手的问题，因为在整个开发过程中我几乎都是按照书上的步骤做的，而且已经在本地完全做好了调试没有问题。
  但是非常遗憾的是在部署应用的时候还是出现了问题。
  a.还是和learning_log一样报错了 remote: $ heroku config:set DISABLE_COLLECTSTATIC=1 
  解决办法 在终端里输入 heroku config:set DISABLE_COLLECTSTATIC=0
  
  b.应用推送到heroku后，报错应用错误，通过 查看日志（heroku logs --tail），发现报错内容是 H14 
  解决方法：根据官网内教程 使用代码heroku ps:scale web=1 虽然每次执行后都报错 Couldn't find that process type.
  但是再次推送后就发现部署成功了，目前总的来说解决途径不能完全确定。
  
  ps：通过这个部署过程发现 静态部署文件全部写在if内或者部分顶格都是没有问题的，python版本只要是支持的对于部署和应用进程来说都是没有太大影响的，
  只是说heroku官网内列出的完全支持版本的支持效果更好，支持的东西更多。
