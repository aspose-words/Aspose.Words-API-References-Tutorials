---
title: 取得字體行距
linktitle: 取得字體行距
second_title: Aspose.Words 文件處理 API
description: 透過此逐步教學，了解如何使用 Aspose.Words for .NET 取得字體行距。非常適合開發人員。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/get-font-line-spacing/
---
## 介紹

Aspose.Words for .NET 是一個功能強大的程式庫，可讓您以程式設計方式建立、操作和轉換 Word 文件。您可能需要執行的常見任務是檢索文件中特定字體的行距。在本教學中，我們將逐步引導您完成流程，確保您可以使用 Aspose.Words for .NET 輕鬆取得字體行距。 

## 先決條件

在我們深入研究程式碼之前，請確保您具備以下先決條件：

1.  Aspose.Words for .NET Library：下載並安裝最新版本[這裡](https://releases.aspose.com/words/net/).
2. 開發環境：確保您設定了類似 Visual Studio 的 IDE。
3. C# 基礎知識：本教學假設您對 C# 程式設計有基本了解。

## 導入命名空間

首先，您需要在 C# 專案中匯入必要的命名空間。這些命名空間將允許您存取 Aspose.Words 功能。

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

讓我們將取得字體行距的過程分解為簡單、易於管理的步驟。

## 第 1 步：建立一個新文檔

第一步是使用 Aspose.Words for .NET 建立一個新的 Word 文件實例。

```csharp
Document doc = new Document();
```

## 第2步：初始化DocumentBuilder

接下來我們需要初始化`DocumentBuilder`目的。該物件將幫助我們建立和操作文檔內容。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 3：設定字體屬性

現在，我們為要插入的文字設定字體屬性。對於此範例，我們將使用“Calibri”字體。

```csharp
builder.Font.Name = "Calibri";
```

## 第 4 步：將文字寫入文檔

使用`DocumentBuilder`對象，將一些文字寫入文件中。該文字將使用我們在上一步中設定的字體屬性。

```csharp
builder.Writeln("Sample Text");
```

## 第 5 步：檢索字體對象

為了取得行間距，我們需要存取剛剛新增的文字的字體物件。這可以透過瀏覽文件結構到第一段運行來完成。

```csharp
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
```

## 第 6 步：取得行距

最後，我們從字體物件中檢索行間距並將其列印到控制台。

```csharp
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## 結論

現在你就擁有了！當您將其分解為以下簡單步驟時，使用 Aspose.Words for .NET 檢索字體行間距非常簡單。無論您是建立新文檔還是使用現有文檔，Aspose.Words 都提供了有效管理字體屬性所需的所有工具。

## 常見問題解答

### 什麼是 Aspose.Words for .NET？
Aspose.Words for .NET 是一個功能強大的程式庫，可讓開發人員使用 C# 以程式設計方式建立、操作和轉換 Word 文件。

### 我可以在其他 .NET 語言中使用 Aspose.Words for .NET 嗎？
是的，您可以將 Aspose.Words for .NET 與任何 .NET 語言一起使用，包括 VB.NET 和 F#。

### 如何下載 Aspose.Words for .NET？
您可以從以下位置下載最新版本的 Aspose.Words for .NET[這裡](https://releases.aspose.com/words/net/).

### Aspose.Words for .NET 有沒有免費試用版？
是的，您可以從以下位置獲得免費試用[這裡](https://releases.aspose.com/).

### 在哪裡可以找到 Aspose.Words for .NET 的文檔？
 Aspose.Words for .NET 的文件已可用[這裡](https://reference.aspose.com/words/net/).