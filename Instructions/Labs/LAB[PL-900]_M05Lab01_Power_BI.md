---
lab:
  title: 實驗室 5：如何建立簡單的儀表板
  module: 'Module 5: Get Started with Power BI'
---

## <a name="lab-5-how-to-build-a-simple-dashboard"></a>實驗室 5：如何建立簡單的儀表板

## <a name="scenario"></a>案例

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

校園行政單位想要更新其訪客登記系統，讓保全人員控管各棟大樓的出入狀況，且所有造訪情形都必須由大樓負責人預先登記和記錄。

在整個課程中，您將建立應用程式並執行自動化功能，以便 Bellows College 的行政和保全人員能夠管理及控管校內大樓的出入狀況。

在此實驗室中，您將建立可視覺化校園造訪情形相關資料的 Power BI 報表和儀表板。

## <a name="high-level-lab-steps"></a>高階實驗室步驟

我們將依照下列步驟設計和建立 Power BI 儀表板：

-   建立含有校園造訪情形資訊之各種視覺效果的報告

-   利用使用者自然語言建立其他視覺效果

## <a name="prerequisites"></a>必要條件

- 完成**單元 0 實驗室 0：驗證實驗室環境**
- 完成**課程模組 2 實驗室 1 - 資料模型化**

## <a name="things-to-consider-before-you-begin"></a>開始前要考慮的事項

-   誰是報告的目標對象？
-   How will the audience consume the report? Typical device? Location?
-   您是否有足夠的資料可以視覺化？
-   您可以用於分析造訪情形相關資料的可能特性有哪些？

## <a name="exercise-1-create-power-bi-report"></a>練習 1：建立 Power BI 報告

**目標：** 在此練習中，您會根據我們在上一個練習中運用的 Excel 試算表資料，建立 Power BI 報表。

### <a name="task-1-prepare-power-bi-service"></a>工作 \#1：Power BI 服務的準備工作

1.  下載 [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) 並儲存在您的電腦上。

2.  視需要瀏覽至 <https://app.powerbi.com/> 並登入。

3.  在畫面左下角，選取 [取得資料]。

4.  在 [建立新內容] 區段中，選取 [檔案] 底下的 [取得] 按鈕。

5.  選取 [本機檔案]****。

6.  找到並選取您之前下載的 **visits.pbix** 檔案。

7.  資料載入完成後，請展開 [我的工作區] 選取**造訪情形**報告 (請注意，該[類型] 已設定為 [報告])。

8.  Click <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>. If <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept> menu item is not visible click <bpt id="p2">**</bpt>...<ept id="p2">**</ept> and then select <bpt id="p3">**</bpt>Edit<ept id="p3">**</ept>.

您現在已設定好 Power BI 服務並可用於實驗室中。

### <a name="task-2-create-chart-and-time-visualizations"></a>工作 \#2：建立圖表和時間視覺效果

1.  按 [視覺效果] 面板中的 [圓形圖] 圖示以插入圖表。

2.  Press the drop-down arrow beside <bpt id="p1">**</bpt>bc_building<ept id="p1">**</ept> in the Fields pane. Drag the <bpt id="p1">**</bpt>Building<ept id="p1">**</ept> field and drop it into <bpt id="p2">**</bpt>Legend<ept id="p2">**</ept> box.

3.  Bellows College 是一個教育組織，校園內有多棟大樓。

4.  使用角落控點調整圓形圖大小，以便看到所有圖表元件。

5.  按一下圓形圖外部的報告以取消選取，然後在 **[視覺效果]** 窗格中選取堆疊直條圖。

6.  校園訪客目前記錄在紙本日誌中。

7.  拖曳 [開始時間] 欄位，然後將其拖放至 [X 軸] 目標方塊中。

8.  在 [視覺效果] 窗格中，按一下 [年] 和 [季] 旁邊的 **x**，僅保留 [軸] 的 [月] 和 **[日]** 總計。

9.  視需要使用角落控點調整圖表大小。

10. 測試報告互動功能：

    1.  按一下圓形圖上不同的大樓圖塊，並觀察時間報告的變化。

    2.  此資訊並未以一致的方式擷取，而且也無法收集和分析整個校園造訪情形的相關資料。

    3.  向上及向下鑽研，然後選取時間直條圖上的不同直條以觀察圓形圖報告的變化。

11. 按 [儲存] 以儲存行中的工作。

## <a name="exercise-2-create-power-bi-dashboard"></a>練習 2：建立 Power BI 儀表板

### <a name="task-1-create-power-bi-dashboard"></a>工作 \#1：建立 Power BI 儀表板

1.  您應該透過上一個工作將報告保持開啟狀態。

2.  Select <bpt id="p1">**</bpt>Pin to a dashboard<ept id="p1">**</ept> on the menu. Depending on the layout you may need to press <bpt id="p1">**</bpt>...<ept id="p1">**</ept> to show additional menu items.

3.  在 **[釘選到儀表板]** 提示出現時，選取 **[新的儀表板]** 。

4.  輸入 [校園管理] 做為 [儀表板名稱]，然後按下 [動態釘選]。

5.  A pop-up will prompt you that the dashboard has been created. Select <bpt id="p1">**</bpt>Go to dashboard<ept id="p1">**</ept>.

6.  測試顯示之圓形圖和長條圖的互動功能。

### <a name="task-2-add-visualizations-using-natural-language"></a>工作 \#2：使用自然語言新增視覺效果

1.  在 **[校園管理]** 儀表板中，選取位於頂端的 **[詢問有關資料的問題]** 列。

2.  Enter <bpt id="p1">**</bpt>buildings by number of visits<ept id="p1">**</ept> in Q&amp;A area. A bar chart will be displayed.

3.  選取 **[釘選視覺效果]** 。

4.  選取 [現有儀表板]，選取您的 [校園管理] 儀表板，按下 [釘選]。

5.  按一下 **[結束問與答]** 。

Your <bpt id="p1">**</bpt>Campus Management<ept id="p1">**</ept> dashboard should be displayed with three visuals on it. You may have to scroll down to see the new Q&amp;A visual.

您的儀表板看起來應類似於下圖：

![](media/5-powerbi-result.png)