### **加入常用單位地點選項**

**API 路徑：**
`[GET]/api/RequestForm/LocationOptions/{param}`

**`param` 判斷依據為是否為病患傳送：**
- `true` - 病患傳送
- `false` - 非病患傳送
(api自動抓取用戶資訊，並提供該用戶的常用清單)
(Key:sort為常用清單的排序，非常用清單預設無sort = -1)
(若沒有常用單位請先到Feature設定)
----
### **常用地點管理**

**API 路徑：**
`[GET]/api/Feature/LocationCommons`

自動抓取該用戶的常用地點清單，可依照是否病患傳送以及排序顯示給用戶調整。

---
**API 路徑：**
`[PUT]/api/Feature/LocationCommons`
**requestBody(格式array)**
```
[
  {
      "id": "9dbb6774-06e9-4f6b-962e-9f978cd741b7",
      "toLocationId": "01246563-8e50-4065-b884-4587246b5efb",
      "sort": 3,
      "isPatient": true
  }
]
```
**`param` 將該用戶修改過的資料以PUT更新：**
- `id` - 已存在的用戶常用單位。
- `toLocationId` - 單位地點(須為已存在的單位)。
- `sort` - 可修改其排序(將用在下單下拉選單排序，請前端給予正確順序並修改)。
- `isPatient` - 用以分辨下單時是否為病患傳送。

----
**API 路徑：**
`[POST]/api/Feature/LocationCommons`
**requestBody**
```
{
    "toLocationId": "0251058d-57f2-407f-85ec-ab2eaf5c7cbb",
    "sort": 1,
    "isPatient": true
}
```
**`param` 將該用戶修改過的資料以PUT更新：**
- `toLocationId` - 單位地點(須為已存在的單位)。
- `sort` - 可隨意給數字(後端將以是否病患傳送為基礎查詢資料庫，並使用最大sort數字+1)。
- `isPatient` - 用以分辨下單時是否為病患傳送。
