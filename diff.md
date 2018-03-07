#git reset 三个参数的区别

修改readme.md，分别提交
git status 显示：
![当前状态](http://upload-images.jianshu.io/upload_images/3105729-9096ac806325cda5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

git log 查看记录：

![记录](http://upload-images.jianshu.io/upload_images/3105729-a11b176082d042c6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


 1.--mixed 和 --soft 的区别为状态修改
    当我们使用**git reset --soft HEAD~1** 后，README.md的内容并没有发生变化，但是HEAD的指向了**first**，说明在执行soft后，只是撤销了一次commit，回到了*staged*状态，这时**git commit** ，修改会重新被提交
    
![内容未发生变化](http://upload-images.jianshu.io/upload_images/3105729-712c7d5a8830f71f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![当前状态](http://upload-images.jianshu.io/upload_images/3105729-196268554217f209.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![git log 记录](http://upload-images.jianshu.io/upload_images/3105729-8ca624128d1028b3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

2.当我们使用**git reset HEAD~1**后，README.md的内容也没有发生变化，HEAD指向了**first**，但是这时候我们需要**git commit -a**才能将修改重新提交，说明在执行git reset HEAD~1后，回到了*未暂存*的状态

![当前状态](http://upload-images.jianshu.io/upload_images/3105729-68289f11a28cdb4a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3.在使用**git reset --hard HEAD~1**后，HEAD指向了**first** ，README.md的内容发生变化，说明在执行**git reset --hard HEAD~1**后，*工作区被重置*。

![文档内容发生变化](http://upload-images.jianshu.io/upload_images/3105729-93ce281062b7ef87.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![工作区clean](http://upload-images.jianshu.io/upload_images/3105729-7d1c337a9b07687d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

