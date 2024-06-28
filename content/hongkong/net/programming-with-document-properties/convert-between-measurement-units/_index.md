---
title: 測量單位之間的轉換
linktitle: 測量單位之間的轉換
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 在文件中的測量單位之間進行轉換的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document-properties/convert-between-measurement-units/
---

在本教程中，我們將引導您完成 C# 原始程式碼，以便使用 Aspose.Words for .NET 在測量單位之間進行轉換。此功能可讓您以不同的測量單位指定邊距、頁首和頁尾距離等。

## 第 1 步：項目設置

首先，在您最喜歡的 IDE 中建立一個新的 C# 專案。請確定您的專案中引用了 Aspose.Words for .NET 程式庫。

## 第 2 步：建立文件和建構函數

在此步驟中，我們將建立一個新文件並初始化建構函式。使用以下程式碼：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步驟 3：配置計量單位

現在我們將轉換不同測量單位的邊距、頁首和頁尾距離等值。使用以下代碼指定特定測量單位的值：

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

這段程式碼使用了`ConvertUtil`Aspose.Words 類別將指定值轉換為英吋（`InchToPoint` ）。您也可以使用其他可用的轉換方法`ConvertUtil`類別將值轉換為其他測量單位。

### 使用 Aspose.Words for .NET 在測量單位之間轉換的範例原始碼

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

現在您已經了解如何使用 Aspose.Words for .NET 在文件中指定邊距、頁首和頁尾距離等時在測量單位之間進行轉換。透過遵循本教學中提供的逐步指南，您可以輕鬆地在自己的文件中指定所需測量單位的值。