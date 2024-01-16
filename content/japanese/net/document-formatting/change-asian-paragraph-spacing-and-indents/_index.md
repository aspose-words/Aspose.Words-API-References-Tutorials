---
title: Word文書のアジア言語の段落間隔とインデントを変更する
linktitle: Word文書のアジア言語の段落間隔とインデントを変更する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書のアジア言語の段落間隔とインデントを変更する方法を学びます。
type: docs
weight: 10
url: /ja/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
このチュートリアルでは、Aspose.Words for .NET を使用してアジア言語の段落の間隔とインデントを変更する方法を説明します。以下の手順に従ってソース コードを理解し、変更を適用します。

## ステップ 1: ドキュメントをロードする

まず、ドキュメントのディレクトリを指定し、アジアのタイポグラフィを含むドキュメントを Document オブジェクトにロードします。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## ステップ 2: 段落の間隔とインデントを変更する

ここで、アジア文書の最初の段落の間隔とインデントを変更します。その方法は次のとおりです。

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; //更新ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // ParagraphFormat.RightIndent を更新します
format.CharacterUnitFirstLineIndent = 20; //ParagraphFormat.FirstLineIndent を更新します
format.LineUnitBefore = 5; //更新ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // ParagraphFormat.SpaceAfter を更新します
```

## ステップ 3: ドキュメントを保存する

テキスト入力フォームフィールドを挿入した後、`Save`方法。必ず適切なファイル パスを指定してください。

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Aspose.Words for .NET を使用してアジア言語の段落間隔とインデントを変更するためのソース コードの例

Aspose.Words for .NET を使用したアジア言語の段落間隔とインデントの編集機能の完全なソース コードを次に示します。

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent が更新されます
	format.CharacterUnitRightIndent = 10;      //ParagraphFormat.RightIndent が更新されます
	format.CharacterUnitFirstLineIndent = 20;  //ParagraphFormat.FirstLineIndent が更新されます
	format.LineUnitBefore = 5;                 //ParagraphFormat.SpaceBefore が更新されます
	format.LineUnitAfter = 10;                 //ParagraphFormat.SpaceAfter が更新されます

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

このコードを使用すると、Aspose.Words for .NET を使用してアジア言語の段落の間隔とインデントを変更できるようになります。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してアジア言語の段落の間隔とインデントを変更する方法を学びました。関連するプロパティを変更することで、`ParagraphFormat`を使用すると、Word 文書内のアジア言語の段落のレイアウトと外観を制御できます。この機能は、アジアの文字を使用したテキストの書式設定をカスタマイズし、言語コンテンツが混在するドキュメントで望ましい視覚的プレゼンテーションを実現するのに役立ちます。

### よくある質問

#### Q: Aspose.Words for .NET の「アジア言語の段落間隔とインデントの変更」機能は何をしますか?

A: Aspose.Words for .NET の「アジア言語の段落間隔とインデントの変更」機能を使用すると、Word 文書内のアジア言語の段落の間隔とインデントのプロパティを変更できます。左右のインデント、最初の行のインデント、前後のスペースの値を調整して、段落のレイアウトと外観を制御できます。

#### Q: Aspose.Words for .NET を使用してアジア言語の段落の間隔とインデントを変更するにはどうすればよいですか?

 A: アジア言語の段落の間隔とインデントを変更するには、`ParagraphFormat`ターゲット段落のプロパティを変更し、関連するプロパティを変更します。提供されているコード例では、ドキュメントの最初の段落にアクセスし、`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` 、 そして`LineUnitAfter`プロパティを使用して間隔とインデントを調整します。

#### Q: これらの変更を文書内の他の段落に適用できますか?

 A: はい、各段落にアクセスすることで、これらの変更を文書内の他の段落に適用できます。`ParagraphFormat`オブジェクト。コード例はドキュメントの最初の段落をターゲットにしていますが、インデックスを調整することで他の段落を変更できます。`Paragraphs`コレクションを使用するか、他の基準を使用して目的の段落を選択します。