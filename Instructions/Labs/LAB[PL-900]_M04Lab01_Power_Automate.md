---
lab:
  title: '實驗室 4:如何建立自動化解決方案'
  module: 'Module 4: Get Started with Power Automate'
---

# <a name="lab-4-how-to-build-an-automated-solution"></a>實驗室 4:如何建立自動化解決方案

## <a name="scenario"></a>案例

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

校園行政單位想要更新其訪客登記系統，讓保全人員控管各棟大樓的出入狀況，且所有造訪情形都必須由大樓負責人預先登記和記錄。

在整個課程中，您將建立應用程式並執行自動化功能，以便 Bellows College 的行政和保全人員能夠管理及控管校內大樓的出入狀況。

在此實驗室中，您將建立 Power Automate 流程，在排程造訪時傳送電子郵件給訪客。

## <a name="high-level-lab-steps"></a>高階實驗室步驟

您必須實作下列需求才能完成專案：

- 排程造訪時，必須透過電子郵件通知連絡人。

## <a name="prerequisites"></a>必要條件

- 完成**單元 0 實驗室 0：驗證實驗室環境**
- 完成**課程模組 2 實驗室 1 - 資料模型化**
- 完成**課程模組 2 實驗室 3 完成 - 如何建置模型驅動應用程式**
- 已建立填入個人電子郵件地址的連絡人 John Doe

## <a name="exercise-1-create-visit-notification-flow"></a>練習 1：建立造訪通知流程

<bpt id="p1">**</bpt>Objective:<ept id="p1">**</ept> In this exercise, you will create a Power Automate flow that implements the requirement. The visitor should be sent an email that includes the unique code assigned to the visit when a visit is created.

### <a name="task-1-create-a-flow"></a>工作 \#1：建立流程

1.  Navigate to <ph id="ph1">&lt;https://make.powerapps.com&gt;</ph>. You may need to reauthenticate - click <bpt id="p1">**</bpt>Sign in<ept id="p1">**</ept> and follow instructions if needed.

2.  如果尚未選取，請在右上方選取您的 [[我的縮寫名] 練習] 環境。

3.  在左側導覽中，選取 [流程]。

4.  如果出現提示，請選取 [開始]。

5.  按一下 [新增流程]，然後選取 [自動化雲端流程]。

6.  在 [流程名稱] 中輸入 "Visit Notification"。

7.  在 [選擇流程的觸發程序] 中，搜尋 **Dataverse**。

8.  選取觸發程序 [When a row is added, modified or deleted] (當有資料列新增、修改或刪除時)，然後按一下 [建立]。

9.  填入流程的觸發條件：

    1.  為 [變更類型] 選取 [已新增]

    2.  選取 **[造訪情形]** 做為 **[資料表名稱]**

    3.  選取 **[組織]** 做為 **[範圍]**

    4.  On the trigger step, click the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and click <bpt id="p2">**</bpt>Rename<ept id="p2">**</ept>. Rename this trigger <bpt id="p1">**</bpt>"When a visit is added"<ept id="p1">**</ept>. This is a good practice, so you and other flow editors can understand the purpose of the step without having to dive into the details.

### <a name="task-2-create-a-step-to-get-the-visitor-row"></a>工作 \#2：建立用以取得訪客資料列的步驟

1.  Bellows College 是一個教育組織，校園內有多棟大樓。

2.  搜尋 **Dataverse**。

3.  選取 [依識別碼取得資料列] 動作。

4.  選取 **[連絡人]** 做為 **[資料表名稱]**

5.  校園訪客目前記錄在紙本日誌中。

6.  此資訊並未以一致的方式擷取，而且也無法收集和分析整個校園造訪情形的相關資料。

7.  On this action, click the ellipsis (<bpt id="p1">**</bpt>...<ept id="p1">**</ept>) and click <bpt id="p2">**</bpt>Rename<ept id="p2">**</ept>.
        Rename this action <bpt id="p1">**</bpt>"Get the Visitor"<ept id="p1">**</ept>. This is a good practice, so you and other flow editors can understand the purpose of the step without having to dive into the details.

