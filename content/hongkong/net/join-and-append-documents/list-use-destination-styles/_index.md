---
title: 列出使用目標樣式
linktitle: 列出使用目標樣式
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 合併和追加 Word 文檔，同時保留目標文檔的清單樣式。
type: docs
weight: 10
url: /zh-hant/net/join-and-append-documents/list-use-destination-styles/
---

本教學將引導您完成使用 Aspose.Words for .NET 的清單使用目標樣式功能的流程。此功能可讓您在使用目標文件的清單樣式的同時加入和附加 Word 文件。

## 先決條件

在開始之前，請確保您具備以下條件：

1. Aspose.Words for .NET 已安裝。您可以從 Aspose 網站下載它或透過 NuGet 安裝它。
2. Visual Studio 或任何其他 C# 開發環境。

## 第 1 步：初始化文件目錄

首先，您需要設定文檔目錄的路徑。修改值`dataDir`變數到您的文件所在的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入來源文檔和目標文檔

接下來，您需要使用 Aspose.Words 載入來源文件和目標文件。`Document`班級。更新檔名`Document`根據您的文檔名稱建構函數。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 步驟 3：將來源文件設定為在目標文件之後繼續

為了確保來源文件的內容在目標文件結束後繼續，您需要設定`SectionStart`來源文檔中第一部分的屬性`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 第 4 步：處理清單格式

為了處理清單格式，您將遍歷來源文件中的每個段落並檢查它是否為清單項目。如果是，您將將該清單 ID 與目標文件中的現有清單進行比較。如果存在具有相同 ID 的列表，您將在來源文件中建立該列表的副本，並更新段落的列表格式以使用複製的列表。

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## 步驟 5：將來源文檔附加到目標文檔

現在，您可以使用以下命令將來源文檔附加到目標文檔`AppendDocument`的方法`Document`班級。這`ImportFormatMode.UseDestinationStyles`參數可確保在追加操作期間使用目標文件的清單樣式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## 第 6 步：儲存最終文檔

最後，使用啟用的「清單使用目標樣式」功能儲存合併的文檔`Save`的方法`Document`班級。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### 使用 Aspose.Words for .NET 的清單使用目標樣式的範例原始程式碼 

以下是 C# 中使用 Aspose.Words for .NET 的「清單使用目標樣式」功能的完整原始碼：


```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//將來源文件設定為在目標文件結尾後直接繼續。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	//追蹤創建的列表。
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			//檢查目標文件是否已包含具有此 ID 的清單。如果確實如此，那麼這可能
			//使兩個列表一起運行。相反，請在來源文件中建立清單的副本。
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				//該 ID 已存在新複製的列表，檢索儲存的列表，
				//並將其用於當前段落。
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					//將此清單的副本新增至文件中並儲存以供以後參考。
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				//將此段落的清單設定為複製的清單。
				para.ListFormat.List = currentList;
			}
		}
	}
	//將來源文件附加到目標文件的末端。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 成功實現了「清單使用目標樣式」功能。最終文件將包含與目標文件中的清單樣式合併的內容。