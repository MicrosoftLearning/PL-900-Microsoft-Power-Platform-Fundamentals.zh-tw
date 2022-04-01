---
lab:
  title: 實驗 7：如何建立簡單的儀表板
  module: 'Module 5: Get Started with Power BI'
ms.openlocfilehash: 5381acb81a59a46f6eb6aca9f2bde18de9846473
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/27/2022
ms.locfileid: "137898852"
---
# <a name="module-5-get-started-with-power-bi"></a>課程模組 5：開始使用 Power BI
## <a name="lab-how-to-build-a-simple-dashboard"></a>實驗室：如何建立簡單的儀表板

# <a name="scenario"></a>案例

Bellows College 是一個教育組織，校園內有多棟大樓。 校園訪客目前記錄在紙本日誌中。 此資訊並未以一致的方式擷取，而且也無法收集和分析整個校園造訪情形的相關資料。 

校園行政單位想要更新其訪客登記系統，讓保全人員控管各棟大樓的出入狀況，且所有造訪情形都必須由大樓負責人預先登記和記錄。

在整個課程中，您將建立應用程式並執行自動化功能，以便 Bellows College 的行政和保全人員能夠管理及控管校內大樓的出入狀況。 

在此實驗室中，您將建立可視覺化校園造訪情形相關資料的 Power BI 儀表板。

# <a name="high-level-lab-steps"></a>高階實驗室步驟

我們將依照下列步驟設計和建立 Power BI 儀表板：

-   連接至 Dataverse
-   轉換資料以包含相關資料列 (查詢) 的易用描述
-   建立並發佈含有校園造訪情形資訊之各種視覺效果的報告
-   利用使用者自然語言建立其他視覺效果
-   建立 Power BI 儀表板的行動裝置檢視


## <a name="prerequisites"></a>必要條件

* 完成 **單元 0 實驗室 0：驗證實驗室環境**
* 完成 **單元 2 實驗室 1：Microsoft Dataverse 簡介**

## <a name="things-to-consider-before-you-begin"></a>開始前要考慮的事項

-   誰是報告的目標對象？
-   這些對象會如何使用報告？ 一般裝置？ 位置？
-   您是否有足夠的資料可以視覺化？
-   您可以用於分析造訪情形相關資料的可能特性有哪些？

# <a name="exercise-1-create-power-bi-report"></a>練習 1：建立 Power BI 報告 

**目標：** 在此練習中，您將根據 Dataverse 資料庫的資料建立 Power BI 報告。

## <a name="task-1-install-power-bi-desktop--prepare-power-bi-service"></a>工作 1：安裝 Power BI Desktop/準備 Power BI 服務

