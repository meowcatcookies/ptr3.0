## 批次派工選項 [GET]/api/StatusConfigurations/Assign?isStation=false
 * 沒有時間就是今天
 * 指定時間
   * /api/StatusConfigurations/Assign?isStation=false&date=2025-03-18
 * 傳送員選項API
   * /api/RequestForm/PorterOptions?isOnDuty=true&isStation=false
   * 請依照頁面調整是否為駐站傳送員isStation=(bool)
<img src="img\2025-03-19 15_26_49-執行中案件列表 - UETrack™.jpg" alt="批次派工" >

### 批次派工選項 中英/欄位KEY對照表

| 中文  | 英文 |
|----------------|----------------|
| 案件編號 | orderNo |
| 傳送單位 | fromLocationName |
| 到達單位 | toLocationName |
| 傳送床號 | bedNo |
| 到達床號 | toBedNo |
| 傳送內容 | transTypeName |
| 傳送工具 | equipName |
| 需求時間 | requestTime |
| 預約時間 | advanceTime(nullable) |

### 批次派工(送出) [PUT]/api/StatusConfigurations/Assign
#### Body
```
{
  "isRush": true,
  "porterId": "3cd5544e-9e0a-4baf-8890-9d029d5f4789",
  "orderNos": [
    "2025030700006"
  ]
}
```
#### 批次派工Body 中英/欄位KEY對照表
 | 中文  | 英文 |
 |----------------|----------------|
 | 臨時插單 | locationName(bool) |
 | 傳送員 | porterId  |
 | 訂單編號 | orderNos(arrary) |


## 批次轉派選項 [GET]/api/StatusConfigurations/Transfer?isStation=false
 * 沒有時間就是今天
 * 指定時間
   * /api/StatusConfigurations/Transfer?isStation=false&date=2025-03-18
 * 傳送員選項API
   * /api/RequestForm/PorterOptions?isOnDuty=true&isStation=false
   * 請依照頁面調整是否為駐站傳送員isStation=(bool)
<img src="img\2025-03-19 15_36_15-執行中案件列表 - UETrack™.jpg" alt="批次轉派" >

### 批次轉派選項 中英/欄位KEY對照表

| 中文  | 英文 |
|----------------|----------------|
| 案件編號 | orderNo |
| 傳送單位 | fromLocationName |
| 到達單位 | toLocationName |
| 傳送床號 | bedNo |
| 到達床號 | toBedNo |
| 傳送內容 | transTypeName |
| 傳送工具 | equipName |
| 需求時間 | requestTime |
| 預約時間 | advanceTime(nullable) |
| 派工時間 | assignTime |
| 傳送員 | porterName |

### 批次派工(送出) [PUT]/api/StatusConfigurations/Transfer
#### Body
```
{
  "isRush": true,
  "porterId": "3cd5544e-9e0a-4baf-8890-9d029d5f4789",
  "orderNos": [
    "2025030700006"
  ]
}
```
#### 批次派工Body 中英/欄位KEY對照表
 | 中文  | 英文 |
 |----------------|----------------|
 | 臨時插單 | locationName(bool) |
 | 傳送員 | porterId  |
 | 訂單編號 | orderNos(arrary) |


## 批次到達選項 [GET]/api/StatusConfigurations/Response?isStation=false
 * 沒有時間就是今天
 * 指定時間
   * /api/StatusConfigurations/Response?isStation=false&date=2025-03-18

<img src="img\2025-03-19 15_58_20-駐站案件列表 - UETrack™.jpg" alt="批次到達" >

### 批次轉派選項 中英/欄位KEY對照表

| 中文  | 英文 |
|----------------|----------------|
| 案件編號 | orderNo |
| 傳送單位 | fromLocationName |
| 到達單位 | toLocationName |
| 傳送床號 | bedNo |
| 到達床號 | toBedNo |
| 傳送內容 | transTypeName |
| 傳送工具 | equipName |
| 需求時間 | requestTime |
| 預約時間 | advanceTime(nullable) |
| 派工時間 | assignTime |
| 傳送員 | porterName |

### 批次轉派(送出) [PUT]/api/StatusConfigurations/Transfer
#### Body
```
[
  "2025030700006"//訂單編號orderNo
]

```

