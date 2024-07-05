---
title: 画像フォルダの設定
linktitle: 画像フォルダの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Markdown にエクスポートするときに画像フォルダーを設定する方法を学びます。画像の配置をカスタマイズして、整理と統合を改善します。
type: docs
weight: 10
url: /ja/net/programming-with-markdownsaveoptions/set-images-folder/
---

ここでは、.NET 用の Aspose.Words ライブラリを使用して Markdown エクスポート オプションの画像フォルダーを設定するのに役立つ次の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。このコードを使用する前に、プロジェクトに Aspose.Words ライブラリが含まれていることを確認してください。

## ステップ1: ドキュメントディレクトリのパスを設定する

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

画像を含むドキュメントが保存されているドキュメント ディレクトリへの正しいパスを必ず指定してください。

## ステップ2: 画像を含むドキュメントを読み込む

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Markdown オプションを使用してエクスポートする画像を含む指定されたドキュメントを読み込みます。

## ステップ3: Markdownエクスポートオプションの画像フォルダを設定する

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

インスタンスを作成します`MarkdownSaveOptions`そして、画像フォルダへのパスを`ImagesFolder`プロパティ。エクスポートした画像を保存するフォルダーへの正しいパスを指定してください。

## ステップ4: Markdownエクスポートオプションを使用してドキュメントを保存する

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

指定された Markdown エクスポート オプションを使用して、ドキュメントをメモリ ストリームに保存します。その後、フローを使用して、Markdown コンテンツをファイルに保存するなどの他の操作を実行できます。

### Aspose.Words for .NET を使用して MarkdownSaveOptions の画像フォルダーを設定するサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

このソース コードは、画像を含むドキュメントを読み込み、Markdown エクスポート オプションの画像フォルダーを設定する方法を示しています。指定されたオプションを使用して、ドキュメントはメモリ ストリームに保存されます。これにより、Markdown コンテンツをエクスポートするときに画像フォルダーの場所をカスタマイズできます。