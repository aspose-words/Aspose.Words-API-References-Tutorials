---
title: 關聯
linktitle: 關聯
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 插入連結。逐步指南。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/link/
---

在此範例中，我們將引導您了解如何使用 Aspose.Words for .NET 的連結功能。連結用於建立對網站或其他文件的可點擊引用。

## 第 1 步：使用文件產生器

首先，我們將使用文件產生器將內容新增至文件。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：插入鏈接

我們可以使用以下命令插入鏈接`InsertHyperlink`文檔生成器的方法。我們需要指定連結文字（此處為「Apose」）以及目標 URL。

```csharp
builder.InsertHyperlink("Aspose", "https://www.aspose.com”，錯誤）；
```

### Aspose.Words for .NET 連結的範例原始碼


```csharp
//使用文件產生器將內容新增至文件。
DocumentBuilder builder = new DocumentBuilder();

//插入連結。
builder.InsertHyperlink("Aspose", "https://www.aspose.com”，錯誤）；
```
恭喜！現在您已經了解如何使用 Aspose.Words for .NET 的連結功能。


### 常見問題解答

#### Q：如何連結到 Aspose.Words 中的 URL？

答：要連結到 Aspose.Words 中的 URL 位址，您可以使用`<a>`標籤與`href`包含 URL 位址的屬性。例如，您可以使用`<a href="https://www.aspose.com">Click Here</a>`超連結到 URL“https://www.example.com”，顯示文字“點擊此處”。

#### Q：是否可以連結到 Aspose.Words 中的內部書籤？

答：是的，可以連結到 Aspose.Words 中的內部書籤。您可以使用`<a>`標籤與`href`包含前面帶有哈希 (#) 的書籤名稱的屬性。例如，`<a href="#bookmark1">Go to bookmark 1</a>`將連結到文件中名為「bookmark1」的書籤。

#### Q：如何在 Aspose.Words 中自訂連結的顯示文字？

答：要自訂Aspose.Words中連結的顯示文本，您可以修改連結之間的內容`<a>`標籤。例如，`<a href="https://www.aspose.com">Click here</a>`將顯示文字「按一下此處」作為超連結。

#### Q：我可以在 Aspose.Words 中指定連結的目標嗎？

答：是的，您可以使用 Aspose.Words 中的連結指定目標`target`的屬性`<a>`標籤。例如，`<a href="https://www.aspose.com" target="_blank">Open in new window</a>`將在新視窗或標籤中開啟連結。