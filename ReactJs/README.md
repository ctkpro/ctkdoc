### Getting Started with Redux
- [參考](https://egghead.io/lessons/javascript-redux-describing-state-changes-with-actions)

- 每個component的狀態都由redux的state來maintain
- 所有的state改變都是必須透過dispatch action來達成
- store記錄狀態，createStore時裡面傳入reducer(下例是counter)，來知道有action時狀態該如何改變
![store_getState](https://cloud.githubusercontent.com/assets/6972644/11875047/a5d0518e-a51d-11e5-9dbb-36efe84ce009.jpg)
- 