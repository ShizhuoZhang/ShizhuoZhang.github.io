
# <center>搭建个人博客教程<center>  
&emsp;&emsp; 本来只想用Github Pages做一个在线简历，做着做着就想做成个人博客来记录生活和学习。但由于不懂Java、HTML或CSS等方面的知识，所以就直接使用现有的Jekyll模板。
&emsp;&emsp; 该项目代码Fork自[原作者的工程](https://github.com/byeluliangwei/byeluliangwei.github.io)。__ 
__简单修改后的博客地址：__ https://shizhuozhang.github.io。

## 个性化修改步骤
&emsp;&emsp; 因为对功能的需求不高，所以总体上并没有修改太多内容。  

- Fork原作者的工程到自己的Github账户下，删除`__posts`目录和`images`目录下的绝大部分内容，简单修改了一下`__config`文件中的个人信息。

- 进入工程所在的`setting`中，Rename仓库名（与自己的Account name一致），然后，在`Github Pages`中找到自己的博客主页，点击可进行测试。

- 进一步的细节修改：替换图片（图片存放在`images`目录），修改`_include`目录下的footer文件中的部分链接。

- 最后就是发布文章，将自己的工程clone到本地，将你自己编写好的文章放到`__posts`目录下，再push到github后。

- 如果想要进一步修改模板内容，可以配置ruby环境，安装bundler、jekyll等工具，可以离线预览网页的具体内容，便于前期个性化修改。虽然该部分网上教程不少，例如[This](https://www.cnblogs.com/zjjDaily/p/8695978.html) ，但我操作时并不顺利，遇到的一个最大的问题是jekyll各种gems的版本和依赖关系不匹配，最后通过在Gemfile中规定版本号解决。

- 工程中还有“评论”，“浏览量”，“打赏”等功能，可以玩一玩。
## 致谢

感谢作者[byeluliangwei] (https://byeluliangwei.github.io) 和[dawn1432](https://dawn1432.github.io) 。
