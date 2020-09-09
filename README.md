# AndroidStudyCode
study Android recode


git准备流程：

							1.
								看下C盘用户目录下有没有.ssh，有的话复制id_rsa.pub文件里面的秘钥，添加到github SSH上
															 没有的话执行：
																		ssh-keygen -t rsa -C "youremail@example.com"
															 疯狂回车
							2.
								到一个文件夹中，也就是本地仓库文件夹，执行：
																		git init
								之后会发现文件夹中多了一个.git文件，是用来追踪的
							3.
								到远程仓库要链接本地的文件夹下Clone with SSH，执行：
																		git remote add origin xxx.git 			xxx是Clone SSH
							4.
								REDME文件不在本地仓库所以执行：
																		git pull --rebase origin master
								（如果远程仓库为空则不用）
							
							
git使用流程：
							
														1.
															git add 新文件
														2.
															git commit -m "注释"
														3.
															git push origin master
						可以使用git status 查看当前文件状态
							
							
branch使用流程：
		命令常用：
			1	git branch	查看分支
			2	git branch name	新建分支,其中name为分支名称
			3	git checkout name	切换到name分支
			4	git merge name	合并name分支到当前分支
			5	git branch -d name	删除name分支
			6	git push -u name:name1	提交分支name到云端分支name1
			7	git log	查看commit日志
			
			
			开始
			1.提交文件至缓存:git add file/folder
			2.提交文件至版本库:git commit -m "description"
			3.本地新建分支:branch_name:git branch branch_name
			4.切换到新建分支:git checkout branch_name
			5.提交本地分支到云端:git push -u origin branch_name:cloud_branch_name
			6.切换到主分支: git checkout master
			7.合并分支:git merge branch_name/git meger origin/cloud_branch_name
			8.云端操作合并
			结束
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
			
	