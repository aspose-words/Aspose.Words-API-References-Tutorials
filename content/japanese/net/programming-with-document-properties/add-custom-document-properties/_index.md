---
title: カスタムドキュメントプロパティを追加する
linktitle: カスタムドキュメントプロパティを追加する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントにカスタム プロパティを追加するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-properties/add-custom-document-properties/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントにカスタム プロパティを追加するための C# ソース コードについて説明します。この機能を使用すると、ドキュメントにカスタム情報を追加できます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

この手順では、カスタム プロパティを追加する Word 文書を読み込みます。次のコードを使用して文書を読み込みます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが配置されているディレクトリの実際のパスを入力します。

## ステップ3: カスタムプロパティを追加する

次に、ドキュメントにカスタム プロパティを追加してみましょう。プロパティを追加するには、次のコードを使用します。

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

このコードは、まずカスタム プロパティに「承認済み」プロパティが既に存在するかどうかを確認します。存在する場合、プロセスは中断されます。存在しない場合、カスタム プロパティがドキュメントに追加されます。

### Aspose.Words for .NET を使用してカスタム ドキュメント プロパティを追加するためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
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

正しいドキュメントパスを必ず指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントにカスタム プロパティを追加する方法を学習しました。このチュートリアルで提供されるステップ バイ ステップ ガイドに従うことで、独自のカスタム プロパティをドキュメントに簡単に追加できます。