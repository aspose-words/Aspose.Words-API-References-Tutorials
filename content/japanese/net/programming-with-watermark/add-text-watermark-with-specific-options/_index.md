---
title: 特定のオプションでテキスト透かしを追加する
linktitle: 特定のオプションでテキスト透かしを追加する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、特定のオプションでテキスト透かしを追加する方法を学習します。ステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、特定のオプションでテキスト透かしを追加する方法について説明します。テキスト透かしは、ドキュメントが下書きや機密文書であることを示すためにドキュメントに重ねて表示されるテキストです。

## ステップ1: ドキュメントジェネレーターの使用

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントの読み込み

ドキュメント パスを使用して既存のドキュメントを読み込みます。

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## ステップ3: 特定のオプションでテキスト透かしを追加する

インスタンスを作成します`TextWatermarkOptions`クラスを選択し、テキスト透かしの必要なオプションを設定します。

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## ステップ4: ドキュメントを保存する

最後に、テキスト透かしを追加したドキュメントを保存できます。

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Aspose.Words for .NET を使用して特定のオプションでテキスト透かしを追加するためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

おめでとうございます！Aspose.Words for .NET を使用して、特定のオプションでテキスト透かしを追加する方法を学習しました。

