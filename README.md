# 1. git操作
## 1.1. 将仓库从远程克隆到本地
	git clone url
## 1.2. 切换到个人的分支版本
	git checkout -b xxx origin/xxx
## 1.3. 修改本地文件后, 推送到远程仓库
	git add . : 添加更新到暂存区
	git commit -m "update" : 提交到本地版本区
	git push origin xxx : 推送到远程仓库个人的分支
## 1.4. 得到其它分支的远程更新
	git checkout yyy : 切换到yyy(其它)分支版本
	git pull origin yyy : 拉取远程yyy分支的更新到本地yyy分支

# 2. 个人分支下的文件说明
## 2.1. 每日测试题-张晓飞.doc
	个人整理的所有测试题合集, 以技术块划分
	包括题目和答案
## 2.2. 181025-每日测试题.doc
	某个班的所有测试题合集, 以天为单位划分
	只有题目
## 2.3. 181025-每日测试题(参考答案).doc
	某个班的所有测试题合集带答案的版本