1. 依照下列指示設定 Power BI： 

    - 如果 **已經** 安裝了 Power BI Desktop，請直接跳到[工作 2](#task-2-prepare-data)。
    
    - 如果您尚未安裝 Power BI Desktop，請完成 **步驟 2**。
    
    - 如果您不具必要權限或在執行 Power BI Desktop 時遇到問題，請繼續執行 **步驟 4**。

2. 瀏覽至 [https://aka.ms/pbidesktopstore](https://aka.ms/pbidesktopstore) 下載 Power BI Desktop，並進行安裝。

    > [!IMPORTANT]
    > 如果在使用 Microsoft Store 安裝 Power BI Desktop 時遇到問題，請嘗試獨立式安裝程式，下載網址為：[https://aka.ms/pbiSingleInstaller](https://aka.ms/pbiSingleInstaller)。

3. 如果已成功安裝 Power BI Desktop，現在即可直接跳到[工作 2](#task-2-prepare-data)；否則請繼續執行下一個步驟。

    > 如果您不具必要權限或在執行或設定 Power BI Desktop 時遇到問題，請完成下列工作步驟。

4. 下載 [visits.pbix](../../Allfiles/visits.pbix) 並儲存在您的電腦上。

5. 瀏覽至 [https://app.powerbi.com/](https://app.powerbi.com/)，然後按一下 [登入]。 

6. 按一下 **[我的工作區]** 。 

7. 如果出現 **[取得資料]** 頁面，請按一下 **[略過]** 。 

8. 展開 **[+ 新增]** 並選取 **[上傳檔案]** 。

    > [!IMPORTANT]
    > 如果您沒有看到 **[+ 新增]** ，則可能需要啟動 Power BI 的新外觀。 請務必在畫面頂端將 **[新外觀]** 切換為 **[開啟]** 。

9. 選取 [本機檔案]。

10. 找到並選取您之前下載的 **visits.pbix** 檔案。

11. 資料載入完成後，請選取 [瀏覽次數] 報告 (請注意，該[類型] 已設定為 [報告])。

12. 按一下 **[編輯]** 。 如果未出現 [編輯] 功能表項目，請按一下 [...]，然後選取 [編輯]。

13. 您現在已設定好 Power BI 服務並可用於實驗室中。 繼續執行[工作 3](#task-3-create-chart-and-time-visualizations)，但在整個實驗過程中，使用線上 Power BI 服務 (網址為：[https://app.powerbi.com](https://app.powerbi.com))，而不要使用 Power BI Desktop。

## <a name="task-2-prepare-data"></a>工作 2：準備資料

1.  尋找您的組織 URL

    * 在新的索引標籤中，瀏覽至 Power Platform 系統管理中心，網址為 <https://admin.powerplatform.com>
    
    * 在左側導覽頁面中選取 [環境]，然後開啟您的 [練習] 環境。
    
    * 在 **[詳細資料]** 面板上以滑鼠右鍵按一下 **[環境 URL]** ，然後選取 **[複製連結位址]** 。
    
2. 開啟 Power BI Desktop，並在出現提示時使用提供的認證登入。

3. 選取 [取得資料]，然後選取 [更多...]。

4. 選取左側的 [Power Platform]，然後選取 [Common Data Service (舊版)]，然後按一下 [連線]。 如果出現提示，請使用您提供的認證登入，然後按一下 [連線]。

5. 將您之前複製的環境 URL 貼到 **[伺服器 URL]** 欄位中，然後按下 **[確定]** 。

6. 展開 **[實體]** 節點，選取 **[bc_Building]** 和 **[bc_Visit]** 實體，然後按一下 **[載入]** 。

7. 在左側垂直工具列上按一下 **[模型]** 圖示。

8. 拖曳 **bc_Building** 資料表的 **bc_buildingid** 資料行，然後將其拖放至 **bc_Visit** 資料表的 **bc_building** 資料行。 這會在兩個資料表之間建立關聯性，Power BI 將可藉此顯示相關資料。

9. 在左側工具列上選取 **[報告]** 圖示。

10. 在 **[欄位]** 面板中展開 **bc_Visit** 節點。

11. 按一下 [bc_Visit] 旁的 [...]，然後選取 [新增資料行]。

12. 完成下列公式：

    ```
    Column = RELATED(bc_Building[bc_name])
    ```

    然後按下 Enter。 此步驟會在造訪情形資料中新增具有大樓名稱的新欄位。

13. 按一下剛剛建立的 [資料行] 欄位旁的 [...]，然後選取 [重新命名]。 輸入 **大樓** 做為欄位名稱。

14. 按一下 [bc_visitid] 欄位旁的 [...]，然後選取 [重新命名]。 輸入 **造訪情形** 做為欄位名稱。

15. 按一下 [bc_scheduledstart] 欄位旁的 [...]，然後選取 [重新命名]。 輸入 **開始時間** 做為欄位名稱。

16. 按下 [檔案] \| [儲存]，然後輸入您選擇的檔案名，將進行中的工作儲存起來。

## <a name="task-3-create-chart-and-time-visualizations"></a>工作 3：建立圖表和時間視覺效果

1. 按下 **[視覺效果]** 面板中的圓形圖圖示以插入圖表。

2. 拖曳 **[大樓]** 欄位，然後將其拖放至 **[圖例]** 方塊中。

3. 拖曳 **[造訪情形]** 欄位，然後將其拖放至 **[值]** 目標方塊。

4. 使用角落控點調整圓形圖大小，以便看到所有圖表元件。

5. 按一下圓形圖外部的報告以取消選取，然後在 **[視覺效果]** 窗格中選取堆疊直條圖。 

6. 拖曳 **[造訪情形]** 欄位，然後將其拖放至 **[值]** 目標方塊中。

7. 拖曳 **[開始時間]** 欄位，然後將其拖放至 **[軸]** 目標方塊中。

8. 在 [視覺效果] 窗格中，按一下 **[日]** 和 **[季]** 旁邊的 **[x]** ，以便僅保留 [軸] 的 **[年]** 和 **[月]** 總數。

9. 視需要使用角落控點調整圖表大小。

10. 測試報告互動功能：

    * 選取圓形圖上不同的大樓圖塊，並觀察時間報告的變化。
    
    * 按一下直條圖。 按向下鍵以開啟 **[向下鑽研]** 模式，然後按一下直條圖以向下鑽研至下一個層級 (月)。 另一種方式是按一下功能區上的 [資料] / [鑽研] \| [展開下一層級]。
    
    * 向上及向下鑽研，然後選取時間直條圖上的不同直條以觀察圓形圖報告的變化。
    
11. 按下 [檔案] \| [儲存]。

# <a name="exercise-2-create-power-bi-dashboard"></a>練習 2：建立 Power BI 儀表板

## <a name="task-1-publish-power-bi-report"></a>工作 1：發佈 Power BI 報告

1. 按下功能區 [常用] 索引標籤上的 **[發佈]** 按鈕。

2. 選取 **[我的工作區]** 做為目的地，然後按下 **[選取]** 。

3. 等待發佈完成，然後按一下 [在 Power BI 中開啟 \<name of your report\>.pbix]。

## <a name="task-2-create-power-bi-dashboard"></a>工作 2：建立 Power BI 儀表板

1. 您應該透過上一個工作將報告保持開啟狀態。

2. 選取功能表上的 **[釘選到儀表板]** 。 視版面配置之不同，可能需要按 [...] 才會顯示其他功能表項目。

3. 在 **[釘選到儀表板]** 提示出現時，選取 **[新的儀表板]** 。

4. 輸入 **[您的姓氏] 校園管理** 做為 **[儀表板名稱]** ，然後按下 **[動態釘選]** 。

5. 選取位於頂端的 **[我的工作區]** ，然後選取 **[(您的姓氏) 校園管理]** 儀表板。

6. 測試顯示之圓形圖和長條圖的互動功能。

## <a name="task-3-add-visualizations-using-natural-language"></a>工作 3：使用自然語言新增視覺效果

1. 在 **[校園管理]** 儀表板中，選取位於頂端的 **[詢問有關資料的問題]** 列。

2. 在 [問與答] 區域中輸入 **依造訪情形的數量顯示大樓**。 系統將會顯示長條圖。

3. 選取 **[釘選視覺效果]** 。

4. 選取 **[現有儀表板]** ，然後選取 **[(您的姓氏) 校園管理]** 儀表板並按下 **[釘選]** 。

5. 按一下 **[結束問與答]** 。

此時應該會顯示您的 **[(您的姓氏) 校園管理]** 儀表板。 您可能需要向下捲動才能看到新的問與答視覺效果。 

您的儀表板看起來應類似於下圖：

![Power BI 儀表板](media/5-powerbi-result.png)

## <a name="task-4-build-mobile-phone-view-and-share-a-report-with-a-qr-code"></a>工作 4：建立行動電話檢視及透過 QR 代碼分享報告

1. 從儀表板中選取 [編輯] \| [行動裝置版面配置]。

2. 視需要重新排列區塊。

3. 按一下右上方的 [行動裝置版面配置]，並將 [檢視] 變更為 [Web 版面配置]。

4. 選取位於頂端的 **[我的工作區]** ，然後選取您的 **報告**。

5. 選取 [編輯]，然後選取 [...]\| [產生 QR 代碼]。

6. *選擇性：* 如果您有行動裝置，請使用 iOS 和 Android 平台上可用的 QR 掃描應用程式或相機應用程式 (若您的手機有支援) 掃描代碼。 出現提示時，請登入您的帳戶。 在行動裝置上導覽並探索報告。

# <a name="challenges"></a>挑戰

* 在儀表板和報告中納入您的校園和大樓計畫
* 報告和分析造訪模式和趨勢
* 停留逾時情形的視覺效果
* 針對大型校園串流 Power BI，以實現近乎即時的處理程序 
