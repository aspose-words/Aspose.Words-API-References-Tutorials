---
title: メタファイルをSVGに変換
linktitle: メタファイルをSVGに変換
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを HTML に変換する際に、メタファイルを SVG 形式に変換するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

このチュートリアルでは、Aspose.Words for .NET を使用してメタファイルを SVG 形式に変換するための C# ソース コードを説明します。この機能を使用すると、ドキュメントを HTML に変換するときにメタファイルを SVG 形式に変換できます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: SVG 画像をドキュメントに挿入する

このステップでは、変換するドキュメントに SVG 画像を挿入します。 HTML タグを使用して SVG 画像を挿入するには、次のコードを使用します。

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

このコードは、次のインスタンスを作成します。`Document`そして`DocumentBuilder`ドキュメントを作成します。を挿入します`<svg>`を含むタグ`<polygon>`SVG 画像の形状とスタイルを定義する属性を持つ要素。

## ステップ 3: HTML 保存オプションを設定する

次に、HTML 保存オプションを設定して、メタファイルを SVG 形式に変換するように指定します。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

このコードは、次のインスタンスを作成します。`HtmlSaveOptions`とセット`MetafileFormat`に`HtmlMetafileFormat.Svg` HTML に変換するときにメタファイルを SVG 形式に変換するように指定します。

## ステップ 4: ドキュメントを HTML に変換して保存する

最後に、前に定義した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

このコードはドキュメントを HTML に変換し、SVG に変換されたメタファイルとともにファイルに保存します。

### Aspose.Words for .NET を使用してメタファイルを Svg に変換するソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
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
