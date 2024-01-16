---
title: Word文書の段落に枠線と網掛けを適用する
linktitle: Word文書の段落に枠線と網掛けを適用する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書の段落に枠線と網かけを適用する方法を学びます。
type: docs
weight: 10
url: /ja/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
このチュートリアルでは、Aspose.Words for .NET の機能を使用して Word 文書の段落に枠線と網掛けを適用する方法を説明します。以下の手順に従って、ソース コードを理解し、書式設定の変更を適用します。

## ステップ 1: ドキュメントの作成と構成

まず、新しいドキュメントと関連する DocumentBuilder オブジェクトを作成します。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: 境界線の設定

次に、各辺の境界線のスタイルを指定して、段落の境界線を設定しましょう。その方法は次のとおりです。

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## ステップ 3: インフィルのセットアップ

次に、テクスチャと塗りつぶしの色を指定して、段落の塗りつぶしを構成します。その方法は次のとおりです。

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## ステップ 4: コンテンツを追加する

書式設定されたコンテンツを段落に追加します。その方法は次のとおりです。

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## ステップ 3: ドキュメントを保存する

テキスト入力フォームフィールドを挿入した後、`Save`方法。必ず適切なファイル パスを指定してください。

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Aspose.Words for .NET を使用して段落に枠線と網掛けを適用するソース コードの例

Aspose.Words for .NET を使用した段落への境界線とシェーディングの適用機能の完全なソース コードは次のとおりです。

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書の段落に枠線と網掛けを適用する方法を学習しました。段落の設定により、`Borders`そして`Shading`プロパティを使用して、段落の境界線のスタイル、線の色、塗りつぶしの色を設定できました。 Aspose.Words for .NET は、段落の外観をカスタマイズし、ドキュメントの視覚的表現を強化するための強力な書式設定機能を提供します。

### よくある質問

#### Q: Aspose.Words for .NET を使用して Word 文書の段落に枠線と網掛けを適用するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書の段落に枠線と網掛けを適用するには、次の手順に従います。
1. 新しいドキュメントを作成し、`DocumentBuilder`物体。
2. にアクセスして段落の境界線を設定します。`Borders`の財産`ParagraphFormat`各辺の境界線のスタイルを設定します。
3. にアクセスして段落の塗りつぶしを設定します。`Shading`の財産`ParagraphFormat`そしてテクスチャと塗りつぶしの色を指定します。
4. を使用して段落にコンテンツを追加します。`Write`の方法`DocumentBuilder`.
5. を使用して文書を保存します。`Save`方法。

#### Q: 段落の各辺の境界線スタイルを設定するにはどうすればよいですか?

 A: 段落の各辺の境界線スタイルを設定するには、`Borders`の財産`ParagraphFormat`そして、`LineStyle`それぞれのプロパティ`BorderType`（例えば、`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom`）。次のようなさまざまな線スタイルを指定できます。`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`、など。

#### Q: 段落のシェーディングのテクスチャと塗りつぶしの色を指定するにはどうすればよいですか?

 A: 段落のシェーディングのテクスチャと塗りつぶしの色を指定するには、`Shading`の財産`ParagraphFormat`そして、`Texture`プロパティを必要なテクスチャ インデックスに設定します (例:`TextureIndex.TextureDiagonalCross` ）。を設定することもできます`BackgroundPatternColor`そして`ForegroundPatternColor`を使用してプロパティを目的の色に変更します。`System.Drawing.Color`クラス。