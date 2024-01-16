---
title: 変数の取得
linktitle: 変数の取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント変数を取得するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-properties/get-variables/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントから変数を取得するための C# ソース コードを説明します。この機能を使用すると、ドキュメント内で定義された変数にアクセスできます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

このステップでは、変数を取得する Word 文書を読み込みます。次のコードを使用してドキュメントをロードします。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが置かれているディレクトリの実際のパスに置き換えます。

## ステップ 3: 変数の取得

次に、ドキュメントで定義されている変数を取得します。次のコードを使用します。

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

このコードは、ドキュメント変数内の各キーと値のペアを反復処理し、各変数の名前と値を取得します。次に、変数が連結されて各変数の情報が表示されます。

### Aspose.Words for .NET を使用した変数の取得のソース コード例

```csharp

	//ドキュメントディレクトリへのパス。
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

必ず正しいドキュメント パスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントから変数を取得する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、独自のドキュメントの変数に簡単にアクセスして表示できます。