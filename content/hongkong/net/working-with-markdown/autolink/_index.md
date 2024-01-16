---
title: 自動連結
linktitle: 自動連結
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 逐步指南插入自動連結。
type: docs
weight: 10
url: /zh-hant/net/working-with-markdown/autolink/
---

在此範例中，我們將解釋如何使用 Aspose.Words for .NET 的「自動連結」功能。此功能可讓您自動將超連結插入文件中。

## 第 1 步：使用文件產生器

首先，我們將使用文件產生器將內容新增至文件。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 步驟 2：插入超鏈接

我們可以使用以下命令插入超鏈接`InsertHyperlink`文檔生成器的方法。我們指定 URL 和要為連結顯示的文字。

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
```

## 步驟 3：插入電子郵件地址作為鏈接

我們也可以使用「mailto:」前綴插入電子郵件地址作為連結。這將允許用戶單擊連結來打開他們的預設電子郵件用戶端。

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## 步驟 4：儲存文檔

最後，我們可以將文件儲存為所需的格式。

### 使用 Aspose.Words for .NET 的自動連結範例原始碼


```csharp
//使用文件產生器將內容新增至文件。
DocumentBuilder builder = new DocumentBuilder();

//插入超連結。
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


恭喜！現在您已經了解如何使用 Aspose.Words for .NET 的「自動連結」功能。


### 常見問題解答

#### Q：如何在 Aspose.Words 中建立指向 URL 位址的自動連結？

答：要在 Aspose.Words 中建立指向 URL 地址的自動鏈接，您可以使用`<a>`標籤與`href`包含 URL 位址的屬性。例如，您可以使用`<a href="https://www.aspose.com">https://www.aspose.com</a>`自動連結到“https://www.aspose.com”。

#### Q：是否可以在 Aspose.Words 中自訂自動連結的顯示文字？

答：是的，您可以在 Aspose.Words 中自訂自動連結的顯示文字。您可以透過取代 URL 位址之間的內容來使用任何其他文本，而不是使用 URL 位址作為顯示文字。`<a>`標籤。例如，您可以使用`<a href="https://www.aspose.com">Click here</a>`將文字「按一下此處」顯示為自動連結。

#### Q：如何在 Aspose.Words 中的自動連結新增其他屬性？

答：若要為 Aspose.Words 中的自動連結新增附加屬性，您可以在`<a>`標籤。例如，您可以使用`<a href="https://www.aspose.com" target="_blank">Link</a>`使用以下命令在新視窗或標籤中開啟鏈接` attribute target="_blank"`.