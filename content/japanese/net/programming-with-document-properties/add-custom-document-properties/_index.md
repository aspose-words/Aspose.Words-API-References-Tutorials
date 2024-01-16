---
title: カスタムドキュメントプロパティの追加
linktitle: カスタムドキュメントプロパティの追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してカスタム プロパティをドキュメントに追加するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-properties/add-custom-document-properties/
---

このチュートリアルでは、Aspose.Words for .NET を使用してカスタム プロパティをドキュメントに追加するための C# ソース コードを説明します。この機能を使用すると、ドキュメントにカスタム情報を追加できます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

このステップでは、カスタム プロパティを追加する Word 文書を読み込みます。次のコードを使用してドキュメントをロードします。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが置かれているディレクトリの実際のパスに置き換えます。

## ステップ 3: カスタム プロパティを追加する

次に、カスタム プロパティをドキュメントに追加しましょう。次のコードを使用してプロパティを追加します。

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

このコードは、まず「Authorized」プロパティがカスタム プロパティにすでに存在するかどうかを確認します。存在する場合、プロセスは中断されます。それ以外の場合は、カスタム プロパティがドキュメントに追加されます。

### Aspose.Words for .NET を使用してカスタム ドキュメント プロパティを追加するソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

必ず正しいドキュメント パスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントにカスタム プロパティを追加する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、独自のカスタム プロパティをドキュメントに簡単に追加できます。