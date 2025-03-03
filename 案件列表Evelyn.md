
## **案件列表欄位名稱與 API KEY對應表（Mapping）**
大致上(所有類型)都差不多，若有疑問再提出

| **前端欄位名稱 (columnName)** | **API Key** |
|------------------|------------------|
| 需求 | `OrderNoTransTypeNameEquipName` |
| 下單單位 | `OrderLocationName` |
| 傳送單位 | `FromLocationNameBedNo` |
| 到達單位 | `ToLocationNameToBedNo` |
| 傳送內容 | `TransTypeName` |
| 傳送工具 | `EquipName` |
| 需求時間 | `RequestTime` |
| 預約時間 | `AdvanceTime` |
| 派工時間 | `AssignTime` |
| 到達時間 | `ResponseTime` |
| 完工時間 | `CompleteTime` |
| 傳送員 | `PorterName` |
| 病患資訊 | `PatientNamePatientMedicalRecordNumber` |
| 注意事項 | `[核對]+{SubjectType}+#+{SubjectTypeId} +#+{RemarkNames}+{RemarkItemList}` |
| 專案 | `ProjectName` |
| 滿意度 | `(btn)` |
| 稽核 | `Audits` |
| 案件狀態 | `JobState()` |

### 案件狀態

| 中文 (Chinese)       | 英文 (English)       |
|----------------------|----------------------|
| 1-2(重要)、3-10(一般)value是數字 | `Priority` |
| 已到達or未到達 | `ResponseState` |
| (參考下方五種狀態) | `JobState` |

#### JobState 中英對照表

| 英文 (English)       | 中文 (Chinese)       |
|----------------------|----------------------|
| Advanced             | 預約                 |
| Waiting              | 等待派工             |
| WaitingExceeded      | 逾時未派             |
| Excuting             | 執行中               |
| ExcutingExceeded     | 執行過久             |
### 篩選狀態

| 中文 (Chinese)       | 英文 (English)       |
|----------------------|----------------------|
| 已到達or未到達 | `ResponseState` |
| 重要or一般 | `MarkState` |
| 執行中過久未到達 | `ResponseTimeExceeded` |
| 傳送員-已讀or未讀 | `IsRead` |
| 緊急 | `"ColumnLabel": "Others",Emergency` |
| 延遲 | `"ColumnName": "延遲","Data": ""(Data有值就是有延遲)` |
| 已核對、未核對 | `IsConfirm` |
| 傳送員申請取消案件 | `IsCancelling` |
| 核對錯誤 | `IsIgnore` |
| 病患、非病患 | `IsPatientMove` |
| 需來回案件 | `IsSendBack = true && HasSendback = true` |

### ActionList-中英對照表

| 英文 (English)       | 中文 (Chinese)       |
|----------------------|----------------------|
| Assign               | 派工                 |
| Transfer             | 轉派(顯示工號，不是中文)                 |
| Handover             | 交接                 |
| Emergency            | 提升為緊急案件                 |
| TransferToStation    | 轉駐站案件             |
| Delay                | 延遲                 |
| Cancel               | 取消                 |
| Edit                 | 編輯                 |
| Response             | 到達                 |
| Complete             | 完工                 |



### ProjectName 中英對照表

| 英文 (English) | 中文 (Chinese) |
|----------------|----------------|
| AdHoc          | 臨時傳送       |
| Station        | 駐站           |

## [GET]/api/StatusConfigurations/Details/{orderno}

### Detail-案件歷程 中英/欄位KEY對照表

| 欄位  | KEY |
|----------------|----------------|
| 使用者名稱  | userName |
| 動作  | action |
| 時間 | actionTime |
| 其他資訊  | cancelName+delayName+historyRemark |
| 傳送員  | porterName |

| 中文  | KEY |
|----------------|----------------|
| 取消原因 | cancelName |
| 延遲原因 | delayName |
| 案件歷史紀錄附註 | historyRemark |

### Detail-案件內容 中英/欄位KEY對照表

| 欄位  | KEY |
|----------------|----------------|
| 案件編號  | orderNo |
| 傳送內容  | transTypeName |
| 傳送工具  | equipName |
| 下單單位  | orderLocationName |
| 傳送單位  | fromLocationName |
| 到達單位  | toLocationName |
| 病患姓名  | patientName |
| 傳送床號  | bedNo |
| 到達床號  | toBedNo |
| 病患生日  | patientBirthDate |
| 病歷號  | patientMedicalRecordNumber |
| 病患等級  | patientLevelName |
| 需求時間  | requestTime |
| 預約時間  | advanceTime(如果沒有似乎不用顯示此欄位) |
| 注意事項  | remarksList-remarkName + remarks |
| 核對項目 | SubjectType(string) |
| 條碼 | SubjectTypeId(string) |
| 核對狀況(true=已核對/false=未核對) | IsConfirm(bool) |
| 紀錄 | (展開後以下的KEY) |
| 成功=true/失敗=false|verifyIsSuccess|
| 紀錄之訊息 |verifyMessage|
| 威合=true/院方名稱=false | verifyIsHosp (bool) |
| 紀錄時間 | verifyCreateAt (datetime) |

| 中文  | KEY |
|----------------|----------------|
| 備註事項 | remarksList |
| 備註事項中的項目 | remarkName |
| 文字備註 | remarks |

### Detail-交接紀錄 中英/欄位KEY對照表

| 欄位  | KEY |
|----------------|----------------|
| 轉出人  | fromUserName |
| 轉入人  | toUserName |
| 交接地點  | locationName |
| 交接時間  | completionTime |
| 核對項目  | 無 |

### Detail-稽核評價 中英/欄位KEY對照表

| 欄位  | KEY |
|----------------|----------------|
| 案件編號  | orderNo |
| 分數  | score |
| 使用者名稱  | userName |
| 稽核評價  | question |
| 建立日期  | createdate |

### Detail-簽收評價 中英/欄位KEY對照表

| 欄位  | KEY |
|----------------|----------------|
| 案件編號  | orderNo |
| 簽收評價  | evaluationName |
| 備註  | remark |
| 分數  | score |
| 建立日期  | createDate |
| 簽收人  | signee |

### RequestAction-案件動作 中英/欄位KEY對照表

| 中文  | 英文 |
|----------------|----------------|
| 新增案件 | New |
| 直接指派 | Designate |
| 未定時案件啟動 | UndeterminedStart |
| 排程案件啟動 | ScheduledStart |
| 單位返回 | SendBack |
| 手機返回 | SendBackByMobile |
| 定點定時 To 臨時傳送 | TransferToCentral |
| 新增案件(醫院) | HospitalNew |
| 派工 | Assign |
| 智慧派工 | SA |
| 轉派 | Transfer |
| 到達 | Response |
| 完工 | Complete |
| 取消 | Cancel |
| 傳送員請求取消 | ApplyForCancel |
| 中心同意取消 | ApplyForCancel_Ok |
| 中心駁回取消 | ApplyForCancel_No |
| 編輯 | Edit |
| 延遲 | Delay |
| 提升為緊急案件 | UpToEmergency |
| 重新申請 | RecreateOrder |
| 指派交接 | HandoverDesignated |
| 交接Bus Route | HandoverToBus |
| 交接成功 | HandoverSuccess |
| 交接取消 | HandoverCancel |
| 定點定時轉臨時傳送 | BusRouteToCentral |
| 轉臨時傳送 | TransferToAdhoc |
| 轉駐站 | TransferToStation |
