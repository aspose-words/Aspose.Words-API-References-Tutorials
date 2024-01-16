---
title: 往復情報のエクスポート
linktitle: 往復情報のエクスポート
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを HTML として保存するときにラウンドトリップ情報をエクスポートするためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントからラウンドトリップ情報をエクスポートするための C# ソース コードを説明します。この機能を使用すると、エクスポートされた HTML ファイルにラウンドトリップ情報を含めることができ、元のドキュメントに加えられた変更を簡単に取得できるようになります。

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

次に、ドキュメントのラウンドトリップ情報をエクスポートするための HTML 保存オプションを構成します。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

このコードは、次のインスタンスを作成します。`HtmlSaveOptions`そして、`ExportRoundtripInformation`というオプション`true`エクスポート時にラウンドトリップ情報を含めるには。

## ステップ 4: ドキュメントを HTML に変換して保存する

最後に、前に構成した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

このコードは、ラウンドトリップ情報を含むドキュメントを HTML に変換し、エクスポートされた HTML ファイルを指定されたディレクトリに保存します。

### Aspose.Words for .NET を使用したラウンドトリップ情報のエクスポートのソース コード例


```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

必ずドキュメント ディレクトリへの正しいパスを指定してください。`dataDir`変数。