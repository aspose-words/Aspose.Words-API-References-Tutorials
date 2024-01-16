---
title: 画像フォルダーの設定
linktitle: 画像フォルダーの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Markdown にエクスポートするときに画像フォルダーを設定する方法を学習します。画像の配置をカスタマイズして、整理と統合を改善します。
type: docs
weight: 10
url: /ja/net/programming-with-markdownsaveoptions/set-images-folder/
---

ここでは、.NET 用の Aspose.Words ライブラリを使用して Markdown エクスポート オプションの画像フォルダーを設定するのに役立つ次の C# ソース コードを説明するステップバイステップ ガイドを示します。このコードを使用する前に、プロジェクトに Aspose.Words ライブラリが含まれていることを確認してください。

## ステップ 1: ドキュメント ディレクトリ パスを設定する

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

画像を含むドキュメントが配置されているドキュメント ディレクトリへの正しいパスを必ず指定してください。

## ステップ 2: 画像を含むドキュメントをロードする

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Markdown オプションを使用して、エクスポートする画像を含む指定されたドキュメントを読み込みます。

## ステップ 3: Markdown エクスポート オプションの画像フォルダーを設定する

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

のインスタンスを作成します`MarkdownSaveOptions`そして、画像フォルダーへのパスを設定します。`ImagesFolder`財産。エクスポートした画像を保存するフォルダーへの正しいパスを必ず指定してください。

## ステップ 4: Markdown エクスポート オプションを使用してドキュメントを保存する

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

指定された Markdown エクスポート オプションを使用して、ドキュメントをメモリ ストリームに保存します。その後、フローを使用して、Markdown コンテンツをファイルに保存するなど、他の操作を実行できます。

### Aspose.Words for .NET で MarkdownSaveOptions の画像フォルダーを設定するソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

このソース コードは、画像を含むドキュメントをロードし、Markdown エクスポート オプションの画像フォルダーを設定する方法を示しています。指定されたオプションを使用して、ドキュメントはメモリ ストリームに保存されます。これにより、Markdown コンテンツをエクスポートするときに画像フォルダーの場所をカスタマイズできます。