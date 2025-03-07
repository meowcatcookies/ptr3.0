
*   **派工 (指派案件給傳送員)**:
    *   `PATCH /api/StatusConfigurations/Assign` - 說明：**派工-指派案件給傳送員**。傳送員選項可參考 `[GET]/api/RequestForm/PorterOptions?isOnDuty=true and isStation=false`。
*   **提升為緊急案件**:
    *   `PATCH /api/StatusConfigurations/UpToEmergency/{orderNo}` - 說明：**將案件提升為緊急狀態**。適用於 "執行中案件列表" 以及 "駐站案件列表"。
*   **延遲**:
    *   `PATCH /api/StatusConfigurations/Delay` - 說明：**新增案件延遲**。延遲原因選項請參考 `[GET] /api/StatusConfigurations/DelayOptions`。
*   **轉駐站案件**:
    *   `PATCH /api/StatusConfigurations/TransferToStation` - 說明：**將案件轉為駐站案件**，並更新相關資訊。
*   **取消**:
    *   `PATCH /api/StatusConfigurations/Cancel` - 說明：**取消案件**。取消原因選項請參考 `[GET] /api/StatusConfigurations/CancelOptions`。適用於 "執行中案件列表" 以及 "駐站案件列表"。
*   **到達 (更新案件為已到達狀態)**:
    *   `PATCH /api/StatusConfigurations/Response/{orderNo}` - 說明：**更新案件為已到達狀態**。更新案件的回應時間並將狀態改為已到達。
*   **完成案件**:
    *   `PATCH /api/StatusConfigurations/Complete/{orderNo}` - 說明：**完成案件**。需要已指派傳送員且已到達。
*   **交接 (執行案件交接)**:
    *   `PATCH /api/StatusConfigurations/Handover` - 說明：**執行案件交接**。將案件交接給新的傳送員，需要案件已到達且有指派傳送員。
*   **交接完成 (確認交接)**:
    *   `PATCH /api/StatusConfigurations/Designate/{orderNo}` - 說明：**確認交接**。更新交接紀錄+更新案件傳送員。
*   **編輯**:
    *   `PATCH /api/StatusConfigurations/Edit`
        *   **需要依據是否攜帶病患 GET 不同 Option**: 您可能需要查看 `/api/RequestForm/TransTypeOptions`、`/api/RequestForm/LocationOptions/{isPatientMove}`、`/api/RequestForm/EquipOptions`、`/api/RequestForm/RemarksOptions` 等 API，它們的選項會根據 `isPatientMove` 參數而有所不同。
*   **轉派 (再派 - 指派案件給傳送員)**:
    *   `PATCH /api/StatusConfigurations/Transfer`
    *   傳送員選項可參考 `[GET]/api/RequestForm/PorterOptions?isOnDuty=true and isStation=false`。
*   **批次 - 轉派**:
    *   `PUT /api/StatusConfigurations/Transfer`
    *   傳送員選項可參考 `[GET]/api/RequestForm/PorterOptions?isOnDuty=true and isStation=false`。
*   **批次 - 派工**:
    *   `PUT /api/StatusConfigurations/Assign`
    *   傳送員選項可參考 `[GET]/api/RequestForm/PorterOptions?isOnDuty=true and isStation=false`。
*   **批次 - 到達**:
    *   `PUT /api/StatusConfigurations/Response`
*   **批次 - 完工**:
    *   `PUT /api/StatusConfigurations/Complete`
*   **批次 - 取消**:
    *   `PUT /api/StatusConfigurations/Cancel`
*   **批次 - 延遲**:
    *   `PUT /api/StatusConfigurations/Delay`




