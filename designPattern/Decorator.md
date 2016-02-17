# Decorator

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
- 


https://github.com/gajus/react-css-modules#decorator
