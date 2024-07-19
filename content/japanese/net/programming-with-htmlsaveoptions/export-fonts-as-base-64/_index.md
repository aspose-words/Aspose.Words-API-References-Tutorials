---
title: フォントをBase64としてエクスポート
linktitle: フォントをBase64としてエクスポート
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを保存するときに、Base 64 フォントをエクスポートするためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Base 64 フォントをエクスポートするための C# ソース コードについて説明します。この機能を使用すると、ドキュメントを HTML 形式で保存するときに、フォントを Base 64 データとしてエクスポートできます。

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

ここで、HTML 保存オプションを設定して、Base 64 フォントをエクスポートします。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

このコードはインスタンスを作成します`HtmlSaveOptions`そしてセット`ExportFontsAsBase64`に`true` HTML として保存するときにフォントを Base 64 データとしてエクスポートするように指定します。

## ステップ4: ドキュメントをHTMLに変換して保存する

最後に、先ほど設定した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

このコードはドキュメントを HTML に変換し、フォントを Base 64 データとしてエクスポートしたファイルに保存します。

### Aspose.Words for .NET を使用してフォントを Base 64 としてエクスポートするためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

ドキュメントディレクトリへの正しいパスを必ず指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントを HTML として保存するときに、Base 64 フォントをエクスポートする方法を学習しました。このチュートリアルで説明されているステップバイステップのガイドに従うことで、フォントを安全にエクスポートし、HTML ドキュメントに埋め込むことが簡単にできます。