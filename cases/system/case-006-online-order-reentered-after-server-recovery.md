# Case 006 - 線上訂單結帳後再次進單

## 客服反映內容

項次：[ID]  
店名：[門市/公司]  
POS 版次：v4.0.1  
線上點餐平台版本：[線上點餐平台]  
線上點餐平台帳號/密碼/檢碼：[SECRET]  
結帳方式：後結

客服回報特定桌號在結帳後不會自動清桌，但其他桌號正常。

客服確認 POS1 與 POS2 的桌況設定皆未啟用「手動清桌」，店家也表示未調整過相關設定。後續客服重新測試時，清桌行為恢復正常。

當下因線路繁忙，客服無法同步測試線上訂單進單是否也有相同狀況。

正確受影響桌號：

- B6
- A5Bar
- A7Bar

## 查詢結果

查詢相關線上訂單資料：

### A5Bar

- orderid：[ID]
- ordernumber：[ID]
- memo：線上加點單據(D)|[PLATFORM_ORDER_ID]|[ID]|
- orderno：[ID]

### B6

- orderid：[ID]
- ordernumber：[ID]
- memo：線上加點單據(D)|[PLATFORM_ORDER_ID]|[ID]|
- orderno：[ID]

### A7Bar

- orderid：[ID]
- ordernumber：[ID]
- memo：線上加點單據(D)|[PLATFORM_ORDER_ID]|[ID]|
- orderno：[ID]

查看 log 後，確認線上點餐 server 在該時段發生異常。

消費者點餐與店家操作結帳都發生在 server 異常期間。server 恢復正常後，相關線上訂單又再次進單到 POS，導致已結帳桌號出現重新進單的狀況。

## 處理判定

系統/串接異常，需上 Redmine 請 RD 協助確認線上點餐 server 異常恢復後的重送處理邏輯。
