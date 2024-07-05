---
title: MHTML リソースの CID URL をエクスポートする
linktitle: MHTML リソースの CID URL をエクスポートする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを保存するときに、MHTML リソースの CID URL をエクスポートするためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

このチュートリアルでは、Aspose.Words for .NET を使用して MHTML リソースの CID URL をエクスポートするための C# ソース コードについて説明します。この機能を使用すると、ドキュメントを MHTML 形式で保存するときに、MHTML リソースの CID URL をエクスポートできます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

このステップでは、エクスポートするドキュメントを読み込みます。指定されたディレクトリからドキュメントを読み込むには、次のコードを使用します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

このコードはインスタンスを作成します`Document`指定されたディレクトリからドキュメントを読み込みます。

## ステップ3: HTMLバックアップオプションの設定

ここで、MHTML リソースの CID URL をエクスポートするための HTML 保存オプションを設定します。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

このコードはインスタンスを作成します`HtmlSaveOptions`保存形式をMHTMLに設定することで、MHTMLリソースのCID URLのエクスポートも可能になります。`ExportCidUrlsForMhtmlResources`に`true`.

## ステップ4: ドキュメントをMHTMLに変換して保存する

最後に、先ほど設定した HTML 保存オプションを使用してドキュメントを MHTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

このコードはドキュメントを MHTML に変換し、エクスポートされた MHTML リソースの CID URL を含むファイルに保存します。

### Aspose.Words for .NET を使用して MHTML リソースの Cid Url をエクスポートするためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

ドキュメントディレクトリへの正しいパスを必ず指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントを MHTML 形式で保存するときに、MHTML リソースの CID URL をエクスポートする方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、エクスポートされた MHTML ドキュメント内の CID URL を簡単に管理できます。

