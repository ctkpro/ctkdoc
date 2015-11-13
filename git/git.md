#給CTK用的git best best practices

## 開發流程
- 開發任何功能或debug前都要開一個branch (必讀2篇文章：[什麼是branch](https://github.com/doggy8088/Learn-Git-in-30-days/blob/master/docs/08%20%E9%97%9C%E6%96%BC%E5%88%86%E6%94%AF%E7%9A%84%E5%9F%BA%E6%9C%AC%E8%A7%80%E5%BF%B5%E8%88%87%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F.markdown)，[透過分支在同一個遠端儲存庫中進行版控](https://github.com/doggy8088/Learn-Git-in-30-days/blob/master/docs/27%20%E9%80%8F%E9%81%8E%E5%88%86%E6%94%AF%E5%9C%A8%E5%90%8C%E4%B8%80%E5%80%8B%E9%81%A0%E7%AB%AF%E5%84%B2%E5%AD%98%E5%BA%AB%E4%B8%AD%E9%80%B2%E8%A1%8C%E7%89%88%E6%8E%A7.markdown))

```git
(master)$ git checkout -b [BranchName]
```

> **[BranchName]**
> feature/xxx
> hotfix/xxx

SourceTree操作畫面
1. New Branch
![create-new-branch](https://cloud.githubusercontent.com/assets/6972644/11111822/da825c02-8947-11e5-9ba0-dc1c88a9b5d2.jpg)
2. 給一個branch name，按下create branch
![assign-branch-name](https://cloud.githubusercontent.com/assets/6972644/11111902/928ad52c-8948-11e5-80ad-dc150fca59ba.jpg)
3. 新的branch建立而且工作區域自動切換到新branch
![new-branch-created](https://cloud.githubusercontent.com/assets/6972644/11111944/0d0b6f32-8949-11e5-9bff-42d4f8a476cb.jpg)

- 開發完之後可以用merge或是rebase將新功能加回master ([merge與rebase的區別](https://docs.google.com/presentation/d/1Jh5nI-nyqxRSR_5jZMisWfKQrJ1WsomJavL-5bU0zsk/edit#slide=id.p))
	- 如果是使用**merge**
	```
	(BranchName)$ git checkout master //將目前分支切到master
	(master)    $ git merge [BranchName] //如果要使用merge所下的command
	```
	- 如果是使用**rebase**
	```
	//不需要切回master，在修改的[BranchName上執行]
	(BranchName)$ git rebase master
	```
	使用sourcetree操作rebase
	![sourcetree-rebase](https://cloud.githubusercontent.com/assets/6972644/11112197/9e082384-894b-11e5-802a-8b4300f5df19.jpg)
	rebase完之後的畫面(如果有衝突要處理)
	![after-rebase](https://cloud.githubusercontent.com/assets/6972644/11112262/39106dc8-894c-11e5-8c80-22b625895e58.jpg)
	切換到master (checkout master)
	![checkout-master](https://cloud.githubusercontent.com/assets/6972644/11112296/8a6aba98-894c-11e5-865e-8a10cc07cf6f.jpg)
	再merge更改的branch
	![merge-branch](https://cloud.githubusercontent.com/assets/6972644/11112312/ae2a1884-894c-11e5-96d7-8e839f456bfb.jpg)
	成功後再將分支刪除，push到remote
	![push-remote](https://cloud.githubusercontent.com/assets/6972644/11112517/e5ef32c0-894e-11e5-8c97-9c2a980d0ea2.jpg)
	
> **注意事項 **
> - merge or rebase前要issue review request
> - merge or rebase前通過所有的測試

- merge or rebase完將branch砍掉

```
git branch -d [BranchName]
```

## 注意事項
- 使用wiki
- maintain README.rd

## References
- [merge與rebase的差別](https://docs.google.com/presentation/d/1Jh5nI-nyqxRSR_5jZMisWfKQrJ1WsomJavL-5bU0zsk/edit#slide=id.p)：這個slide裡用的是sourcetree GUI做git command的demo，如果要用GUI的可以參考
- [Learn Git in 30 days (中文)](https://github.com/doggy8088/Learn-Git-in-30-days)：要對git有一個完整的概念可以參考這裡
- [如何上傳圖片到github](http://blog.davidebbo.com/2014/11/using-issues-for-github-pages-screenshots.html)：請參考文章章節 **Suggested option: use GitHub issues to store your images**
- [git best practices](https://projects.tigase.org/projects/tigase-server/wiki/Best_practices)


## 又加了一段文字