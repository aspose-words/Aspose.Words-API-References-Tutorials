---
title: 特定のオプションを使用してテキスト透かしを追加する
linktitle: 特定のオプションを使用してテキスト透かしを追加する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、特定のオプションを使用してテキストの透かしを追加する方法を学びます。ステップバイステップのガイド。
type: docs
weight: 10
url: /ja/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

このチュートリアルでは、Aspose.Words for .NET を使用して特定のオプションを使用してテキストの透かしを追加する方法を説明します。テキスト透かしは、文書が下書きであること、機密であることなどを示すために文書に重ねて表示されるテキストです。

## ステップ 1: ドキュメント ジェネレーターを使用する

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントをロードする

ドキュメント パスを使用して既存のドキュメントを読み込みます。

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## ステップ 3: 特定のオプションを使用してテキストの透かしを追加する

のインスタンスを作成します。`TextWatermarkOptions`クラスを開き、テキストの透かしに必要なオプションを設定します。

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

## ステップ 4: ドキュメントを保存する

最後に、テキスト透かしを追加してドキュメントを保存できます。

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Aspose.Words for .NET で特定のオプションを使用してテキスト透かしを追加するソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
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

おめでとうございます！ Aspose.Words for .NET を使用して、特定のオプションを使用してテキストの透かしを追加する方法を学習しました。

