---
title: Word 文書で優先されるコントロールの種類
linktitle: Word 文書で優先されるコントロールの種類
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して HTML ドキュメントを読み込むときに、Word ドキュメントで優先されるコントロール タイプを指定するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlloadoptions/preferred-control-type/
---
この記事では、Aspose.Words for .NET で優先コントロール タイプ機能を使用する方法について、ステップ バイ ステップで説明します。コードの各部分を詳しく説明します。このチュートリアルの最後には、HTML ドキュメントを読み込むときに優先コントロール タイプを指定する方法が理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで参照できます。

## ステップ1: HTMLコードを定義する

まず、ドキュメントとしてロードしたいHTMLコードを定義する必要があります。この例では、`html`オプション付きのセレクターの HTML コードを含む変数。

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## ステップ2: HTML読み込みオプションを設定する

次に、`HtmlLoadOptions`オブジェクトを設定し、`PreferredControlType`財産に`HtmlControlType.StructuredDocumentTag`. これにより、Aspose.Words は読み込み時に StructuredDocumentTags を使用して HTML を表すようになります。

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## ステップ3: ドキュメントを読み込んで保存する

私たちは`Document`クラスは、先に定義したロードオプションを使用してメモリストリームからHTMLコードをロードします。次に、指定されたディレクトリにドキュメントを保存します。`.docx`ファイル形式。

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Aspose.Words for .NET の優先コントロール タイプのサンプル ソース コード

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

以上です。Aspose.Words for .NET を使用して HTML ドキュメントを読み込むときに、優先コントロール タイプを正常に指定できました。

## 結論

このステップバイステップガイドに従って、Aspose.Words for .NETの「優先コントロールタイプ」機能を使用して、HTMLドキュメントを読み込むときに必要なコントロールタイプを指定する方法を学習しました。`PreferredControlType`財産に`HtmlControlType.StructuredDocumentTag` Aspose.Words で StructuredDocumentTags (SDT) を使用して、HTML コンテンツの表現と処理を改善できます。特定の要件に合わせて、他のコントロール タイプも検討できます。この機能を使用すると、Aspose.Words を使用した C# アプリケーションで HTML ドキュメントを正確かつ効率的に処理できるようになります。

### Word 文書の優先コントロール タイプに関する FAQ

#### Q: Aspose.Words for .NET の「優先コントロール タイプ」機能とは何ですか?

A: 「優先コントロール タイプ」機能を使用すると、HTML ドキュメントを読み込むときに HTML 要素を表す優先コントロール タイプを指定できます。この機能は、HTML コンテンツの表現と処理を向上させるために適切なコントロール タイプを選択するのに役立ちます。

#### Q: HTML ドキュメントを読み込むときに優先コントロール タイプを設定するにはどうすればよいですか?

 A: 優先コントロールタイプを設定するには、`HtmlLoadOptions`オブジェクトを設定し、`PreferredControlType`希望する物件`HtmlControlType`提供された例では、`HtmlControlType.StructuredDocumentTag`使用されている。

#### Q: StructuredDocumentTags (SDT) を優先コントロール タイプとして使用することの重要性は何ですか?

A: StructuredDocumentTags (SDT) は、Word 文書内の複雑なコンテンツやコントロールを表すために使用できる XML ベースの要素です。SDT を優先コントロール タイプとして使用すると、HTML コンテンツの互換性と表現が向上します。

#### Q: HTML ドキュメントを読み込むときに、Aspose.Words が優先コントロール タイプを使用するようにするにはどうすればよいですか?

 A: 設定することで`PreferredControlType`財産に`HtmlControlType.StructuredDocumentTag`サンプル ソース コードに示されているように、Aspose.Words はドキュメントを読み込むときに SDT を使用して HTML 要素を表します。

#### Q: 優先オプションとして他のコントロール タイプを使用できますか?

 A: はい、それ以外は`HtmlControlType.StructuredDocumentTag`Aspose.Words for .NETは、次のような他のコントロールタイプもサポートしています。`HtmlControlType.ContentControl`そして`HtmlControlType.CustomXmlMarkup`.