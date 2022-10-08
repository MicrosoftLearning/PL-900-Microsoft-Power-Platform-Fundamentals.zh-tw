---
lab:
  title: '實驗室 1:資料模型'
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# <a name="lab-1-data-modeling"></a>實驗室 1:資料模型

## <a name="scenario"></a>案例

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

校園行政單位想要更新其訪客登記系統，讓保全人員控管各棟大樓的出入狀況，且所有造訪情形都必須由大樓負責人預先登記和記錄。

在整個課程中，您將建立應用程式並執行自動化功能，以便 Bellows College 的行政和保全人員能夠管理及控管校內大樓的出入狀況。

In this lab you will access your environment, create a Microsoft Dataverse database, and create a solution to track your changes. You will also create a data model to support the following requirements:

- R1 – 追蹤預定的校園造訪資訊

- R2：記錄基本資訊以識別並追蹤訪客

- R3：排定、記錄及管理造訪情形

最後，您會將範例資料匯入至 Microsoft Dataverse。

## <a name="high-level-lab-steps"></a>高階實驗室步驟

為準備您的學習環境，您必須：

- Refer to the <bpt id="p1">[</bpt>data model document<ept id="p1">](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png)</ept> for the metadata description (tables and relationships). You can hold CTRL+click or right click the link to open the data model document in a new window.
- 建立 [造訪情形] 資料表
- 使用 Excel 試算表匯入造訪情形資料

## <a name="prerequisites"></a>必要條件

- 完成**單元 0 實驗室 0：驗證實驗室環境**

## <a name="things-to-consider-before-you-begin"></a>開始前要考慮的事項

- 命名慣例 - 小心地鍵入名稱。

## <a name="exercise-1-create-new-table"></a>練習 1：建立新資料表

**目標：** 在此練習中，您將會為造訪情形建立新的自訂資料表。

### <a name="task-1-create-visit-table-and-columns"></a>工作 \#1：建立「造訪情形」資料表和資料行

[造訪情形] 資料表將包含校園造訪情形的相關資訊，包括訪客、每個造訪情形的預定時間和實際時間。

我們想要在造訪簽入程序期間、當系統要求時，為每個造訪情形指派可讓訪客輕鬆輸入和理解的唯一號碼。

> 我們使用**不受時區影響**的行為來記錄日期和時間資訊，因為造訪時間一律使用大樓所在位置的當地時間，且從其他時區檢視時也不應變更。

