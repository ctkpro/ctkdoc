# Decorator

### 心得
- 要為原有的物件添增新的功能，此功能可能在各個不同的物件中執行相同的動作

### 過去哪些案子裡有用過類似的Pattern
- ```redux```的 ````@connect```, ````@connectData```, 還有```react-intl```的```@injectIntl```

### 哪個案子裡的設計如果可以用這個Pattern會更好
- mgr的poject中有很多unbind().bind()的功能，有可能會unbind過去的動作結果發生潛在的錯誤，可以參考 **Javascript 設計模式與開發實踐**裡提到的window.onload的作法

一開始的設計

```javascript
window.onload = function(){
    alert(1);
}

var _onload = window.onload || function(){};

window.onload = function(){
    _onload();
    alert(2);
}
```

使用```Function.prototype.before``` and ```Function.prototyp.after```設計之後

```javascript
window.onload = function(){
    alert(1);
}

window.onload = (window.onload || function(){}).after(function(){
    alert(2);
}).after(function(){
    alert(3);
}).after(function(){
    alert(4);
});

```


### 重點整理

- GoF 參考架構圖
![GoF Decorator](https://cloud.githubusercontent.com/assets/6972644/13096814/1d4c55b4-d557-11e5-8e71-5f39f3cbae99.jpg)

- 參考react的@connectData

```javascript
import React, { Component } from 'react';
import hoistStatics from 'hoist-non-react-statics';

/*
  Note:
    When this decorator is used, it MUST be the first (outermost) decorator.
    Otherwise, we cannot find and call the fetchData and fetchDataDeffered methods.
*/

export default function connectData(fetchData, fetchDataDeferred) {
  return function wrapWithFetchData(WrappedComponent) {
    class ConnectData extends Component {
      render() {
        return <WrappedComponent {...this.props} />;
      }
    }

    ConnectData.fetchData = fetchData;
    ConnectData.fetchDataDeferred = fetchDataDeferred;

    return hoistStatics(ConnectData, WrappedComponent);
  };
}
```

- 設計 **Decorator** 時最好不要有相依性(e.g. 『進行資料加密』的 **Decorator** 可能會妨礙『用以過濾某些字』的 **Decorator** -- 如果加密發生於過濾之前)
- 如果實在有相依性可以使用 **Creation Methods** 取用 **Decorator** 的安全組合 (參考： *Encapsulate Classes with Factory*)
- **Decorator** 動態的增加物件的功能。相對於用繼承的方式來擴充功能，裝飾品提供更彈性的方法來擴充物件的功能。
- 在不改變函數原始碼的情況下，能給函數增加功能[Javascript 設計模式與開發實踐]

