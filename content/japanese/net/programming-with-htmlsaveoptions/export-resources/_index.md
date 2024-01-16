---
title: リソースのエクスポート
linktitle: リソースのエクスポート
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して HTML として保存するときにドキュメント リソースをエクスポートするためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/export-resources/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメント リソースをエクスポートするための C# ソース コードを説明します。この機能を使用すると、ドキュメントを HTML 形式で保存するときに、フォントなどのリソースを外部ファイルとしてエクスポートできます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

このステップでは、エクスポートするドキュメントをロードします。次のコードを使用して、指定したディレクトリからドキュメントをロードします。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

このコードは、次のインスタンスを作成します。`Document`指定されたディレクトリからドキュメントをロードします。

## ステップ 3: HTML バックアップ オプションの構成

次に、ドキュメント リソースをエクスポートするための HTML 保存オプションを構成します。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources"
};
```

このコードは、次のインスタンスを作成します。`HtmlSaveOptions`そして、次のオプションを設定します。

- `CssStyleSheetType`に設定されています`CssStyleSheetType.External`CSS スタイル シートを外部ファイルにエクスポートします。
- `ExportFontResources`に設定されています`true`フォントリソースをエクスポートします。
- `ResourceFolder`リソースが保存される宛先ディレクトリを指定します。
- `ResourceFolderAlias`リソースへのアクセスに使用される URL エイリアスを指定します。

## ステップ 4: ドキュメントを HTML に変換して保存する

最後に、前に構成した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

このコードは、ドキュメントを HTML に変換し、指定された URL エイリアスを使用して、指定されたディレクトリにリソースを保存します。

### Aspose.Words for .NET を使用したエクスポート リソースのソース コード例

```csharp

	//ドキュメントディレクトリへのパス。
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

必ずドキュメント ディレクトリへの正しいパスを指定してください。`dataDir`変数。