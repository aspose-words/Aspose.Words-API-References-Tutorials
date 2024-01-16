---
title: 使用警告來源
linktitle: 使用警告來源
second_title: Aspose.Words 文件處理 API
description: 了解如何透過 Aspose.Words for .NET 逐步指南使用警告來源。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/use-warning-source/
---

在此範例中，我們將向您展示如何將警告來源與 Aspose.Words for .NET 一起使用。警告來源指示使用回調函數時警告的來源。

## 第 1 步：載入文檔

我們將使用以下命令載入包含警告的現有文檔`Load`的方法`Document`班級。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## 步驟 3：使用警告來源

我們將透過設定文檔的`WarningCallback`屬性到集合`WarningInfo`對象。

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## 步驟 4：儲存文檔

最後，我們可以將文件儲存為所需的格式。

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### 將警告來源與 Aspose.Words for .NET 一起使用的範例原始程式碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

恭喜！現在您已經了解如何將警告來源與 Aspose.Words for .NET 一起使用。

### 常見問題解答

#### Q：我們可以自訂「警告」標籤的外觀嗎？

答：「警告」標籤的格式取決於所使用的 Markdown 渲染器。在大多數情況下，您可以使用 CSS 來自訂外觀`blockquote`標記在您的文件中。

#### Q：「警告」標籤可以添加圖示嗎？

答：是的，可以在 Markdown 文件中使用 HTML 程式碼將圖示新增至「警告」標籤。您可以插入一個`span`具有適當類別的標記以在警告文字旁邊顯示圖示。

#### Q：「警告」標籤與所有 Markdown 閱讀器相容嗎？

 A：「警告」標籤的兼容性取決於所使用的 Markdown 渲染。大多數 Markdown 讀者都會支持`blockquote`標籤來顯示突出顯示的文本，但確切的外觀可能會有所不同。