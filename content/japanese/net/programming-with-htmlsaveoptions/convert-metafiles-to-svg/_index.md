---
title: メタファイルをSVGに変換する
linktitle: メタファイルをSVGに変換する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを HTML に変換するときに、メタファイルを SVG 形式に変換するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

このチュートリアルでは、Aspose.Words for .NET を使用してメタファイルを SVG 形式に変換するための C# ソース コードについて説明します。この機能を使用すると、ドキュメントを HTML に変換するときにメタファイルを SVG 形式に変換できます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントにSVG画像を挿入する

この手順では、変換するドキュメントに SVG 画像を挿入します。HTML タグを使用して SVG 画像を挿入するには、次のコードを使用します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

このコードはインスタンスを作成します`Document`そして`DocumentBuilder`ドキュメントを構築します。`<svg>`タグを含む`<polygon>`SVG 画像の形状とスタイルを定義する属性を持つ要素。

## ステップ3: HTML保存オプションを設定する

ここで、HTML 保存オプションを設定し、メタファイルを SVG 形式に変換するように指定します。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

このコードはインスタンスを作成します`HtmlSaveOptions`そしてセット`MetafileFormat`に`HtmlMetafileFormat.Svg` HTML に変換するときにメタファイルを SVG 形式に変換するように指定します。

## ステップ4: ドキュメントをHTMLに変換して保存する

最後に、先ほど定義した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

このコードはドキュメントを HTML に変換し、メタファイルを SVG に変換したファイルに保存します。

### Aspose.Words for .NET を使用してメタファイルを SVG に変換するためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
