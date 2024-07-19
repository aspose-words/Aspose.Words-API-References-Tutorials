---
title: 每級使用空格字元進行列表縮排
linktitle: 每級使用空格字元進行列表縮排
second_title: Aspose.Words 文件處理 API
description: 在 Aspose.Words for .NET 中使用每級空格字元進行清單縮排的逐步指南。輕鬆建立結構良好的 Word 文件。
type: docs
weight: 10
url: /zh-hant/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words for .NET 是一個功能強大的程式庫，用於在 C# 應用程式中建立、編輯和操作 Word 文件。 Aspose.Words 提供的功能之一是可以在每一層使用一個空格字元來縮排列表。在本指南中，我們將向您展示如何使用 Aspose.Words for .NET 的 C# 原始程式碼來實作此功能。

## 了解 Aspose.Words 函式庫

在深入研究程式碼之前，了解 .NET 的 Aspose.Words 函式庫非常重要。 Aspose.Words 是一個受歡迎的函式庫，它讓 Word 文件的文字處理變得簡單有效率。它提供了廣泛的建立、修改和操作 Word 文件的功能，包括清單和縮排的管理。

## 建立文件並添加內容

第一步是建立一個新文件並在其中添加內容。使用 Document 類別建立一個新的文檔實例。然後使用 DocumentBuilder 類別新增文字並建立具有多層縮排的清單。這是一個例子：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//建立具有三級縮排的列表
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

在此範例中，我們建立一個新文件並使用 DocumentBuilder 新增文字並建立具有三級縮排的清單。我們在清單中新增了三個項目，每個項目都縮排了一個額外的層級。

## 每級使用一個空格字元進行列表縮排

新增內容後，我們現在可以使用每級一個空格字元來配置清單的縮排。為此，我們使用 TxtSaveOptions 類，並將 ListIndentation.Count 屬性設為縮排等級數，將 ListIndentation.Character 屬性設為要使用的空格字元。就是這樣：

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

在此範例中，我們建立 TxtSaveOptions 的實例並將 ListIndentation.Count 屬性設為 3 以指示清單中存在三個縮排等級。我們也將 ListIndentation.Character 屬性設定為要用於縮排的空格字元 (' ')。

### Aspose.Words for .NET 的「每級使用一個空格字元進行清單縮排」功能的範例原始碼

以下是 Aspose.Words for .NET 的「每級使用一個空格字元進行清單縮排」功能的完整範例原始碼：

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             //文檔目錄的路徑
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             //建立文件並添加內容
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             //建立具有三級縮排的列表
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             //每級使用一個空格字元進行列表縮排
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             //使用指定選項儲存文檔
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## 結論

在本指南中，我們說明如何使用 Aspose.Words for .NET 來套用「每層使用一個空格字元進行清單縮排」功能。透過依照提供的步驟並使用提供的 C# 原始碼，您可以輕鬆配置 Word 文件中清單的縮進，每層使用一個空格字元。 Aspose.Words 透過文字格式化和清單管理為文字處理提供了巨大的靈活性和強大功能，讓您在 C# 應用程式中建立結構良好的文件。

### 經常問的問題

#### Q：什麼是 Aspose.Words for .NET？
Aspose.Words for .NET 是一個功能強大的程式庫，用於在 C# 應用程式中建立、編輯和操作 Word 文件。它為 Word 文件的文字處理提供了許多功能，包括每個層級使用一個空格進行縮排清單的功能。

#### Q：如何使用 Aspose.Words for .NET 在每一層使用一個空格來進行清單縮排？
您可以按照以下步驟在每一層使用一個空格來縮排清單：

使用建立一個新文檔`Document`班級。

使用`DocumentBuilder`類別會向文件新增內容並建立具有多層縮排的清單。

新增內容並配置清單縮排後，請使用`TxtSaveOptions`類別並設定`ListIndentation.Count`屬性與縮排等級的數量和`ListIndentation.Character`空間上的屬性（`' '`）來使用。

使用指定選項儲存文檔`Save`的方法`Document`班級。

#### Q：Aspose.Words 是否支援其他字元進行清單縮排？
是的，Aspose.Words 支援其他字元來縮排列表。您可以使用非空白字符，例如製表符 (`'\t'` ) 或其他特殊字符，透過設定`ListIndentation.Character`屬性到所需的角色。

#### Q：是否可以自訂清單縮排每級的空格數？
是的，您可以透過變更清單縮排的值來自訂每級的空格數`ListIndentation.Count`財產在`TxtSaveOptions`班級。您可以指定每個縮排等級所需的空格數。

#### Q：Aspose.Words 還提供哪些其他清單管理功能？
Aspose.Words 提供了許多用於管理 Word 文件中的清單的功能。您可以建立編號清單或項目符號清單、設定縮排等級、自訂清單樣式、新增清單項目等等。