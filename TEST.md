# WooSearch Test Script

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
## Table of Contents

- [User Story 1](#user-story-1)
  - [啟動與安裝](#啟動與安裝)
    - [TestCase:啟用 Plugin（WooCommerce 未安裝 / 啟用）](#testcase啟用-plugin（woocommerce-未安裝--啟用）)
    - [TestCase:啟用 Plugin（WooCommerce 已啟用）](#testcase啟用-plugin（woocommerce-已啟用）)
    - [TestCase:停用 WooCommerce 後，Plugin 會自動停用（WooCommerce 已啟用）](#testcase停用-woocommerce-後，plugin-會自動停用（woocommerce-已啟用）)
    - [TestCase:啟用 Plugin左手邊的menu會出現WooSearch](#testcase啟用-plugin左手邊的menu會出現woosearch)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->
## User Story 1
### 啟動與安裝
#### TestCase:啟用 Plugin(WooCommerce 未安裝/啟用)
- **步驟：**
- 進入「http://{domain}/wp-admin/plugins.php」
- 對「WooSearch」外掛點擊「啟用」
> 結果 >>> 啟動失敗，跳出提示訊息：「WooCommerce is deactivate! Please activate WooCommerce first.」

#### TestCase:啟用 Plugin(WooCommerce 已啟用)
- **步驟：**
- 進入```http://{domain}/wp-admin/plugins.php```
- 對「WooSearch」外掛點擊「啟用」
> 結果 >>> 啟用成功，沒有錯誤訊息

#### TestCase:停用 WooCommerce 後, Plugin 會自動停用(WooCommerce 已啟用)
- **步驟:**
- 進入「http://{domain}/wp-admin/plugins.php」
- 對「WooCommerce」外掛點擊「停用」
> 結果 >>> 「WooSearch」自動轉為「停用」，並跳出提示訊息：「WooCommerce is deactivate! Please activate WooCommerce first.」

#### TestCase:啟用 Plugin左手邊的menu會出現WooSearch
- **Activate** WooSearch Plugin 之後，左手邊的Menu會出現 ```WooSearch``` 的icon
- 點選 ```WooSearch``` 的icon 會到 WooSearch 的設定頁面
- **Deactivate** WooSearch之後，左手邊的 WooSearch icon會消失
