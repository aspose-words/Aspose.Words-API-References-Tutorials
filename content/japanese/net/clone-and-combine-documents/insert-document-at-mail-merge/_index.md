---
title: 差し込み印刷時に文書を挿入
linktitle: 差し込み印刷時に文書を挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、差し込み印刷中にドキュメントを別のドキュメントに挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
このチュートリアルでは、Aspose.Words for .NET の差し込み印刷中にドキュメントを挿入機能を使用して、差し込み印刷中にドキュメントを別のドキュメントに挿入する方法を説明します。以下の手順に従ってソース コードを理解し、ドキュメントの挿入を実行します。

## ステップ 1: メインドキュメントをロードする

まず、ドキュメントのディレクトリを指定し、メインドキュメントを Document オブジェクトにロードします。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## ステップ 2: 差し込み印刷を構成する

次に、差し込み印刷を構成し、文書を別の文書に挿入するためのフィールド差し込みコールバックを指定しましょう。その方法は次のとおりです。

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## ステップ 3: 差し込み印刷の実行

差し込みフィールドの名前と対応するデータを指定して、差し込み印刷を実行します。その方法は次のとおりです。

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Aspose.Words for .NET を使用した差し込み文書挿入のソース コード例

Aspose.Words for .NET の差し込み文書への文書の挿入機能の完全なソース コードを次に示します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
//メイン文書には「Document_1」という差し込みフィールドがあります。
//このフィールドに対応するデータには、ドキュメントへの完全修飾パスが含まれています。
//それをこのフィールドに挿入する必要があります。
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

このコードを使用すると、Aspose.Words for .NET を使用して差し込み印刷中に文書を別の文書に挿入できるようになります。結果のドキュメントは新しい名前で保存されます


## 結論

このチュートリアルでは、Aspose.Words for .NET の差し込み印刷中にドキュメントを挿入機能を使用して、差し込み印刷中にドキュメントを別のドキュメントに挿入する方法を検討しました。差し込み印刷を構成し、必要なデータを提供すると、さまざまな文書テンプレートまたはセクションを結合して動的に文書を組み立てることができます。 Aspose.Words for .NET は、複雑なドキュメント生成シナリオを管理するための柔軟かつ強力な方法を提供し、ドキュメントの作成および操作タスクを自動化するための貴重なツールとなります。

### よくある質問

#### Q: 差し込み印刷中に文書を別の文書に挿入する目的は何ですか?

A: 差し込み印刷中にドキュメントを別のドキュメントに挿入すると、差し込み印刷プロセス中に提供されたデータに基づいて、さまざまなドキュメント テンプレートまたはセクションを動的に組み合わせることができます。この機能は、さまざまな事前定義されたテンプレートまたはセクションを最終ドキュメントにマージして複雑なドキュメントを組み立てる場合に特に便利です。

#### Q: Aspose.Words for .NET を使用して差し込み印刷中に文書を別の文書に挿入するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して差し込み印刷中に文書を別の文書に挿入するには、次の手順に従います。
1. ベースとなるメインドキュメントを Document オブジェクトに読み込みます。
2. 差し込み印刷を構成し、文書の挿入を処理するフィールド差し込みコールバックを指定します。
3. 差し込みフィールドの名前と対応するデータ (挿入する文書へのパス) を使用して差し込み印刷を実行します。

#### Q: 差し込み印刷中の挿入動作をカスタマイズするにはどうすればよいですか?

A: 差し込み印刷中の挿入動作をカスタマイズするには、IFieldMergingCallback インターフェイスから継承してカスタム FieldMergingCallback を実装できます。これにより、特定の要件に基づいてドキュメントの挿入および結合方法を制御できます。

#### Q: 差し込み印刷中に複数の文書を挿入できますか?

A: はい、各差し込みフィールドに適切なデータを指定することで、差し込み印刷中に複数の文書を挿入できます。ドキュメントの挿入が必要な差し込みフィールドごとに、対応するドキュメントへのパスをデータとして指定します。


