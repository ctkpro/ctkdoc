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
- createStore大概長這樣, ```dispatch({})``` 是讓store有一個初始的狀態
![createStore](https://cloud.githubusercontent.com/assets/6972644/11875441/8f553940-a51f-11e5-8b27-bca6fb83f2bc.jpg)

#### [React Counter Example](https://egghead.io/lessons/javascript-redux-react-counter-example)

- 現在要把react帶進來, render裡面會根據event觸發action
![counter](https://cloud.githubusercontent.com/assets/6972644/11875536/187dbb5c-a520-11e5-841d-4cbbc51c350b.jpg)
![introduce_react](https://cloud.githubusercontent.com/assets/6972644/11875556/333e2bca-a520-11e5-9d09-7424d5e28c69.jpg)
![application_look_like](https://cloud.githubusercontent.com/assets/6972644/11875588/638ce316-a520-11e5-971a-cc24bb31299d.jpg)

#### [Avoiding Array Mutations with concat(), slice(), and ...spread](https://egghead.io/lessons/javascript-redux-avoiding-array-mutations-with-concat-slice-and-spread?series=getting-started-with-redux)

- redux的state是imutable的，對於array的操作也是一樣，要呼叫的function是不能改變原本物件的function
- 加元素不要用```list.push(0)```，要用```list.concat(0)``` 

```
//ES6語法
[...list, 0]
```

- 刪除元素不要用```list.splice(index, 1)```, 要用```list.slice(0, index).concat(list.slice(index+1))```

```
//ES6語法
[
...list.slice(0, index),
...list.slice(index+1)
]
```

- 修改元素不要用(e.g. 元素值+1)```list[index]++```, 要用```list.slice(0, index).concat([list[index]+1]).concat(list.slice(index+1))```

```
//ES6語法
[
...list.slice(0, index),
list[index]+1,
...list.slice(index+1)
]
```