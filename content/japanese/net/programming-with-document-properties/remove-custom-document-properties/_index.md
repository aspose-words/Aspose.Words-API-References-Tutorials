---
title: カスタムドキュメントプロパティの削除
linktitle: カスタムドキュメントプロパティの削除
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントからカスタム プロパティを削除するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-properties/remove-custom-document-properties/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントからカスタム プロパティを削除するための C# ソース コードを説明します。この機能を使用すると、ドキュメントから特定のカスタム プロパティを削除できます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

この手順では、カスタム プロパティを削除する Word 文書を読み込みます。次のコードを使用してドキュメントをロードします。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが置かれているディレクトリの実際のパスに置き換えます。

## ステップ 3: カスタム プロパティの削除

次に、ドキュメントから特定のカスタム プロパティを削除しましょう。次のコードを使用します。

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

このコードは、ドキュメントから「承認日」カスタム プロパティを削除します。 「承認日」を、削除するカスタム プロパティの名前に置き換えることができます。

### Aspose.Words for .NET を使用してカスタム ドキュメント プロパティを削除するソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

必ず正しいドキュメント パスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントからカスタム プロパティを削除する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、独自のドキュメントからカスタム プロパティを簡単に削除できます。