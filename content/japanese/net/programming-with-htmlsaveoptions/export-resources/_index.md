---
title: リソースのエクスポート
linktitle: リソースのエクスポート
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して HTML として保存するときにドキュメント リソースをエクスポートするためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/export-resources/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメント リソースをエクスポートするための C# ソース コードについて説明します。この機能を使用すると、ドキュメントを HTML 形式で保存するときに、フォントなどのリソースを外部ファイルとしてエクスポートできます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

このステップでは、エクスポートするドキュメントを読み込みます。指定されたディレクトリからドキュメントを読み込むには、次のコードを使用します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

このコードはインスタンスを作成します`Document`指定されたディレクトリからドキュメントを読み込みます。

## ステップ3: HTMLバックアップオプションの設定

ここで、ドキュメント リソースをエクスポートするための HTML 保存オプションを設定します。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources"
};
```

このコードはインスタンスを作成します`HtmlSaveOptions`次のオプションを設定します。

- `CssStyleSheetType`に設定されています`CssStyleSheetType.External`CSS スタイルシートを外部ファイルにエクスポートします。
- `ExportFontResources`に設定されています`true`フォントリソースをエクスポートします。
- `ResourceFolder`リソースを保存する宛先ディレクトリを指定します。
- `ResourceFolderAlias`リソースにアクセスするために使用する URL エイリアスを指定します。

## ステップ4: ドキュメントをHTMLに変換して保存する

最後に、先ほど設定した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

このコードは、ドキュメントを HTML に変換し、指定された URL エイリアスを使用して、指定されたディレクトリにリソースを保存します。

### Aspose.Words for .NET を使用してリソースをエクスポートするためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

ドキュメントディレクトリへの正しいパスを必ず指定してください。`dataDir`変数。