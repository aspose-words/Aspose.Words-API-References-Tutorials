---
title: 從 Word 檔案讀取 Active XControl 屬性
linktitle: 從 Word 檔案讀取 Active XControl 屬性
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 讀取 Word 檔案中 ActiveX 控制項的屬性。
type: docs
weight: 10
url: /zh-hant/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

在本逐步指南中，我們將向您展示如何使用 Aspose.Words for .NET 讀取 Word 檔案中 ActiveX 控制項的屬性。我們將為您提供完整的原始程式碼，並向您展示如何格式化 Markdown 輸出。

## 第1步：文檔初始化

第一步是初始化`Document`透過載入包含 ActiveX 控制項的 Word 文件來建立物件。一定要更換`MyDir`與包含文件的目錄的實際路徑。

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## 步驟 2：恢復 ActiveX 控件

在這一步驟中，我們將迭代每個`Shape`文件的目錄以檢索 ActiveX 控制項並讀取其屬性。

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### 使用 Aspose.Words for .NET 讀取 Active XControl 屬性的範例原始碼

以下是使用 Aspose.Words for .NET 讀取 ActiveX 控制項屬性的完整原始碼：

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## 結論

本指南向您展示如何使用 Aspose.Words for .NET 讀取 Word 檔案中 ActiveX 控制項的屬性。透過執行所描述的步驟，您可以初始化文件、檢索 ActiveX 控制項並讀取其屬性。使用提供的範例程式碼作為起點，並根據您的特定需求進行自訂。

讀取 ActiveX 控制項的屬性可讓您從包含這些控制項的 Word 檔案中提取重要資訊。 Aspose.Words for .NET 為具有 ActiveX 控制項的文字處理和自動化文件處理提供了強大的功能。

### 常見問題解答

#### Q：讀取 Word 文件中 ActiveX 控制項屬性的第一步是什麼？

答：第一步是初始化`Document`透過載入包含 ActiveX 控制項的 Word 文件來建立物件。一定要更換`MyDir`與包含文件的目錄的實際路徑。

#### Q：如何將 ActiveX 控制項新增至文件？

答：要檢索 ActiveX 控件，您需要遍歷每個控件`Shape`文件並檢查它是否是 ActiveX 控制項。使用`OleFormat`的財產`Shape`訪問`OleControl`物件並檢索必要的屬性。

#### Q：我可以讀取 ActiveX 控制項的哪些屬性？

答：您可以讀取 ActiveX 控制項的各種屬性，例如標題、值、啟用或停用狀態、類型以及與控制項關聯的子節點。

#### Q：如何取得文件中ActiveX控制項的總數？

 A：要取得文件中ActiveX控制項的總數，可以使用`GetChildNodes`的方法`Document`物件指定`NodeType.Shape`類型並包括子節點。