---
title: 使用 Web 擴充任務窗格
linktitle: 使用 Web 擴充任務窗格
second_title: Aspose.Words 文件處理 API
description: 將 Web 擴充任務窗格與 Aspose.Words for .NET 結合使用的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-webextension/using-web-extension-task-panes/
---

本文提供了有關如何將 Web 擴充任務窗格與 Aspose.Words for .NET 結合使用的逐步指南。我們將詳細解釋程式碼的每一部分。在本教學結束時，您將能夠了解如何新增和設定 Web 擴充功能的任務窗格。

在開始之前，請確保您已在專案中安裝並設定了 Aspose.Words for .NET 程式庫。您可以在 Aspose 網站上找到庫和安裝說明。

## 步驟1：定義文檔目錄

首先，您需要定義要儲存產生文件的目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 2：建立並設定任務窗格

我們創建一個`TaskPane`物件並將其添加到文件中`s `WebExtensionTaskPanes` 集合。接下來，我們配置任務窗格的屬性，例如其停靠狀態、可見度和寬度。

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

我們也設定了 Web 擴充憑證，包括目錄 ID、版本和商店類型。

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

最後，我們為 Web 擴充功能新增屬性和綁定。

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## 步驟 3：儲存並載入文檔

我們將文件與在指定目錄中配置的任務窗格一起儲存。

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## 步驟 4：顯示任務窗格訊息

接下來，我們載入文件並顯示任務窗格來源資訊。

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

就這樣 ！您已成功將 Web 擴充任務窗格與 Aspose.Words for .NET 結合使用。

### 將 Web 擴充任務窗格與 Aspose.Words for .NET 結合使用的範例原始程式碼


```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	TaskPane taskPane = new TaskPane();
	doc.WebExtensionTaskPanes.Add(taskPane);

	taskPane.DockState = TaskPaneDockState.Right;
	taskPane.IsVisible = true;
	taskPane.Width = 300;

	taskPane.WebExtension.Reference.Id = "wa102923726";
	taskPane.WebExtension.Reference.Version = "1.0.0.0";
	taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
	taskPane.WebExtension.Reference.Store = "th-TH";
	taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
	taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
		WebExtensionBindingType.Text, "194740422"));

	doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
	
	
	
	doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
	
	Console.WriteLine("Task panes sources:\n");

	foreach (TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
	{
		WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;
		Console.WriteLine($"Provider: \"{reference.Store}\", version: \"{reference.Version}\", catalog identifier: \"{reference.Id}\";");
	}
 
```
