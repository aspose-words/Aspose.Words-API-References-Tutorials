---
title: プロパティを列挙する
linktitle: プロパティを列挙する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント プロパティを列挙するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-properties/enumerate-properties/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメント プロパティを列挙するための C# ソース コードを説明します。この機能を使用すると、ドキュメントの組み込みプロパティとカスタム プロパティにアクセスできます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

このステップでは、プロパティを一覧表示する Word 文書を読み込みます。次のコードを使用してドキュメントをロードします。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが置かれているディレクトリの実際のパスに置き換えます。

## ステップ 3: プロパティを列挙する

次に、ドキュメント プロパティ (組み込みプロパティとカスタム プロパティの両方) をリストしてみましょう。次のコードを使用します。

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

このコードはドキュメント名を表示し、次に組み込みプロパティとカスタム プロパティをリストし、それらの名前と値を表示します。

### Aspose.Words for .NET を使用したプロパティの列挙のソース コード例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

必ず正しいドキュメント パスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメント プロパティを列挙する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、独自のドキュメントのプロパティに簡単にアクセスして表示できます。

