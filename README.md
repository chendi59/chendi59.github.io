#优化部署与管理
---
##一. 博客搭建流程
1. **创建github仓库，zzming.github.io；**
2. **创建两个分支：master 与 develop；**
3. **设置develop为默认分支（因为我们只需要手动管理这个分支上的Hexo网站文件）；**
4. **本地手动创建zzming.github.io文件夹；**
5. **在本地zzming.github.io文件夹下通过Git bash依次执行npm install hexo、hexo init、npm install 和 npm install hexo-deployer-git；**
6. **使用git clone 克隆 zzming.github.io仓库到本地zzming.github.io文件夹:**

		6.1 git clone --no-checkout git@github.com:zzming/zzming.github.io.git tmp
		6.2 mv tmp/.git .   #将 tmp 目录下的 .git 目录移到当前目录
		6.3 rmdir tmp
		6.4 git reset --hard HEAD

7. **修改_config.yml中的deploy参数，分支应为master；**
8. **依次执行git add .、git commit -m “…”、git push origin hexo提交网站相关的文件；**
9. **执行hexo generate -d生成网站并部署到GitHub上。**

	在GitHub上的zzming.github.io仓库就有两个分支，一个develop分支用来存放网站的原始文件，一个master分支用来存放生成的静态网页。

##二. 博客管理流程
---
1. **日常修改**

	在本地对博客进行修改（添加新博文、修改样式等等）后，通过下面的流程进行管理：

		1.1 依次执行git add .、git commit -m “…”、git push origin hexo指令
			将改动推送到GitHub（此时当前分支应为develop）；
		1.2 然后才执行hexo generate -d发布网站到master分支上。

2. **本地资料丢失**

	当重装电脑之后，或者想在其他电脑上修改博客，可以使用下列步骤：

		2.1 使用git clone git@github.com:zzming/zzming.github.io.git拷贝仓库（默认分支为develop）；
		2.2 在本地新拷贝的zzming.github.io文件夹下通过Git bash依次执行下列指令：
			npm install hexo、npm install、npm install hexo-deployer-git（记得，不需要hexo init这条指令）。