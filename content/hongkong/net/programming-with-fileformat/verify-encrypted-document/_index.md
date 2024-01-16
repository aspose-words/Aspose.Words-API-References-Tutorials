---
title: 驗證加密的Word文檔
linktitle: 驗證加密的Word文檔
second_title: Aspose.Words 文件處理 API
description: 驗證 Word 文件是否已使用 Aspose.Words for .NET 加密的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-fileformat/verify-encrypted-document/
---

本文提供了有關如何將加密 Word 文件驗證功能與 Aspose.Words for .NET 結合使用的逐步指南。我們將詳細解釋程式碼的每一部分。在本教學結束時，您將能夠了解如何檢查文件是否已加密。

在開始之前，請確保您已在專案中安裝並設定了 Aspose.Words for .NET 程式庫。您可以在 Aspose 網站上找到庫和安裝說明。

## 步驟1：定義文檔目錄

首先，您需要定義文件所在目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第2步：檢測文件格式

接下來，我們使用`DetectFileFormat`的方法`FileFormatUtil`類別來檢測文件格式資訊。在此範例中，我們假設加密文件名稱為「Encrypted.docx」並且位於指定的文檔目錄中。

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## 步驟3：檢查文件是否已加密

我們使用`IsEncrypted`的財產`FileFormatInfo`物件檢查文件是否已加密。該屬性傳回`true`如果文件已加密，否則返回`false`。我們在控制台中顯示結果。

```csharp
Console.WriteLine(info.IsEncrypted);
```

就這樣 ！您已使用 Aspose.Words for .NET 成功檢查文件是否已加密。

### 使用 Aspose.Words for .NET 驗證加密文件的範例原始碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```

## 經常問的問題

### Q：驗證加密的Word文檔的步驟是什麼？

驗證加密Word文檔的步驟如下：

定義文檔目錄。

檢測文件格式。

檢查文檔是否已加密。

### Q：如何設定文檔目錄？
設定文檔目錄，需要替換`"YOUR DOCUMENT DIRECTORY"`在以下程式碼中使用文檔目錄的實際路徑：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### Q：如何檢測文件格式？
您可以使用`DetectFileFormat`的方法`FileFormatUtil`類別來檢測文件格式資訊。在下列範例中，我們假設加密文件名稱為「Encrypted.docx」並且位於指定的文件目錄中：

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### Q：如何檢查文件是否加密？
您可以使用`IsEncrypted`的財產`FileFormatInfo`物件檢查文件是否已加密。該屬性傳回`true`如果文件已加密，否則返回`false`。結果顯示在控制台中：

```csharp
Console.WriteLine(info.IsEncrypted);
```

### Q：如何使用 Aspose.Words for .NET 檢查文件是否已加密？
透過遵循本教學中提到的步驟並執行提供的原始程式碼，您可以使用 Aspose.Words for .NET 檢查文件是否已加密。
