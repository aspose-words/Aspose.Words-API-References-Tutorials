---
title: フォントをBase 64としてエクスポート
linktitle: フォントをBase 64としてエクスポート
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET でドキュメントを保存するときに Base 64 フォントをエクスポートするためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Base 64 フォントをエクスポートするための C# ソース コードを説明します。この機能を使用すると、ドキュメントを HTML 形式で保存するときにフォントを Base 64 データとしてエクスポートできます。

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

次に、Base 64 フォントをエクスポートするように HTML 保存オプションを構成します。次のコードを使用します。

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

このコードは、次のインスタンスを作成します。`HtmlSaveOptions`とセット`ExportFontsAsBase64`に`true` HTML として保存するときにフォントを Base 64 データとしてエクスポートするように指定します。

## ステップ 4: ドキュメントを HTML に変換して保存する

最後に、前に構成した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

このコードは、ドキュメントを HTML に変換し、Base 64 データとしてエクスポートされたフォントとともにファイルに保存します。

### Aspose.Words for .NET を使用してフォントを Base 64 としてエクスポートするソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

必ずドキュメント ディレクトリへの正しいパスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントを HTML として保存するときに、Base 64 フォントをエクスポートする方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、フォントを安全にエクスポートして HTML ドキュメントに埋め込むことが簡単にできます。