1. 登入 [https://make.powerapps.com](https://make.powerapps.com/) (若您尚未登入)

1. 如果尚未選取，請在右上方選取您的 [[我的縮寫名] 練習] 環境。

1. 使用左側導覽，展開 [Dataverse]，然後選取 [資料表]。

1. 按一下 [+新增資料表]。

1. 輸入**造訪情形**作為 [顯示名稱]。

1. 按一下 [儲存]。

1. 在 [結構描述] 區段下，選取 [資料行]。

1. 建立「預定開始時間」資料行

    - 選取 [+ 新增資料行]。

    - 輸入**預定開始時間**作為 [顯示名稱]。

    - 選取 [日期和時間] 作為 [資料類型]。

    - 在 [必要項]中，選取 [業務需求]。

    - 展開 [進階選項]。

    - 在 [時區調整]中，選取 [不受時區影響]。

    - 按一下 [檔案]  。

1. 建立「預定結束時間」資料行

    - 按一下 [+ 新增資料行]。

    - 輸入**排定的結束時間**作為 [顯示名稱]。

    - 選取 [日期和時間] 作為 [資料類型]。

    - 在 [必要項]中，選取 [業務需求]。

    - 展開 [進階選項]。

    - 在 [時區調整]中，選取 [不受時區影響]。

    - 按一下 [檔案]  。

1. 建立「實際開始時間」資料行

    - 按一下 [+ 新增資料行]。

    - 輸入**實際開始時間**作為 [顯示名稱]。

    - 選取 [日期和時間] 作為 [資料類型]。

    - 在 [必要項]中，將此項保留為 [選用]。

    - 展開 [進階選項]。

    - 在 [時區調整]中，選取 [不受時區影響]。

    - 按一下 [檔案]  。

1. 建立「實際結束時間」資料行

    - 按一下 [+ 新增資料行]。

    - 輸入**實際結束時間**作為 [顯示名稱]。

    - 選取 [日期和時間] 作為 [資料類型]。

    - 在 **[必要項目]** 中，將此項保留為 **[選用]** 。

    - 展開 [進階選項]。

    - 在 [時區調整]中，選取 [不受時區影響]。

    - 按一下 [檔案]  。

1. 建立「代碼」資料行

    - 按一下 [+ 新增資料行]。

    - 輸入**代碼**作為 [顯示名稱]。

    - 選取 [自動編號] 作為 [資料類型]。

    - 選取 **[日期前置編號]** 做為 **[自動編碼類型]** 。

    - 按一下 [檔案]  。

1. 建立 [訪客] 查詢資料行

    - 按一下 [+ 新增資料行]。

    - 輸入**訪客**作為 [顯示名稱]。

    - 選取 [查詢] 作為 [資料類型]。

    - 選取 [連絡人] 作為 [相關資料表]。

    - 展開 [進階選項]。

    - 在 [關聯性名稱] 中輸入 **visitor_id**。

    - 按一下 [檔案]  。

## <a name="exercise-2-import-data"></a>練習 2：匯入資料

**目標：** 在此練習中，您會將範例資料匯入至 Dataverse 資料庫。

### <a name="task-1-import-the-visitsxlsx-file"></a>工作 \#1：匯入 Visits.xls 檔案

在此工作中，您將會從 Excel 檔案匯入造訪情形資料。

1. You should have the <bpt id="p1">**</bpt>Visits.xlsx<ept id="p1">**</ept> file stored on your Desktop. Download <bpt id="p1">[</bpt>Visits.xlsx<ept id="p1">](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx)</ept> if you do not.

2. 若尚未登入，請登入 [https://make.powerapps.com](https://make.powerapps.com/)。

3. 如果尚未選取，請在右上方選取您的 [[我的縮寫名] 練習] 環境。

4. 使用左側導覽，展開 [Dataverse]，然後選取 [資料表]。

5. 找到並開啟您在上一個練習中建立的 [造訪情形] 資料表。

6. 使用頂端的功能表，在 [匯入] 旁選取下拉式箭頭，然後選取 [從 Excel 匯入資料]。

7. 在隨後出現的功能表中，選取 [上傳] 按鈕。

8. Bellows College 是一個教育組織，校園內有多棟大樓。

9. 按一下 [對應資料行] (請注意，您可能需要向右捲動，才能看到 [對應資料行] 選項)。

10. 請依以下說明來對應資料行：

| 造訪情形資料行| 來源資料行 |
| - | - |
| 實際結束| 實際結束時間 |
| 實際開始| 實際開始時間 |
| 程式碼| code |
| 名称| NAME |
| 計劃結束| 排定結束時間 |
| 排定的開始時間| 排定開始時間 |

11. 將其餘所有欄位保留為 [未設定]。

12. 在畫面右上角，按一下 [儲存變更]。

13. 在 [匯入資料] 畫面中，驗證對應狀態顯示為「對應成功」。

14. 選取右上角的 [匯入] 以完成資料匯入。

校園訪客造訪情況目前記錄在紙本日誌中。

15. 按一下 **X** 以關閉匯入資料面板。

### <a name="task-2-verify-data-import"></a>工作 \#2：確認資料匯入

1. 匯入資料後，請使用畫面左側的瀏覽，再次選取 [瀏覽] 資料表。

2. 確認您在 [Visit columns and data] (造訪資料行和資料) 區段下看到匯入的資料。

恭喜，您已順利建立了新資料表並匯入資料。