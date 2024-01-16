---
title: Word 文書内のアジア語とラテン語のテキスト間のスペース
linktitle: Word 文書内のアジア語とラテン語のテキスト間のスペース
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のアジア語とラテン語のテキスト間のスペースを自動的に調整する方法を学びます。
type: docs
weight: 10
url: /ja/net/document-formatting/space-between-asian-and-latin-text/
---
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書機能のアジア語とラテン語のテキスト間のスペース機能を使用する方法を説明します。以下の手順に従ってソース コードを理解し、変更を適用します。

## ステップ 1: ドキュメントの作成と構成

まず、新しいドキュメントと関連する DocumentBuilder オブジェクトを作成します。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: アジア語とラテン語のテキスト間のスペースを設定する

次に、ParagraphFormat オブジェクトのプロパティを使用して、アジア語とラテン語のテキスト間のスペースを構成します。その方法は次のとおりです。

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## ステップ 3: ドキュメントを保存する

テキスト入力フォームフィールドを挿入した後、`Save`方法。必ず適切なファイル パスを指定してください。

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Aspose.Words for .NET を使用したアジアとラテンのテキスト間のスペースのソース コードの例

Aspose.Words for .NET を使用したアジア文字とラテン文字の間のスペース機能の完全なソース コードは次のとおりです。


```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Automatically adjust space between Asian and Latin text");
builder.Writeln("Automatically adjust space between Asian text and numbers");

doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

このコードを使用すると、Aspose.Words for .NET を使用してドキュメント内のアジア語とラテン語のテキスト間のスペースを自動的に調整できるようになります。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して、スペース機能を使用して Word 文書内のアジア語とラテン語のテキスト間の間隔を調整するプロセスについて説明しました。概要を示した手順に従うことで、適切な間隔と配置を確保できます。これは、アジアとラテンの混合コンテンツを扱う場合に特に役立ちます。

### よくある質問

#### Q: Word 文書内のアジア文字とラテン文字の間のスペース機能とは何ですか?

A: Word 文書内のアジア語とラテン語のテキスト間のスペース機能とは、アジア語 (中国語、日本語など) とラテン語 (英語など) など、異なる文字で書かれたテキスト間のスペースを自動的に調整する機能を指します。

#### Q: アジア語とラテン語のテキストの間のスペースを調整することが重要なのはなぜですか?

A: アジア言語とラテン語のテキスト間のスペースを調整することは、文書内でさまざまな文字が調和してブレンドされるようにするために非常に重要です。適切な間隔を設定すると、読みやすさと全体的な外観が向上し、テキストが窮屈になったり広がったりするのを防ぎます。

#### Q: 異なるスクリプト間のスペース調整をカスタマイズできますか?

 A: はい、次のコマンドを使用して、異なるスクリプト間のスペース調整をカスタマイズできます。`AddSpaceBetweenFarEastAndAlpha`そして`AddSpaceBetweenFarEastAndDigit`プロパティ。これらのプロパティを有効または無効にすることで、アジア言語のテキストとラテン語のテキストの間、およびアジア言語のテキストと数字の間のスペースを制御できます。

#### Q: Aspose.Words for .NET は他のドキュメント書式設定機能をサポートしていますか?

A: はい、Aspose.Words for .NET は、さまざまな文書書式設定機能の広範なサポートを提供します。フォント スタイル、段落、表、画像などの機能が含まれています。 Word 文書をプログラムで効果的に操作し、書式設定することができます。

#### Q: Aspose.Words for .NET の追加リソースとドキュメントはどこで入手できますか?

 A: Aspose.Words for .NET の使用に関する包括的なリソースとドキュメントについては、次のサイトを参照してください。[Aspose.Words API リファレンス](https://reference.aspose.com/words/net/)。ここには、Aspose.Words for .NET の強力な機能を効果的に活用するための詳細なガイド、チュートリアル、コード サンプル、API リファレンスが含まれています。