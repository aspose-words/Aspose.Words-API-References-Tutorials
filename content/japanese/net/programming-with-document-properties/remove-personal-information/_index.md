---
title: 個人情報を削除する
linktitle: 個人情報を削除する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントから個人情報を削除するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-properties/remove-personal-information/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントから個人情報を削除する C# ソース コードについて説明します。この機能を使用すると、作成者識別データなどの機密性の高い個人情報をドキュメントから削除できます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

このステップでは、個人情報を削除する Word 文書をアップロードします。次のコードを使用して文書を読み込みます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが配置されているディレクトリの実際のパスを入力します。

## ステップ3: 個人情報を削除する

ここで、個人情報の削除を有効にするには、`RemovePersonalInformation`財産に`true`次のコードを使用します。

```csharp
doc.RemovePersonalInformation = true;
```

このコードは、文書内の個人情報の削除を有効にします。

## ステップ4: ドキュメントを保存する

最後に、個人情報を削除したドキュメントを保存します。次のコードを使用します。

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

このコードは、個人情報を削除したドキュメントを新しいファイルに保存します。

### Aspose.Words for .NET を使用して個人情報を削除するサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

必ず正しいドキュメントパスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントから個人情報を削除する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、自分のドキュメントから機密情報を簡単に削除できます。