### <a name="task-3-create-a-step-to-send-an-email-to-the-visitor"></a>工作 \#3：建立用以將電子郵件傳送給訪客的步驟

1.  Click <bpt id="p1">**</bpt>+ New step<ept id="p1">**</ept>. This is the step that will send an email to the visitor.

2.  搜尋*郵件*，再依序選取 [Office 365 Outlook]連接器及 [傳送電子郵件 (V2)] 動作。

3.  如果系統要求您接受使用此動作的條款及條件，請按一下 [接受]。

4.  選取 [收件人] 欄位底下的 [新增動態內容]。 
    
5.  從動態內容清單中選取 [電子郵件]。
        > Notice that it is beneath the **Get the visitor** header. This means you
        are selecting the Email that is related to the Visitor that you looked
        up in the previous step.

6.  在 **[主旨]** 欄位中輸入**您的 Bellows College 預定造訪行程**。

7.  在 **[電子郵件本文]** 中輸入下列文字：

>   Dynamic content needs to be placed where fields are named in brackets. It is recommended to copy &amp; paste all text first and then add dynamic content in the correct places.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   Dear {First Name},

   You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

   Best regards,

   Campus Administration
   Bellows College
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  Highlight the <bpt id="p1">**</bpt>{First Name}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>First Name<ept id="p1">**</ept> field from the <bpt id="p2">**</bpt>Get the Visitor<ept id="p2">**</ept> step.

9.  Highlight the <bpt id="p1">**</bpt>{Scheduled Start}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>Scheduled Start<ept id="p1">**</ept> field <bpt id="p2">**</bpt>When a visit is added<ept id="p2">**</ept> step.

10.  Highlight the <bpt id="p1">**</bpt>{Scheduled End}<ept id="p1">**</ept> text. Replace it with the <bpt id="p1">**</bpt>Scheduled End<ept id="p1">**</ept> field from the <bpt id="p2">**</bpt>When a visit is added<ept id="p2">**</ept> step.

11.  按一下 [儲存]。

Leave this flow tab open for the next task. You flow should look approximately like the following:

![流程步驟的範例。](media/4-Flow.png)

### <a name="task-4-validate-and-test-the-flow"></a>工作 4\#：驗證並測試流程

1.  在瀏覽器中開啟新的索引標籤，並巡覽至 <https://make.powerapps.com>。

2.  如果尚未選取，請在右上方選取您的 [[我的縮寫名] 練習] 環境。

3.  按一下 [應用程式]，然後選取您先前建立的 [Bellows 校園管理] 模型驅動應用程式。

3.  保持此瀏覽器索引標籤處於開啟狀態，然後導覽回之前的流程索引標籤。

4.  On the command bar, click <bpt id="p1">**</bpt>Test<ept id="p1">**</ept>. Select <bpt id="p1">**</bpt>Manually<ept id="p1">**</ept> and then click <bpt id="p2">**</bpt>Test<ept id="p2">**</ept>.

5.  保持模型驅動應用程式開啟，並巡覽至瀏覽器索引標籤。 

6.  使用左側的導覽，選取 [造訪]。

6. 按 [+ 新增] 按鈕以新增 [造訪] 記錄。

7. 完成造訪記錄，如下所示：

    -   **名稱：** 測試造訪

    -   **訪客：** John Doe

    -   **排定開始時間：** 明天上午 8:00

    -   **排定結束時間：** 明天上午 9:00

8. 選取**儲存後關閉**按鈕。

9. Navigate to the browser tab with your flow test running. After a short delay, you should see the flow running. This is where you can catch any issues in the flow or confirm that it ran successfully.

After a short delay, you should see an email in your inbox, since you populated John Doe's email as your personal email. Note that it may go to your Junk Email folder.

## <a name="challenges"></a>挑戰

- Play around with the formatting on the email. How can you make it more professional looking?