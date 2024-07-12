---
title: カスタムドキュメントプロパティを削除する
linktitle: カスタムドキュメントプロパティを削除する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントからカスタム プロパティを削除するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-properties/remove-custom-document-properties/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントからカスタム プロパティを削除するための C# ソース コードについて説明します。この機能を使用すると、ドキュメントから特定のカスタム プロパティを削除できます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

この手順では、カスタム プロパティを削除する Word 文書を読み込みます。次のコードを使用して文書を読み込みます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが配置されているディレクトリの実際のパスを入力します。

## ステップ3: カスタムプロパティの削除

次に、ドキュメントから特定のカスタム プロパティを削除してみましょう。次のコードを使用します。

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

このコードは、ドキュメントから「承認日」カスタム プロパティを削除します。「承認日」は、削除するカスタム プロパティの名前に置き換えることができます。

### Aspose.Words for .NET を使用してカスタム ドキュメント プロパティを削除するサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

必ず正しいドキュメントパスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントからカスタム プロパティを削除する方法を学習しました。このチュートリアルで提供されるステップ バイ ステップ ガイドに従うことで、独自のドキュメントからカスタム プロパティを簡単に削除できます。