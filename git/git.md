#給CTK用的git best best practices

## 開發流程簡述
- 開發任何功能或debug前都要開一個branch (必讀2篇文章：[什麼是branch](https://github.com/doggy8088/Learn-Git-in-30-days/blob/master/docs/08%20%E9%97%9C%E6%96%BC%E5%88%86%E6%94%AF%E7%9A%84%E5%9F%BA%E6%9C%AC%E8%A7%80%E5%BF%B5%E8%88%87%E4%BD%BF%E7%94%A8%E6%96%B9%E5%BC%8F.markdown)，[透過分支在同一個遠端儲存庫中進行版控](https://github.com/doggy8088/Learn-Git-in-30-days/blob/master/docs/27%20%E9%80%8F%E9%81%8E%E5%88%86%E6%94%AF%E5%9C%A8%E5%90%8C%E4%B8%80%E5%80%8B%E9%81%A0%E7%AB%AF%E5%84%B2%E5%AD%98%E5%BA%AB%E4%B8%AD%E9%80%B2%E8%A1%8C%E7%89%88%E6%8E%A7.markdown))

> **[BranchName]**
> feature/xxx
> hotfix/xxx

- 新功能或bug fix都在新的branch上工作
- 做完之後發pull request給team member做code review
- code review完之後就可以merge回master

## SourceTree & GitHub操作畫面

> **注意**：以下畫面的branch name可能沒有統一，因為是在不同的測試中抓取的截圖

1. New Branch
![create-new-branch](https://cloud.githubusercontent.com/assets/6972644/11111822/da825c02-8947-11e5-9ba0-dc1c88a9b5d2.jpg)
2. 給一個branch name，按下create branch
![assign-branch-name](https://cloud.githubusercontent.com/assets/6972644/11111902/928ad52c-8948-11e5-80ad-dc150fca59ba.jpg)
3. 新的branch建立而且工作區域自動切換到新branch
![new-branch-created](https://cloud.githubusercontent.com/assets/6972644/11111944/0d0b6f32-8949-11e5-9bff-42d4f8a476cb.jpg)
4. 把建立的branch push到remote，選取`新開的branch`，勾選`push all tags`
![push-branch-to-remote](https://cloud.githubusercontent.com/assets/6972644/11139947/45ca2698-8a10-11e5-8c39-643a46a05e23.jpg)
5. 此時可以發現remote端也會建立一個相同的branch name
![new-branch-in-remote](https://cloud.githubusercontent.com/assets/6972644/11139983/8487f572-8a10-11e5-974e-8f75e189b0f6.jpg)
6. 此時我們在local branch做修改，commit並push上傳至remote，這個時候我們就需要team member來幫我們做**code review**了
![new-code-update](https://cloud.githubusercontent.com/assets/6972644/11140006/c1824d56-8a10-11e5-9949-70ca74261957.jpg)
7. 到github的頁面，可以對你修改的branch發**pull request**，點選`New Pull Request`
![pull-request](https://cloud.githubusercontent.com/assets/6972644/11140076/60055a86-8a11-11e5-951c-884f4af19c7c.jpg)
8. 寫一個comment(比commit message更詳盡)來解釋你修改code的內容或程式邏輯(可以使用markdown)，按下`create pull request`
![#fill-in-pull-request-information](https://cloud.githubusercontent.com/assets/6972644/11140096/a141a4e6-8a11-11e5-8d64-e6fac659320e.jpg)
9. 如果需要對各行做comment，可以在之後的頁面點下commit message
![select-commit-message](https://cloud.githubusercontent.com/assets/6972644/11140133/07415188-8a12-11e5-9ae1-5b6d2e72fe3d.jpg)
10. 在想要加註解的行數前面按下`加號`，然後加入你對那行的註解，讓別人看到這行程式碼的時候更瞭解你在做什麼？
![add-comments-in-line](https://cloud.githubusercontent.com/assets/6972644/11140148/2ce04188-8a12-11e5-850f-138c61c29cc4.jpg)
11. 被assign的人會收到一封email，可以到github上面看這個pull request，如果有問題可以再加回comment，如果沒有問題就按下merge pull request
12. merge完之後就可以在github上面把branch刪除，刪除完之後即可以通知team member
![delete-merged-branch](https://cloud.githubusercontent.com/assets/6972644/11140234/43d86112-8a13-11e5-98ad-3be43ed18c9a.jpg)
13. team member在local端可以按下fetch, 勾選**Prune tracking branches no longer present on remote** 還有**Fetch all tags**
![fetch-all-tags](https://cloud.githubusercontent.com/assets/6972644/11140254/7f1edbac-8a13-11e5-9a62-42bddc6cd64f.jpg)
14. fetch完之後會發現remote端的branch已經被刪除
![remote-branch-been-deleted-from-local](https://cloud.githubusercontent.com/assets/6972644/11140318/284cba5a-8a14-11e5-8851-ab99104c5a88.jpg)
15. 此時可以把分支切回到`master`，並把之前工作的分支刪除，然而大多數的狀況可能是reviewer還沒時間review，你就必須要開發新功能，這種情況下也沒關係，在local端先切回`master`，然後把工作分支刪除，再接下去開發新feature或是修bug，待reviewer review完merge完之後，再把remote端的分支狀況同步回local端
	
> **注意事項 **
> - merge or rebase前通過所有的測試

## 其它工作建議
- 適度使用wiki (適用詳盡的解說)
- maintain README.md

## References
- [merge與rebase的差別](https://docs.google.com/presentation/d/1Jh5nI-nyqxRSR_5jZMisWfKQrJ1WsomJavL-5bU0zsk/edit#slide=id.p)：這個slide裡用的是sourcetree GUI做git command的demo，如果要用GUI的可以參考
- [Learn Git in 30 days (中文)](https://github.com/doggy8088/Learn-Git-in-30-days)：要對git有一個完整的概念可以參考這裡
- [如何上傳圖片到github](http://blog.davidebbo.com/2014/11/using-issues-for-github-pages-screenshots.html)：請參考文章章節 **Suggested option: use GitHub issues to store your images**
- [git best practices](https://projects.tigase.org/projects/tigase-server/wiki/Best_practices)


## Appendix

### 如果是使用**rebase**
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
