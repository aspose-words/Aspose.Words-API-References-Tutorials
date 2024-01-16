---
title: Mhtml リソースの CID URL をエクスポートする
linktitle: Mhtml リソースの CID URL をエクスポートする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET でドキュメントを保存するときに MHTML リソースの CID URL をエクスポートするためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

このチュートリアルでは、Aspose.Words for .NET を使用して MHTML リソースの CID URL をエクスポートするための C# ソース コードを説明します。この機能を使用すると、ドキュメントを MHTML 形式で保存するときに、MHTML リソースの CID URL をエクスポートできます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

このステップでは、エクスポートするドキュメントをロードします。次のコードを使用して、指定したディレクトリからドキュメントをロードします。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

このコードは、次のインスタンスを作成します。`Document`指定されたディレクトリからドキュメントをロードします。

## ステップ 3: HTML バックアップ オプションの構成

次に、MHTML リソースの CID URL をエクスポートするための HTML 保存オプションを構成します。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

このコードは、次のインスタンスを作成します。`HtmlSaveOptions`保存形式は MHTML に設定されています。また、設定により MHTML リソースの CID URL のエクスポートも有効になります。`ExportCidUrlsForMhtmlResources`に`true`.

## ステップ 4: ドキュメントを MHTML に変換して保存する

最後に、前に構成した HTML 保存オプションを使用してドキュメントを MHTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

このコードは、ドキュメントを MHTML に変換し、エクスポートされた MHTML リソースの CID URL を含むファイルに保存します。

### Aspose.Words for .NET を使用した Mhtml リソースの CID URL のエクスポートのソース コード例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

必ずドキュメント ディレクトリへの正しいパスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントを MHTML 形式で保存するときに、MHTML リソースの CID URL をエクスポートする方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、エクスポートされた MHTML ドキュメント内の CID URL を簡単に管理できます。

