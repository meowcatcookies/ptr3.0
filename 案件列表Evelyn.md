### **案件列表欄位表頭 API**

**API 路徑：**
`/api/StatusConfigurations/Grid/{param}`

**`param` 可輸入的值及對應案件列表類型：**
- `InQueueJobs` - 執行中案件列表
- `StationJobs` - 駐站案件列表
- `CompleteJobs` - 已完工案件列表
- `UndeterminedJobs` - 未定時案件列表
- `CanceledJobs` - 已取消案件列表
- `ScheduledJobs` - 排程案件列表

----

### **案件列表欄位名稱與 API KEY對應表（Mapping）**
大致上(所有類型)都差不多，若有疑問再提出

| **前端欄位名稱 (columnName)** | **API Key** |
|------------------|------------------|
| 需求 | `OrderNo+ TransTypeName + EquipName` |
| 下單單位 | `OrderLocationName` |
| 傳送單位 | `FromLocationName+BedNo` |
| 到達單位 | `ToLocationName+ToBedNo` |
| 傳送內容 | `TransTypeName` |
| 傳送工具 | `EquipName` |
| 需求時間 | `RequestTime` |
| 預約時間 | `AdvanceTime` |
| 派工時間 | `AssignTime` |
| 到達時間 | `ResponseTime` |
| 完工時間 | `CompleteTime` |
| 傳送員 | `PorterName` |
| 病患資訊 | `PatientName+PatientMedicalRecordNumber` |
| 注意事項 | `[核對]+{SubjectType}+#+{SubjectTypeId} +#+{RemarkNames}+{Remarks}` |
| 專案 | `ProjectName` |
| 滿意度 | `(btn)` |
| 稽核 | `Audits` |
| 案件狀態 | `JobState` |
| 已到達or未到達 | `ResponseState` |
| 重要or一般 | `MarkState` |
| 執行中過久未到達 | `ResponseTimeExceeded` |
| 傳送員-已讀or未讀 | `IsRead` |
| 緊急 | `Emergency` |
| 延遲(數字，>0) | `DelayCount` |
| 已核對、未核對 | `IsConfirm` |
| 傳送員申請取消案件 | `IsCancelling` |
| 核對錯誤 | `IsIgnore` |
| 病患、非病患 | `IsPatientMove` |
| 需來回案件 | `IsSendBack = true && HasSendback = true` |
| `RequestState` |New,Assign,Response,Closed|
---

已完工案件列表
| **前端欄位名稱 (columnName)** | **API Key** |
|------------------|------------------|
| 返回(RequestState==='Closed') | `AllowSendBack(btn)` |
| 滿意度 | `(btn)` |

