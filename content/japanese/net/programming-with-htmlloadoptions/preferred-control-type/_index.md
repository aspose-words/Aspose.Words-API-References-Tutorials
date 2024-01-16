---
title: Word 文書で優先されるコントロールの種類
linktitle: Word 文書で優先されるコントロールの種類
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して HTML ドキュメントを読み込むときに、Word ドキュメントで優先されるコントロール タイプを指定するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlloadoptions/preferred-control-type/
---
この記事では、Aspose.Words for .NET で優先コントロール タイプ機能を使用する方法について段階的なガイドを提供します。コードの各部分について詳しく説明します。このチュートリアルの最後には、HTML ドキュメントを読み込むときに優先されるコントロールの種類を指定する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで見つけることができます。

## ステップ 1: HTML コードを定義する

まず、ドキュメントとしてロードする HTML コードを定義する必要があります。この例では、`html`オプションを含むセレクターの HTML コードを含む変数。

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

## ステップ 2: HTML 読み込みオプションを設定する

次に、`HtmlLoadOptions`オブジェクトを設定して、`PreferredControlType`財産を`HtmlControlType.StructuredDocumentTag`。これにより、読み込み時に HTML を表すために StructuredDocumentTags を使用するように Aspose.Words に指示されます。

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## ステップ 3: ドキュメントをロードして保存する

私たちが使用するのは、`Document`クラスを使用して、前に定義したロード オプションを使用してメモリ ストリームから HTML コードをロードします。次に、ドキュメントを指定されたディレクトリに保存します。`.docx`ファイル形式。

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Aspose.Words for .NET を使用した優先コントロール タイプのソース コードの例

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

それだけです ！ Aspose.Words for .NET を使用して HTML ドキュメントをロードするときに、優先コントロール タイプを正常に指定しました。

## 結論

このステップバイステップ ガイドに従うことで、Aspose.Words for .NET の「優先コントロール タイプ」機能を使用して、HTML ドキュメントを読み込むときに目的のコントロール タイプを指定する方法を学習しました。の設定`PreferredControlType`財産を`HtmlControlType.StructuredDocumentTag`Aspose.Words は、HTML コンテンツの表現と処理を改善するために StructuredDocumentTags (SDT) を使用できるようになります。特定の要件に合わせて、他のコントロール タイプも検討できます。この機能を使用すると、C# アプリケーションで Aspose.Words を使用して HTML ドキュメントを正確かつ効率的に処理できるようになります。

### Word 文書で優先されるコントロールの種類に関する FAQ

#### Q: Aspose.Words for .NET の「優先コントロール タイプ」機能とは何ですか?

A: 「優先コントロール タイプ」機能を使用すると、HTML ドキュメントを読み込むときに HTML 要素を表すコントロールの優先タイプを指定できます。これは、HTML コンテンツのより適切な表現と処理のために、適切なコントロール タイプを選択するのに役立ちます。

#### Q: HTML ドキュメントをロードするときに優先コントロール タイプを設定するにはどうすればよいですか?

 A: 優先コントロール タイプを設定するには、`HtmlLoadOptions`オブジェクトを設定し、`PreferredControlType`希望のプロパティ`HtmlControlType`。提供された例では、`HtmlControlType.StructuredDocumentTag`使用されている。

#### Q: StructuredDocumentTags (SDT) を優先コントロール タイプとして使用する意義は何ですか?

A: StructuredDocumentTags (SDT) は、Word 文書内の複雑なコンテンツやコントロールを表すために使用できる XML ベースの要素です。 SDT を優先コントロール タイプとして使用すると、HTML コンテンツの互換性と表現が向上します。

#### Q: HTML ドキュメントを読み込むときに、Aspose.Words が優先コントロール タイプを使用するようにするにはどうすればよいですか?

 A: を設定することで、`PreferredControlType`財産を`HtmlControlType.StructuredDocumentTag`サンプル ソース コードに示されているように、Aspose.Words はドキュメントを読み込むときに SDT を使用して HTML 要素を表します。

#### Q: 他のコントロール タイプを優先オプションとして使用できますか?

 A: はい、それとは別に`HtmlControlType.StructuredDocumentTag` Aspose.Words for .NET は、次のような他のコントロール タイプをサポートしています。`HtmlControlType.ContentControl`そして`HtmlControlType.CustomXmlMarkup`.