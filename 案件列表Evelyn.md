
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



## ProjectName 中英對照表

| 英文 (English) | 中文 (Chinese) |
|----------------|----------------|
| AdHoc          | 臨時傳送       |
| Station        | 駐站           |



---

已完工案件列表
| **前端欄位名稱 (columnName)** | **API Key** |
|------------------|------------------|
| 返回(RequestState==='Closed') | `AllowSendBack(btn)` |
| 滿意度 | `(btn)` |

