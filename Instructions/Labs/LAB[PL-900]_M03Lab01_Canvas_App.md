---
lab:
  title: 實驗室 2：如何建置畫布應用程式
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: 24d99d14079d40f74a43ed0de64dd6ae5d7046c7
ms.sourcegitcommit: 0118c25a230425d0ccba16e6c3922053ee07c183
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2022
ms.locfileid: "144810917"
---
# <a name="module-3-get-started-with-power-apps"></a>模組 3：開始使用 Power Apps
## <a name="lab-how-to-build-a-canvas-app"></a>實驗室：如何建置畫布應用程式

# <a name="scenario"></a>案例

Bellows College 是一個教育組織，校園內有多棟大樓。 校園訪客造訪情況目前記錄在紙本日誌中。 此資訊並未以一致的方式擷取，而且也無法收集和分析整個校園造訪情形的相關資料。

目前，校園行政單位利用 Excel 試算表來追蹤訪客登記。 他們想要更新其訪客登記系統，讓保全人員控管各棟大樓的出入狀況，且所有造訪情形都必須由大樓負責人預先登記和記錄。

在整個課程中，您將建立應用程式並執行自動化功能，以便 Bellows College 的行政和保全人員能夠管理及控管校內大樓的出入狀況。

# <a name="high-level-lab-steps"></a>高階實驗室步驟

我們將依照以下大綱設計畫布應用程式：

-   從 [造訪] 資料表中的資料建立畫布應用程式

-   設定造訪在瀏覽畫面上的顯示方式

-   對應用程式進行一些基本變更

-   測試應用程式功能

## <a name="prerequisites"></a>必要條件

-   完成 **單元 0 實驗室 0：驗證實驗室環境**

# <a name="exercise-1-create-visits-app"></a>練習 \#1：建立造訪應用程式

**目標：** 在此練習中，您將連線您稍早建立的「造訪縮寫」資料表，以建立畫布應用程式。

## <a name="task-1-create-a-visits-app"></a>工作 \#1：建立造訪應用程式

1.  瀏覽至 <https://make.powerapps.com>。 您可能需要重新驗證：如有需要，請按一下 **[登入]** ，然後依照指示操作。

2.  如果尚未選取，請在右上方選取您的 [[我的縮寫名] 練習] 環境。

3.  如有必要，按一下畫面左側的 **首頁** 圖示。 在 [起始] 區段底下，選取 [Dataverse]。

4.  選取您的 Dataverse 連線。 

    >   **注意：** *如果 Dataverse 連線不存在：*
    >   -   選取 [新增連線]
    >   -   找出 [Microsoft Dataverse]
    >   -   按一下 [建立] 

5.  找出並選取您在上一個實驗室中建立的 [造訪] 資料表。

6.  選取右下角的 [連線] 按鈕。

7.  建立您的應用程式之後，在 [歡迎使用 Power Apps Studio] 畫面上，勾選 [不要再顯示] 方塊，然後選取 [略過]。

8.  建立完成後，看起來應該像下圖。

![從造訪資料建立的畫布應用程式。](media/2-canvas-app-from-data.png)

9. 在應用程式設計工具中，選取命令列上的 [預覽您的應用程式] 按鈕 ([播放] 圖示)。 *(您也可以在鍵盤上按 F5 來預覽應用程式。)* 查看一下，了解應用程式成品的運作方式。

10. 選取畫面右上角的 [X] 關閉應用程式預覽。

恭喜，您已成功從 Dataverse 資料表建立 Power App。 程序中的下一個步驟是量身打造應用程式，以符合您大學的品牌。 下一系列的步驟將逐步引導您提供一些額外的自訂給應用程式。

## <a name="task-2-modify-and-theme-the-newly-created-app"></a>工作 \#2：修改新建立的應用程式並設定其主題

在此工作中，您將會為您應用程式的三個畫面 (瀏覽、詳細資料和編輯) 自訂標題文字，以及變更應用程式主題。

1.  您在 [瀏覽] 畫面上。 選取畫面上的 [造訪情形] 標籤。

3.  在畫面右側的 [屬性] 索引標籤下，將 [文字] 控制項屬性更新為「Bellows College 造訪情形」。

4. 在屬性中，將 [字型大小] 變更為 **24**。

4.  按一下空白背景，以在您的 [瀏覽] 畫面上查看更新的文字。

5.  使用左側的巡覽功能，選取 **DetailScreen1**。

5.  選取畫面上的 [造訪情形] 標籤。

6.  在畫面右側的 [屬性] 索引標籤下，將 [文字] 控制項屬性更新為「檢視詳細資料」。

7.  按一下空白背景，以在您的 [詳細資料] 畫面上查看更新的文字。

8.  使用左側的巡覽功能，選取 **EditScreen1**，您可能需要向下捲動才能在樹狀檢視上查看此項目。

9.  選取畫面上的 [造訪情形] 標籤。

10.  在畫面右側的 [屬性] 索引標籤下，將 [文字] 控制項屬性中的 Table1 文字取代為「檢視詳細資料」。

11.  按一下空白背景，以在您的 [編輯] 畫面上查看更新的文字。

12. 使用左側的導覽，選取 [BrowseScreen1]。

13. 在命令工具列上，選取 [主題] 按鈕，然後從出現的清單中選取 [紅色] 主題色彩。

## <a name="task-3-test-your-visits-app"></a>工作 \#3：測試您的造訪應用程式

在此工作中，您將會測試您的新應用程式。

1.  在應用程式設計工具中開啟應用程式後，選取 [檔案]，將應用程式的名稱更新為 [造訪應用程式]，然後選取 [儲存]。

2.  選取 [返回] 箭號回到您的應用程式。

3.  使用左側的巡覽功能，選取 **BrowseScreen1**。

4.  在應用程式設計工具中，選取命令列上的 [預覽您的應用程式] 按鈕 ([播放] 圖示)。 *(您也可以在鍵盤上按 F5 來預覽應用程式。)*

4.  應用程式開啟後，在 [搜尋項目] 欄位中，輸入文字 **Maria**
     *(注意資源庫中的項目如何根據搜尋欄位中輸入的內容進行篩選)。*

5.  **Maria Campbell** 的 **Contoso Suites** 記錄顯示後，按一下資料列以巡覽來開啟該造訪的詳細資料。 (**注意**：*如果顯示多個 Contoso 套件 Maria Campbell 記錄，請選取其中任何一筆記錄*)

6.  若要編輯記錄，請選取應用程式右上角的 [鉛筆圖示]。

7.  您可以在此編輯造訪名稱，並按一下右上角的核取記號來儲存變更。

8.  按一下畫面右上角的 [X] 圖示返回畫布應用程式編輯器。

恭喜！ 您已建立並設定第一個畫布應用程式。

# <a name="challenges"></a>挑戰

-   將下列資料行新增至 DetailScreen1 和 EditScreen1 中的表單：實際開始時間、實際結束時間、代碼、排定開始時間和排定結束時間
