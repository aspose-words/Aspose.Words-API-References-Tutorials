---
title: テキスト入力フォームフィールドをテキストとしてエクスポート
linktitle: テキスト入力フォームフィールドをテキストとしてエクスポート
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してテキスト入力フォーム フィールドをプレーン テキストとしてエクスポートするためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

このチュートリアルでは、Aspose.Words for .NET を使用してテキスト入力フォーム フィールドをプレーン テキストとしてエクスポートするための C# ソース コードを説明します。この機能を使用すると、テキスト入力フォーム フィールドを HTML 入力要素としてエクスポートするのではなく、読み取り可能なテキストとしてエクスポートできます。

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

次に、テキスト入力フォームフィールドをプレーンテキストとしてエクスポートするように HTML 保存オプションを構成します。次のコードを使用します。

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

//指定したフォルダーは存在し、空である必要があります。
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

このコードは、次のインスタンスを作成します。`HtmlSaveOptions`そして、`ExportTextInputFormFieldAsText`というオプション`true`テキスト入力フォームフィールドをプレーンテキストとしてエクスポートします。さらに、抽出した画像を保存するフォルダーを指定します。

## ステップ 4: ドキュメントを HTML に変換して保存する

最後に、前に構成した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

このコードは、テキスト入力フォーム フィールドをプレーン テキストとしてエクスポートすることでドキュメントを HTML に変換し、エクスポートされた HTML ファイルを指定されたディレクトリに保存します。

### Aspose.Words for .NET を使用してテキスト入力フォーム フィールドをテキストとしてエクスポートするソース コードの例


```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	//指定されたフォルダーは存在する必要があり、空である必要があります。
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	//フォームフィールドを HTML 入力要素ではなくプレーンテキストとしてエクスポートするオプションを設定します。
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

必ずドキュメント ディレクトリへの正しいパスを指定してください。`dataDir`変数。