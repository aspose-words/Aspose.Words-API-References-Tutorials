---
title: 輸出ラウンドトリップ情報
linktitle: 輸出ラウンドトリップ情報
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを HTML として保存するときにラウンドトリップ情報をエクスポートするためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントからラウンドトリップ情報をエクスポートするための C# ソース コードについて説明します。この機能を使用すると、エクスポートされた HTML ファイルにラウンドトリップ情報を含めることができるため、元のドキュメントに加えられた変更を簡単に取得できます。

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

ここで、ドキュメントのラウンドトリップ情報をエクスポートするための HTML 保存オプションを設定します。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

このコードはインスタンスを作成します`HtmlSaveOptions`そして、`ExportRoundtripInformation`オプション`true`エクスポート時にラウンドトリップ情報を含めます。

## ステップ4: ドキュメントをHTMLに変換して保存する

最後に、先ほど設定した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

このコードは、ラウンドトリップ情報を含むドキュメントを HTML に変換し、エクスポートされた HTML ファイルを指定されたディレクトリに保存します。

### Aspose.Words for .NET を使用してラウンドトリップ情報をエクスポートするためのサンプル ソース コード


```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

ドキュメントディレクトリへの正しいパスを必ず指定してください。`dataDir`変数。