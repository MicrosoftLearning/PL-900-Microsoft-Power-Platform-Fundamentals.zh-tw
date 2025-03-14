---
lab:
  title: 實驗室 5：如何建立簡單的儀表板
  module: 'Module 5: Describe the capabilities of Microsoft Power BI'
---

## 實驗室 5：如何建立簡單的儀表板

**WWL 租用戶 - 使用條款**如果您針對講師導向訓練交付的一部分取得租用戶，請注意，租用戶的功能是為了在講師導向訓練中支援實際操作實驗室。 租用戶不應共用，或用於實際操作實驗室以外的用途。 本課程中使用的租用戶是試用租用戶，在課程結束後無法使用或存取租用戶，且不符合延伸模組的資格。 租用戶不得轉換成付費訂用帳戶。 此課程中提供的租用戶仍是 Microsoft Corporation 的財產，我們保留隨時取得存取權和重新持有的權利。 

## 案例

Bellows College 是一個教育組織，校園內有多棟大樓。 校園訪客目前記錄在紙本日誌中。 此資訊並未以一致的方式擷取，而且也無法收集和分析整個校園造訪的相關資料。

校園行政單位想要更新其訪客登記系統，讓保全人員控管各棟大樓的出入狀況，且所有造訪都必須由大樓負責人預先登記和記錄。

在此實驗室中，您將建立可視覺化校園造訪相關資料的 Power BI 報表和儀表板。

**高階實驗室步驟**

我們將依照下列步驟設計和建立 Power BI 儀表板：

- 建立含有校園造訪資訊之各種視覺效果的報告

- 利用使用者自然語言建立其他視覺效果

### 必要條件

- 完成**單元 1 實驗室 0 - 驗證實驗室環境**

**開始前要考慮的事項**

- 誰是報告的目標對象？

- 這些對象會如何使用報告？ 一般裝置？ 位置？

- 您是否有足夠的資料可以視覺化？

- 您可以用於分析造訪相關資料的可能特性有哪些？

## 練習 #1：建立 Power BI 報告

**目標：** 在此練習中，您會根據我們在上一個練習中運用的 Excel 試算表資料，建立 Power BI 報表。

### 工作 #1：Power BI 服務的準備工作

1. 您應該會有一個 visits.pbix 檔案儲存在桌面上 AllFiles 資料夾中的虛擬機器上。 下載 [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) 並儲存到您的電腦，如果尚未存在，請加以儲存。

1. 開啟新的索引標籤，並視需要瀏覽至 `https://app.powerbi.com` 並登入。

1. 從左側導覽中選取 [我的工作區]****。

1. 選取 [上傳]****，然後選取 [瀏覽]****。

1. 找到並選取您之前下載的 **visits.pbix** 檔案。

1. 一旦資料載入完成，請選取 **visit** 報告。

    >**注意：** 類型設定為 **[報表**]，請勿選取語意模型。

1. 選取 [編輯]。

如果未出現 [編輯]**** 功能表項目，請按一下 […]****，然後選取 [編輯****]。

您現在已設定好 Power BI 服務並可用於實驗室中。

### 工作 #2：建立圖表和時間視覺效果

1. 選取 [視覺效果]****  面板中的 [圓形圖]**** 圖示以插入圖表。

1. 在 [**數據**] 窗格中展開**** bc_Visit。 拖曳 [大樓]**** 欄位，然後將其拖放至 [圖例]**** 方塊中。

1. 拖曳 [造訪]**** 欄位，然後將其拖放至 [值] **** 方塊。

1. 使用角落控點調整圓形圖大小，以便看到所有圖表元件。

1. 按一下圓形圖外部的報告以取消選取，然後在 [視覺效果]**** 窗格中選取 [堆疊直條圖]****。

1. 如果尚未展開，請在 [數據] 窗格中展開**bc_Visit****。** 拖曳 [造訪]**** 欄位，然後將其拖放至 [Y 軸]**** 目標方塊中。

1. 拖曳 [開始時間]**** 欄位，然後將其拖放至 [X 軸]**** 目標方塊中。

1. 在 [視覺效果]**** 窗格中，按一下 [年] **** 和 [季]**** 旁邊的 **x**，僅保留 [軸] 的 [月]**** 和 [日]**** 總計。

1. 視需要使用角落控點調整圖表大小。

1. 測試報告互動功能：

    - 在圓形圖上選取不同的建置配量，並觀察堆疊直條圖上的變更。

    - 選取堆疊直條圖。 選取向上箭號，以**向上鑽研**切入。 選取向下鍵以開啟 [向下鑽研]**** 模式，然後選取直條圖以向下鑽研至下一個層級 (日)。

    - 向上及向下鑽研，然後選取堆疊直條圖上的不同直條以觀察圓形圖報告的變化。

1. 選取 [儲存此報表]****，以儲存進行中的工作。

## 練習 2：建立 Power BI 儀表板

### 工作 #1：建立 Power BI 儀表板

1. 您應該透過上一個工作將報告保持開啟狀態。

1. 選取功能表上的 **[釘選到儀表板]** 。 視配置而定，您可能需要選取省略號功能表 [...]**** 以顯示更多選項。

1. 在 **[釘選到儀表板]** 提示出現時，選取 **[新的儀表板]** 。

1. 輸入 `Campus Management` 作為 [儀表板名稱]****，然後選取 [即時釘選]****。

1. 快顯視窗會提示您已建立儀表板。 選取 [移至儀表板]****。

1. 測試顯示之圓形圖和長條圖的互動功能。

### 工作 #2：使用自然語言新增視覺效果

1. 在 **[校園管理]** 儀表板中，選取位於頂端的 **[詢問有關資料的問題]** 列。

1. 在 Q&A 區域中輸入 `buildings by number of visits`。 系統將會顯示長條圖。

1. 選取 **[釘選視覺效果]** 。

1. 選取 [現有儀表板]****，選取您的 [校園管理]**** 儀表板，按下 [釘選]****。

1. 選取 [結束 Q&amp;A]****。

您的 [校園管理]**** 儀表板中應該會顯示三個視覺效果。 您可能需要向下捲動才能看到新的問與答視覺效果。

您的儀表板看起來應類似於下圖：

[![剛剛建立的儀表板的螢幕擷取畫面](media/lab-5-power-bi-01.png)](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Instructions/Labs/media/5-powerbi-result.png)

 
