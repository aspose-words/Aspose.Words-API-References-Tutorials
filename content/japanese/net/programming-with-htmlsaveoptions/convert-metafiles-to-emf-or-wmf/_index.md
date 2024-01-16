---
title: メタファイルを Emf または Wmf に変換
linktitle: メタファイルを Emf または Wmf に変換
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを HTML に変換する際に、メタファイルを EMF または WMF 形式に変換するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

このチュートリアルでは、Aspose.Words for .NET を使用してメタファイルを EMF または WMF 形式に変換するための C# ソース コードを説明します。この機能を使用すると、ドキュメントを HTML に変換するときに、メタファイル形式の画像を EMF や WMF などのより互換性のある形式に変換できます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントに画像を挿入する

このステップでは、変換するドキュメントに画像を挿入します。 HTML タグを使用してデータ ソースから画像を挿入するには、次のコードを使用します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

このコードは、次のインスタンスを作成します。`Document`そして`DocumentBuilder`ドキュメントを作成します。それは、`<img>` Base64 でエンコードされた画像を含むドキュメントにタグを追加します。

## ステップ 3: HTML 保存オプションを設定する

次に、画像に使用するメタファイル形式を含む HTML 保存オプションを設定します。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

このコードは、次のインスタンスを作成します。`HtmlSaveOptions`とセット`MetafileFormat`に`HtmlMetafileFormat.EmfOrWmf` HTML に変換するときにメタファイルを EMF または WMF 形式に変換するように指定します。

## ステップ 4: ドキュメントを HTML に変換して保存する

最後に、前に定義した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

このコードは、ドキュメントを HTML に変換し、保存オプションの設定に応じて、変換されたメタファイルとともに EMF または WMF 形式でファイルに保存します。

### Aspose.Words for .NET を使用してメタファイルを Emf または Wmf に変換するソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

必ずドキュメント ディレクトリへの正しいパスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントを HTML に変換するときに、メタファイルを EMF または WMF 形式に変換する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、変換された HTML ドキュメント内のメタファイルを簡単に管理できます。