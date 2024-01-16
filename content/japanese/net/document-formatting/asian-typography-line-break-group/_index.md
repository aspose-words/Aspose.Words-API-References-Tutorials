---
title: Word 文書内のアジアのタイポグラフィ改行グループ
linktitle: Word 文書内のアジアのタイポグラフィ改行グループ
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書でアジアン タイポグラフィーの改行グループを使用する方法を学びます。
type: docs
weight: 10
url: /ja/net/document-formatting/asian-typography-line-break-group/
---
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書機能でアジアン タイポグラフィーの改行グループを使用する方法を説明します。以下の手順に従って、ソース コードを理解し、書式設定の変更を適用します。

## ステップ 1: ドキュメントをロードする

まず、ドキュメントのディレクトリを指定し、アジアのタイポグラフィを含むドキュメントを Document オブジェクトにロードします。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## ステップ 2: アジアのタイポグラフィのセットアップ

次に、ドキュメントの最初の段落のアジアのタイポグラフィ設定を構成します。その方法は次のとおりです。

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## ステップ 3: ドキュメントを保存する

テキスト入力フォームフィールドを挿入した後、`Save`方法。必ず適切なファイル パスを指定してください。

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Aspose.Words for .NET を使用したアジアのタイポグラフィ改行グループのソース コードの例

Aspose.Words for .NET を使用したアジアのタイポグラフィ改行グループ機能の完全なソース コードは次のとおりです。

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
このコードを使用すると、Aspose.Words for .NET を使用してアジアのタイポグラフィ改行グループを適用できるようになります。

## 結論

このチュートリアルでは、Aspose.Words for .NET の「アジアン タイポグラフィ改行グループ」機能を検討しました。を設定することで、`FarEastLineBreakControl`, `WordWrap` 、 そして`HangingPunctuation`のプロパティ`ParagraphFormat`により、Word 文書内のアジア系タイポグラフィの改行動作を制御することができました。この機能は、アジア言語の文字を処理し、言語コンテンツが混在する文書で適切な改行とワードラップを確保するのに役立ちます。

### よくある質問

#### Q: Aspose.Words for .NET の「アジアン タイポグラフィ改行グループ」機能とは何ですか?

A: Aspose.Words for .NET の「アジア タイポグラフィ改行グループ」機能を使用すると、Word 文書内のアジア タイポグラフィの改行動作を制御できます。具体的には、段落内でアジア系の文字を扱うときに行がどのように分割され、折り返されるかに影響します。

#### Q: Aspose.Words for .NET で「アジアン タイポグラフィ改行グループ」を有効にするにはどうすればよいですか?

 A: 「アジアン タイポグラフィ改行グループ」を有効にするには、`FarEastLineBreakControl`, `WordWrap` 、 そして`HangingPunctuation`のプロパティ`ParagraphFormat`文書内の関連する段落について。設定`FarEastLineBreakControl`に`false`改行に関してアジア文字がラテン文字と同様に扱われるようにします。`WordWrap`に設定`true`アジアのタイポグラフィのワードラップを有効にし、`HangingPunctuation`に設定`false`アジア言語のテキストで句読点がハングするのを防ぎます。

#### Q: 「アジアン タイポグラフィ改行グループ」を文書内の特定の段落に適用できますか?

A: はい、「アジアン タイポグラフィ改行グループ」設定を Word 文書内の特定の段落に適用できます。コード例では、設定はドキュメントの最初の段落に適用されます。必要に応じて他の段落をターゲットにするようにコードを調整するには、`Paragraphs`ドキュメント内の関連セクションのコレクション。