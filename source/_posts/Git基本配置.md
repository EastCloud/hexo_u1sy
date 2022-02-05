---
title: Git基本配置
date: 2022-02-04 14:46:00
categories: 网站
cate_eng: web
urlname: git-basic-configuration
tags:
---

<article class="_2rhmJa"><h2>1、配置git：</h2><p><b>（1&nbsp;）设置用户名称和登录邮箱</b></p><blockquote>
<p>git config --global user.name '用户名称'</p>
<p>git config --global user.email '登录邮箱'</p>
</blockquote><p><b>（2）生成密钥</b></p><blockquote><p>ssh-keygen -t rsa -C '登录邮箱'</p></blockquote><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;***上述代码执行完成后，会连续多次要求输入密码。注意：此时请不要输入密码。</p><p><b>（3）配置</b></p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;打开.ssh文件夹下的id-rsa.pub文件的内容，全部复制。然后登录你的git服务器个人账户设置中，寻找ssh key菜单项，然后粘贴即可。如下图所示：</p><div class="image-package">
<div class="image-container" style="max-width: 700px; max-height: 418px; background-color: transparent;">
<div class="image-container-fill" style="padding-bottom: 42.089999999999996%;"></div>
<div class="image-view" data-width="993" data-height="418"><img data-original-src="//upload-images.jianshu.io/upload_images/9989643-3affb5dc8224df16.png" data-original-width="993" data-original-height="418" data-original-format="" data-original-filesize="43174" data-image-index="0" style="cursor: zoom-in;" class="" src="//upload-images.jianshu.io/upload_images/9989643-3affb5dc8224df16.png?imageMogr2/auto-orient/strip|imageView2/2/w/993/format/webp"></div>
</div>
<div class="image-caption">配置SSH Key</div>
</div><h2>2、创建新项目/托管本地项目/克隆已有项目：</h2><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;当完成第1步的git配置后，就该去摆弄项目了。然而这时候又出现了3种状况需要被别考虑，他们分别是：</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>（1）没有本地项目和远端项目。</b></p><p>&nbsp; &nbsp; &nbsp; &nbsp; 这个就简单了，不用考虑，当然是创建新项目了，去执行第3步先行创建一个远程仓库吧；</p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>（2）已有本地项目但尚未托管到git服务器。</b></p><p>&nbsp; &nbsp; &nbsp; &nbsp; 当然了，这种情况肯定是要先创建远程仓库的。所以就放心大胆的去执行第3步创建远端仓库吧；</p><p>&nbsp; &nbsp; &nbsp; &nbsp;<b>（3）我们在git上已经有了项目或者我们希望参与别人的项目。</b></p><p>&nbsp; &nbsp; &nbsp; &nbsp; 这个时候，我们改如何操作呢？还是不要犹豫了，赶快去执行第4步吧。</p><h2>3、创建远端仓库（如果你已有远程仓库，请忽略这一步的所有操作，这一步和你没关系）</h2><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;登录你的git账户，点击上方导航栏的‘+’按钮，选择&nbsp;New repository，若下图所示：</p><div class="image-package">
<div class="image-container" style="max-width: 700px; max-height: 562px;">
<div class="image-container-fill" style="padding-bottom: 53.06999999999999%;"></div>
<div class="image-view" data-width="1059" data-height="562"><img data-original-src="//upload-images.jianshu.io/upload_images/9989643-1a70e50500487efd.png" data-original-width="1059" data-original-height="562" data-original-format="" data-original-filesize="57984" data-image-index="1" style="cursor: zoom-in;" class="image-loading"></div>
</div>
<div class="image-caption">准备创建repo</div>
</div><p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;然后，你会看到一下界面，按照项目要求填写即可。</p><div class="image-package">
<div class="image-container" style="max-width: 700px; max-height: 601px;">
<div class="image-container-fill" style="padding-bottom: 68.30000000000001%;"></div>
<div class="image-view" data-width="880" data-height="601"><img data-original-src="//upload-images.jianshu.io/upload_images/9989643-38cf64b03df91fb4.png" data-original-width="880" data-original-height="601" data-original-format="" data-original-filesize="43885" data-image-index="2" style="cursor: zoom-in;" class="image-loading"></div>
</div>
<div class="image-caption">创建repo</div>
</div><p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;最后点击create repository按钮后，你会看到一下界面，说明远程仓库创建成功：</p><div class="image-package">
<div class="image-container" style="max-width: 700px; max-height: 697px;">
<div class="image-container-fill" style="padding-bottom: 66.63%;"></div>
<div class="image-view" data-width="1046" data-height="697"><img data-original-src="//upload-images.jianshu.io/upload_images/9989643-32e3d2a3f1f51892.png" data-original-width="1046" data-original-height="697" data-original-format="" data-original-filesize="76812" data-image-index="3" style="cursor: zoom-in;" class="image-loading"></div>
</div>
<div class="image-caption">Repo创建成功共</div>
</div><p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;然后记录下你所创建的远端仓库的项目的ssh地址和https地址。</p><h2>4、克隆项目/初始化本地项目</h2><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;经过第2步和第3步的操作，我们在git服务器上有了一个现成的项目，这个时候情况又是2分状态，分别是：</p><p>&nbsp; &nbsp; &nbsp; &nbsp;<b>（1）没有本地项目。</b></p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;嗯，这种情况最简单，我们只需要将git远端仓库上的代码克隆到本地就可以了（克隆完成后，本地仓库已经同远端仓库保持一致状态了），因此应该执行第6步；</p><p>&nbsp; &nbsp; &nbsp; &nbsp;<b>（2）已有本地项目。</b></p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;这种状况下，我们首先需要初始化本地项目，最终使得本地项目与远端仓库的项目保持同步关联状态。执行第5步是无可非议的。</p><h2>5、初始化本地项目&amp;&amp;添加项目</h2><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>（1&nbsp;）初始化本地项目</b></p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;这一步是在git客户端或者CMD命令行上执行，我们通过命令行进入本地项目目录下，然后再执行下面的命令：</p><blockquote><p>git init</p></blockquote><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;执行完成以后你会发现在git文件夹内会生成一个名称为.git的隐藏文件，说明git初始化成功</p><p>&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>（2&nbsp;）添加项目</b></p><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;继续在git或者CMD命令行上执行以下命令：</p><blockquote><p>git remote add origin &lt;项目ssh地址&gt;</p></blockquote><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;一般这个命令执行成功以后本地仓库的项目便已经同远端仓库的项目保持同步了。不妨登录到git服务器上查看一下呗。</p><h2>6、克隆项目</h2><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;找到你刚才在记录下的远端仓库的地址，或者再次登录以下界面去复制远端仓库地址；</p><p><br></p><div class="image-package">
<div class="image-container" style="max-width: 700px; max-height: 623px;">
<div class="image-container-fill" style="padding-bottom: 58.28%;"></div>
<div class="image-view" data-width="1069" data-height="623"><img data-original-src="//upload-images.jianshu.io/upload_images/9989643-ae9576fcd04fcc89.png" data-original-width="1069" data-original-height="623" data-original-format="" data-original-filesize="64411" data-image-index="4" style="cursor: zoom-in;" class="image-loading"></div>
</div>
<div class="image-caption">克隆项目</div>
</div><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;然后执行一下命令行：</p><blockquote><p>git clone &lt;项目ssh地址&gt;</p></blockquote><h2>7、开始初步使用</h2><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;当我们将上述步骤完成以后，我们便可以初步使用git了。尝试执行一下：</p><blockquote>
<p>git status</p>
<p>git add -u</p>
<p>git commit -m "注释"</p>
</blockquote><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;查看命令行工具返回的结果，是不是和我们平时使用的时候完全一致了呢？</p><h2>8、完成第一次代码提交</h2><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;为了完成第一提交，你是否知道我们要执行那一条命令了呢？请继续看：</p><blockquote>
<p>git pull origin master;</p>
<p>git push origin master;</p>
</blockquote><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;这个时候，就有人不禁要问，我们平时的操作不就是直接执行git pull和git push就可以吗，你为什么要在后边加上正常指令后origin master呢。如果不是清楚，按照我们平时的操作再次执行一遍呗，看看结果再说吧。</p><blockquote>
<p>git status</p>
<p>git add -u</p>
<p>git commit -m "注释"</p>
<p>git pull</p>
</blockquote><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;你会发现执行到git pull操作时，居然不能拉取代码，来我们看看git工具给我们返回的提示是什么吧！</p><div class="image-package">
<div class="image-container" style="max-width: 630px; max-height: 181px;">
<div class="image-container-fill" style="padding-bottom: 28.73%;"></div>
<div class="image-view" data-width="630" data-height="181"><img data-original-src="//upload-images.jianshu.io/upload_images/9989643-49b8f143676b810e.png" data-original-width="630" data-original-height="181" data-original-format="" data-original-filesize="9674" data-image-index="5" style="cursor: zoom-in;" class="image-loading"></div>
</div>
<div class="image-caption">执行git pull操作不成功界面</div>
</div><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;这个原因git工具提示的很明白：就是因为本地仓库跟远端仓库关联不成功会引起的，我们只需要根据提示执行命令：</p><blockquote><p>git branch --set-upstream master origin/master</p></blockquote><p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;然后再重新提交一次代码，肯定是完全正常了。</p><p>参考网站：<a href="https://links.jianshu.com/go?to=http%3A%2F%2Fwww.ruanyifeng.com%2Fblog%2F2014%2F06%2Fgit_remote.html" target="_blank">http://www.ruanyifeng.com/blog/2014/06/git_remote.html</a>（Git远程操作详解）</p></article>
