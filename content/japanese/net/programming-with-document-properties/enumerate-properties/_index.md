---
title: プロパティを列挙する
linktitle: プロパティを列挙する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント プロパティを列挙するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-properties/enumerate-properties/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメント プロパティを列挙する C# ソース コードについて説明します。この機能を使用すると、ドキュメントの組み込みプロパティとカスタム プロパティにアクセスできます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

この手順では、プロパティを一覧表示する Word 文書を読み込みます。次のコードを使用して文書を読み込みます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが配置されているディレクトリの実際のパスを入力します。

## ステップ3: プロパティの列挙

次に、組み込みプロパティとカスタム プロパティの両方を含むドキュメント プロパティを一覧表示します。次のコードを使用します。

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

このコードはドキュメント名を表示し、組み込みプロパティとカスタム プロパティの名前と値を一覧表示します。

### Aspose.Words for .NET を使用したプロパティの列挙のサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
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

正しいドキュメントパスを必ず指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメント プロパティを列挙する方法を学習しました。このチュートリアルで提供されるステップ バイ ステップ ガイドに従うことで、独自のドキュメントのプロパティに簡単にアクセスして表示できます。

