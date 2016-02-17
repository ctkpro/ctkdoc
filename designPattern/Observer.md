# Observer

### 心得
- **XXXgenerator**發現值有改變的時候會呼叫**Observer**說：「我的內容已經更新過了，請你也更新你的輸出內容』

### 過去哪些案子裡有用過類似的Pattern
- 像是Redux裡的Store，儲存的狀態發生改變會通知有註冊(@connect)的Component進行重畫

### 哪個案子裡的設計如果可以用這個Pattern會更好
- MGR的bill畫面或許可以參考此設計

### 重點整理
- (Gang of Four) define a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.
- handling notification automatically
- Customer範例
![Implementing Customer with Observer](https://cloud.githubusercontent.com/assets/6972644/13007557/1bbd2338-d1cc-11e5-9a05-8d5d5da6d8a2.jpg)
- (Refactoring)replace hard-coded notifications with Observer
![replace hard-coded notifications with Observer](https://cloud.githubusercontent.com/assets/6972644/13007719/154d7bdc-d1cd-11e5-8ed5-920c59dcbb0b.jpg)
- 如果是cascading notification (A notify B then notify C)，可以考慮實作一個[Mediator](Mediator.md)
