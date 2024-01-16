---
title: 修改內容控件
linktitle: 修改內容控件
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 修改 Word 文件內容控制項中的文字、下拉清單和圖片。
type: docs
weight: 10
url: /zh-hant/net/programming-with-sdt/modify-content-controls/
---

本教學課程介紹如何使用 Aspose.Words for .NET 修改 Word 文件中不同類型的內容控制項。您可以更新文字、下拉清單的選定值，或取代內容控制項中的圖片。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 Word 文件文字處理的基礎知識。

## 第 1 步：設定文檔目錄
首先設定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文件所在目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入文件並迭代內容控件
使用以下命令載入 Word 文檔`Document`建構函數，將文檔的路徑作為參數傳遞。使用迭代遍歷文件中的所有結構化文件標籤`foreach`環形。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    //根據內容控制項的類型執行操作
}
```

## 步驟3：修改純文字內容控制項
對於類型的內容控件`SdtType.PlainText`，刪除所有現有子項，建立一個新段落，並附加一個包含所需文字的段落。

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## 第四步：修改下拉式清單內容控制項
對於類型的內容控件`SdtType.DropDownList`，透過將其設為特定值來更新所選值`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## 第五步：修改圖片內容控件
對於類型的內容控件`SdtType.Picture`，檢索內容控制項內的形狀並以新影像取代其影像。

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## 步驟6：儲存修改後的文檔
使用指令將修改後的文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithSdt.ModifyContentControls.docx」。

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### 使用 Aspose.Words for .NET 修改內容控制項的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

就是這樣！您已使用 Aspose.Words for .NET 成功修改了 Word 文件中不同類型的內容控制項。