## 批次完工選項 [GET]/api/StatusConfigurations/Complete?isStation=false
 * 沒有時間就是今天
 * 指定時間
   * /api/StatusConfigurations/Complete?isStation=false&date=2025-03-18

<img src="img\2025-03-19 16_07_14-駐站案件列表 - UETrack™.jpg" alt="批次完工" >

### 批次完工選項 中英/欄位KEY對照表

| 中文  | 英文 |
|----------------|----------------|
| 案件編號 | orderNo |
| 傳送單位 | fromLocationName |
| 到達單位 | toLocationName |
| 傳送床號 | bedNo |
| 到達床號 | toBedNo |
| 傳送內容 | transTypeName |
| 傳送工具 | equipName |
| 需求時間 | requestTime |
| 預約時間 | advanceTime(nullable) |
| 派工時間 | assignTime |
| 傳送員 | porterName |
| 到達時間 | responseTime |

### 批次完工(送出) [PUT]/api/StatusConfigurations/Complete
#### Body
```
[
  "2025030700006"//訂單編號orderNo
]

```

## 批次延遲選項 [GET]/api/StatusConfigurations/Delay?isStation=false
 * 沒有時間就是今天
 * 指定時間
   * /api/StatusConfigurations/Delay?isStation=false&date=2025-03-18
 * 延遲選項API
   * /api/StatusConfigurations/DelayOptions

<img src="img\2025-03-19 16_18_39-駐站案件列表 - UETrack™.jpg" alt="批次延遲" >

### 批次延遲選項 中英/欄位KEY對照表

| 中文  | 英文 |
|----------------|----------------|
| 案件編號 | orderNo |
| 傳送單位 | fromLocationName |
| 到達單位 | toLocationName |
| 傳送床號 | bedNo |
| 到達床號 | toBedNo |
| 傳送內容 | transTypeName |
| 傳送工具 | equipName |
| 需求時間 | requestTime |
| 預約時間 | advanceTime(nullable) |
| 派工時間 | assignTime |
| 傳送員 | porterName |
| 到達時間 | responseTime |

### 批次延遲(送出) [PUT]/api/StatusConfigurations/Delay
#### Body
```
{
  "orderNos": [
    "2024031900002"
  ],
  "Remark": "TEST",
  "DelayId": "9c43935f-9845-499b-ac67-e780657d53bd"
}
```
#### 批次延遲Body 中英/欄位KEY對照表
 | 中文  | 英文 |
 |----------------|----------------|
 | 延遲備註 | Remark |
 | 延遲選項Id | DelayId  |
 | 訂單編號 | orderNos(arrary) |


## 批次取消選項 [GET]/api/StatusConfigurations/Cancel?isStation=false
 * 沒有時間就是今天
 * 指定時間
   * /api/StatusConfigurations/Cancel?isStation=false&date=2025-03-18
 * 取消選項API
   * /api/StatusConfigurations/CancelOptions
   *
<img src="img\2025-03-19 16_11_50-駐站案件列表 - UETrack™.jpg" alt="批次取消" >

### 批次取消選項 中英/欄位KEY對照表

| 中文  | 英文 |
|----------------|----------------|
| 案件編號 | orderNo |
| 傳送單位 | fromLocationName |
| 到達單位 | toLocationName |
| 傳送床號 | bedNo |
| 到達床號 | toBedNo |
| 傳送內容 | transTypeName |
| 傳送工具 | equipName |
| 需求時間 | requestTime |
| 預約時間 | advanceTime(nullable) |
| 派工時間 | assignTime |
| 傳送員 | porterName |
| 到達時間 | responseTime |

### 批次取消(送出) [PUT]/api/StatusConfigurations/Cancel
#### Body
```
{
  "orderNos": [
    "2024031900002"
  ],
  "Remark": "TEST",
  "CancelId": "00f05f25-5a8f-479a-811a-3b5ef3f2caa6"
}
```
#### 批次取消Body 中英/欄位KEY對照表
 | 中文  | 英文 |
 |----------------|----------------|
 | 取消備註 | Remark |
 | 取消選項Id | CancelId  |
 | 訂單編號 | orderNos(arrary) |
