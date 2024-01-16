---
title: 將 Docx 轉換為 Rtf
linktitle: 將 Docx 轉換為 Rtf
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將 Word 文件從 Docx 轉換為 RTF 格式。帶有範例原始程式碼的分步教程。
type: docs
weight: 10
url: /zh-hant/net/basic-conversions/docx-to-rtf/
---

在本逐步教學中，我們將指導您如何使用 Aspose.Words for .NET 將 Docx 格式的 Word 文件轉換為 RTF。我們將解釋提供的 C# 原始程式碼，並向您展示如何在您自己的專案中實現它。

首先，請確保您已在開發環境中安裝並設定了 Aspose.Words for .NET。如果您還沒有這樣做，請從以下位置下載並安裝該程式庫[Aspose.Releases]https://releases.aspose.com/words/net/。

## 步驟1：從Stream讀取文檔

首先，開啟一個流來讀取Docx文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## 第 2 步：載入文檔

接下來，從流載入文檔：

```csharp
Document doc = new Document(stream);
```

## 第 3 步：關閉流

由於文件已載入到記憶體中，因此您可以關閉流：

```csharp
stream.Close();
```

## 第四步：對文件進行操作

此時，您可以對文件執行任何所需的操作。

## 第 5 步：將文件儲存為 RTF 格式

若要將文件儲存為 RTF 格式，請將其儲存至記憶體流：

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## 第 6 步：倒帶流

在將記憶體流寫入檔案之前，將其位置回滾到零：

```csharp
dstStream.Position = 0;
```

## 步驟7：將流寫入文件

最後，將記憶體流寫入RTF檔：

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

就是這樣！您已使用 Aspose.Words for .NET 成功將 Docx 格式的 Word 文件轉換為 RTF。

### 使用 Aspose.Words for .NET 的 Docx To Rtf 範例原始碼

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//只讀存取權限足以讓 Aspose.Words 載入文件。
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	//現在您可以關閉串流，不再需要它，因為文件位於記憶體中。
	stream.Close();

	// ....對文檔進行一些操作。

	//將文件轉換為不同的格式並儲存到流。
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	//將流位置倒回零，以便為下一個讀取器做好準備。
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

請隨意在您自己的專案中使用此程式碼，並根據您的特定要求進行修改。

### 常見問題解答

#### 如何將 DOCX 檔案轉換為 RTF 格式？

若要將 DOCX 檔案轉換為 RTF 格式，您可以使用提供此功能的各種軟體工具或程式庫。 Aspose.Words for .NET 就是這樣一個可靠的工具。它提供了一種簡單有效的方法，以程式設計方式將 DOCX 檔案轉換為 RTF 格式。您可以使用該程式庫的 API 載入 DOCX 檔案並將其儲存為所需的 RTF 格式。

#### 轉換過程是否有任何限制？

轉換過程的限制取決於您使用的特定工具或程式庫。某些工具可能對輸入文件的大小或複雜性有限制。選擇能夠滿足轉換任務要求的工具非常重要。

#### 我可以保留原始文件的格式和佈局嗎？

是的，使用 Aspose.Words，您可以在轉換過程中保留原始文件的格式和佈局。例如，Aspose.Words for .NET 為在轉換後的 RTF 文件中維護 DOCX 文件的格式、樣式和其他元素提供了全面的支援。

#### Aspose 是 DOCX 到 RTF 轉換的可靠工具嗎？

是的，Aspose.Words for .NET 是一款高度可靠的 DOCX 到 RTF 轉換工具。它以其強大的功能和卓越的性能而被全球開發人員和企業廣泛使用。該庫提供廣泛的文檔、定期更新和專門的技術支持，使其成為文檔轉換任務的值得信賴的選擇。