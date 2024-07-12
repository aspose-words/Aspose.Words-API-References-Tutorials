---
title: 変数を取得する
linktitle: 変数を取得する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント変数を取得するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-properties/get-variables/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントから変数を取得するための C# ソース コードについて説明します。この機能を使用すると、ドキュメントで定義された変数にアクセスできます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

この手順では、変数を取得する Word 文書を読み込みます。次のコードを使用して文書を読み込みます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが配置されているディレクトリの実際のパスを入力します。

## ステップ3: 変数の取得

次に、ドキュメントで定義された変数を取得します。次のコードを使用します。

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

このコードは、ドキュメント変数内の各キーと値のペアを反復処理し、各変数の名前と値を取得します。その後、変数が連結され、各変数の情報が表示されます。

### Aspose.Words for .NET を使用して変数を取得するためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

必ず正しいドキュメントパスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントから変数を取得する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、自分のドキュメントから変数に簡単にアクセスして表示できます。