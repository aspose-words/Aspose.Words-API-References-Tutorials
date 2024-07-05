---
title: テキスト入力フォームフィールドをテキストとしてエクスポート
linktitle: テキスト入力フォームフィールドをテキストとしてエクスポート
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してテキスト入力フォーム フィールドをプレーン テキストとしてエクスポートするためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

このチュートリアルでは、Aspose.Words for .NET を使用してテキスト入力フォーム フィールドをプレーン テキストとしてエクスポートするための C# ソース コードについて説明します。この機能を使用すると、テキスト入力フォーム フィールドを HTML 入力要素としてエクスポートするのではなく、読み取り可能なテキストとしてエクスポートできます。

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

ここで、テキスト入力フォーム フィールドをプレーン テキストとしてエクスポートするための HTML 保存オプションを設定します。次のコードを使用します。

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

//指定されたフォルダーは存在し、空である必要があります。
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

このコードはインスタンスを作成します`HtmlSaveOptions`そして、`ExportTextInputFormFieldAsText`オプション`true`テキスト入力フォームフィールドをプレーンテキストとしてエクスポートします。さらに、抽出された画像が保存されるフォルダーを指定します。

## ステップ4: ドキュメントをHTMLに変換して保存する

最後に、先ほど設定した HTML 保存オプションを使用してドキュメントを HTML に変換します。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

このコードは、テキスト入力フォーム フィールドをプレーン テキストとしてエクスポートしてドキュメントを HTML に変換し、エクスポートされた HTML ファイルを指定されたディレクトリに保存します。

### Aspose.Words for .NET を使用してテキスト入力フォーム フィールドをテキストとしてエクスポートするためのサンプル ソース コード


```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	//指定されたフォルダーは存在している必要があり、空である必要があります。
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	//フォーム フィールドを HTML 入力要素ではなくプレーン テキストとしてエクスポートするオプションを設定します。
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

ドキュメントディレクトリへの正しいパスを必ず指定してください。`dataDir`変数。