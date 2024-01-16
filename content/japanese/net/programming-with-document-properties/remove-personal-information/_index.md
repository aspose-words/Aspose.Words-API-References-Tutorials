---
title: 個人情報の削除
linktitle: 個人情報の削除
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントから個人情報を削除するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-properties/remove-personal-information/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントから個人情報を削除するための C# ソース コードを説明します。この機能を使用すると、作成者識別データなどの機密の個人情報をドキュメントから削除できます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

このステップでは、個人情報を削除する Word 文書をアップロードします。次のコードを使用してドキュメントをロードします。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが置かれているディレクトリの実際のパスに置き換えます。

## ステップ 3: 個人情報を削除する

次に、設定して個人情報の削除を有効にします。`RemovePersonalInformation`財産を`true`。次のコードを使用します。

```csharp
doc.RemovePersonalInformation = true;
```

このコードは、文書内の個人情報の削除を有効にします。

## ステップ 4: ドキュメントを保存する

最後に、個人情報を削除して文書を保存します。次のコードを使用します。

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

このコードは、個人情報が削除されたドキュメントを新しいファイルに保存します。

### Aspose.Words for .NET を使用して個人情報を削除するためのソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

必ず正しいドキュメント パスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントから個人情報を削除する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、自分のドキュメントから機密情報を簡単に削除できます。