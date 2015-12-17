### Getting Started with Redux
- [參考](https://egghead.io/lessons/javascript-redux-describing-state-changes-with-actions)

- 每個component的狀態都由redux的state來maintain
- 所有的state改變都是必須透過dispatch action來達成
- store記錄狀態，createStore時裡面傳入reducer(下例是counter)，來知道有action時狀態該如何改變
![store_getState](https://cloud.githubusercontent.com/assets/6972644/11875047/a5d0518e-a51d-11e5-9dbb-36efe84ce009.jpg)
- store.getState(): 取得目前store的state
- store.dispatch(): 觸發一個action去改變state
![store_dispatch](https://cloud.githubusercontent.com/assets/6972644/11875154/504e3810-a51e-11e5-92c0-8c0e1e8eeefd.jpg)
- store.subscribe(): 註冊一個callback, 任何action發生dispatch時就會來執行這個callback
![store_subscribe](https://cloud.githubusercontent.com/assets/6972644/11875216/9eea7402-a51e-11e5-8f46-ad411a0646b6.jpg)
- 把render function extract出來，並執行一次，就不用在click的時候才顯示，第一次執行就會顯示目前的counter
![extract render](https://cloud.githubusercontent.com/assets/6972644/11875263/d400cdd0-a51e-11e5-8487-fd4964cfce69.jpg)
- 