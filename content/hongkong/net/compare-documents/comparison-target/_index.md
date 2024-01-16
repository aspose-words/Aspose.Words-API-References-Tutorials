---
title: Word文件中的比較目標
linktitle: Word文件中的比較目標
second_title: Aspose.Words 文件處理 API
description: 了解 Aspose.Words for .NET 的 Word 文件功能中的比較目標，該功能可讓您比較文件並產生包含所做變更的新文件。
type: docs
weight: 10
url: /zh-hant/net/compare-documents/comparison-target/
---
以下是解釋下面 C# 原始程式碼的逐步指南，該程式碼使用 Aspose.Words for .NET 的 Word 文件功能中的比較目標。

## 第 1 步：簡介

Aspose.Words for .NET 的比較目標功能可讓您比較兩個文件並產生一個包含對目標文件所做變更的新文件。這對於追蹤文件的不同版本之間所做的更改非常有用。

## 第2步：設定環境

在開始之前，您需要設定開發環境以使用 Aspose.Words for .NET。確保您已安裝 Aspose.Words 庫並擁有合適的 C# 專案來嵌入程式碼。

## 第 3 步：新增所需的程序集

若要使用 Aspose.Words for .NET 的比較目標功能，您必須將必要的組件新增至專案。確保您的專案中有對 Aspose.Words 的正確引用。

```csharp
using Aspose.Words;
```

## 第四步：文檔初始化

在這一步驟中，我們將初始化兩個文件以進行比較。您必須指定文件所在的目錄路徑以及來源文件的名稱。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//初始化要比較的文件 A。
Document docA = new Document(dataDir + "DocumentA.docx");

//複製文件 A 以建立文件 B 的相同副本。
Document docB = docA.Clone();
```

## 第 5 步：配置比較選項

在此步驟中，我們將配置比較選項以指定比較的行為。選項包括忽略格式的功能以及比較目標，即 Microsoft Word 的「比較文件」對話方塊中的「顯示變更」選項。

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## 第六步：文件比較

現在我們將比較文件並在新文件中產生結果。

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

這`Compare`方法將文件 A 與文件 B 進行比較，並將變更儲存至文件 A。您可以指定使用者名稱和比較日期以供參考。

### 使用 Aspose.Words for .NET 的比較目標的範例原始程式碼


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

//與 Microsoft Word「比較文件」對話方塊中的「顯示變更」選項相關。
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## 結論

在本文中，我們探討了 Aspose.Words for .NET 的 diff 目標功能。此功能可讓您比較兩個文件並產生包含所做變更的新文件。您可以使用這些知識來追蹤文件不同版本之間的變更。

### 常見問題解答

#### Q：在 Aspose.Words for .NET 中使用比較目標的目的為何？

答：Aspose.Words for .NET 中的比較目標可讓您比較兩個文件並產生一個包含對目標文件所做更改的新文件。此功能對於追蹤文件不同版本之間所做的更改以及可視化單獨文件中的差異非常有用。

#### Q：如何在 Aspose.Words for .NET 中使用比較目標？

答：若要在 Aspose.Words for .NET 中使用比較目標，請依照下列步驟操作：
1. 使用 Aspose.Words 函式庫設定您的開發環境。
2. 透過引用 Aspose.Words 將必要的程式集新增到您的專案中。
3. 使用以下命令初始化要比較的文檔`Document`類或`DocumentBuilder`班級。
4. 透過建立一個來配置比較選項`CompareOptions`物件並設定屬性，例如`IgnoreFormatting`和`Target`（例如，`ComparisonTargetType.New`為比較目標）。
5. 使用`Compare`一個文檔上的方法，傳遞另一個文檔和`CompareOptions`對像作為參數。此方法將比較文件並將變更保存在第一個文件中。

####  Q：這樣做的目的是什麼`Target` property in the `CompareOptions` class?

答： 的`Target`財產在`CompareOptions`類別可讓您指定比較目標，這類似於 Microsoft Word 的「比較文件」對話方塊中的「顯示變更」選項。目標可以設定為`ComparisonTargetType.New`顯示新文件中的更改，`ComparisonTargetType.Current`顯示目前文件中的更改，或`ComparisonTargetType.Formatting`僅顯示格式變更。