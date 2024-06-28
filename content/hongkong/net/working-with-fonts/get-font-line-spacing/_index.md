---
title: 取得字體行距
linktitle: 取得字體行距
second_title: Aspose.Words 文件處理 API
description: 在本教學中，了解如何使用 Aspose.Words for .NET 取得 Word 文件中的字體行距。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/get-font-line-spacing/
---
在本教學中，我們將告訴您如何使用 .NET 的 Aspose.Words 函式庫來取得 Word 文件中的字體行距。字體行距定義文字行之間的垂直間距。我們將逐步指導您瞭解並實作 .NET 專案中的程式碼。

## 先決條件
在開始之前，請確保您擁有以下物品：
- C# 程式語言的應用知識
- 專案中安裝的 .NET 的 Aspose.Words 函式庫

## 第 1 步：建立新文件和文件產生器
首先，我們將透過實例化建立一個新文檔`Document`類別和文件建構器透過實例化`DocumentBuilder`班級。

```csharp
//建立一個新文檔
Document doc = new Document();

//建立文檔產生器
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第2步：配置字體
接下來，我們將透過設定來配置字體`Name`文檔生成器的屬性。

```csharp
//配置字體
builder.Font.Name = "Calibri";
```

## 步驟 3：為文件新增文本
我們現在將使用文件產生器將格式化文字新增至文件。

```csharp
//新增文字到文檔
builder. Writen("qText");
```

## 第四步：取得字體行距
現在我們將訪問`Font`文檔第一段的物件並檢索該值`LineSpacing`財產。

```csharp
//取得字體的行距
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### 使用 Aspose.Words for .NET 取得字體行間距的範例原始程式碼 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## 結論
在本教學中，我們了解如何使用 Aspose.Words for .NET 取得 Word 文件中的字體行間距。字體行距對於控製文字行之間的垂直間距非常重要。請隨意使用此功能來自訂文件中文字的外觀。

### 常見問題解答

#### Q：如何更改Word文件中特定文字的行距？

答：使用Aspose.Words，您可以輕鬆變更Word文件中特定文字的行距。使用 API 選擇所需的文字並透過指定適當的值來調整行間距。

#### Q：是否可以在 Word 文件中套用精確的行間距？

答：是的，Aspose.Words 允許您在 Word 文件中套用精確的行間距。您可以使用 API 指定行間距的精確值。

#### Q：如何調整整個Word文件的行距？

答：使用Aspose.Words，您可以輕鬆調整整個Word文件的行距。使用 API 提供的方法指定整個文件所需的行距。

#### Q：Aspose.Words 支援多行間距嗎？

答：是的，Aspose.Words 支援 Word 文件中的多行間距。您可以為文字行設定多個間距，例如正常間距的 1.5 倍或 2 倍。

#### Q：調整行距時如何避免行重疊問題？

答：為避免調整行間距時出現行重疊問題，請務必選擇適當的間距值。也要測試文件的最終渲染，以確保文字保持可讀且格式良好。