---
title: Word文書の文書保護を削除する
linktitle: Word文書の文書保護を削除する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書の保護を削除する方法を学びます。
type: docs
weight: 10
url: /ja/net/document-protection/remove-document-protection/
---
このチュートリアルでは、Aspose.Words for .NET のドキュメントの保護解除機能を使用する手順を説明します。この機能を使用すると、Word 文書の保護を解除して、さらに編集できるようにすることができます。以下の手順に従います。

## ステップ 1: ドキュメントの作成とコンテンツの追加

まず、Document クラスのインスタンスと DocumentBuilder オブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: ドキュメントにコンテンツを追加する

DocumentBuilder オブジェクトを使用して、ドキュメントにコンテンツを追加します。

```csharp
builder.Writeln("Text added to a document.");
```

## ステップ 3: ドキュメントの保護を解除する

ドキュメントの保護を解除するには、Document オブジェクトの Unprotect() メソッドを使用できます。パスワードを使用せずに保護を解除するか、正しいパスワードを使用して保護を解除するかを選択できます。パスワードなしの保護を削除する:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

必ず「newPassword」を正しいドキュメントのパスワードに置き換えてください。

## ステップ 4: 文書を保護せずに保存する

最後に、Document オブジェクトの Save() メソッドを使用して、ドキュメントを保護せずに保存します。

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

ドキュメントを保護せずに保存するには、必ず正しいパスとファイル名を指定してください。

### Aspose.Words for .NET を使用したドキュメント保護の削除のソース コード例

Aspose.Words for .NET を使用してドキュメントの保護を解除するための完全なソース コードを次に示します。

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Text added to a document.");

//ドキュメントは、パスワードを使用せずに保護を解除することも、正しいパスワードを使用して保護を解除することもできます。
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");

doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

次の手順に従うと、Aspose.Words for .NET を使用して Word 文書から保護を簡単に削除できます。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書の文書保護を削除する方法を検討しました。表示された手順に従うことで、ドキュメントの保護を簡単に解除し、さらに編集できるようにすることができます。 Aspose.Words for .NET は、ドキュメント保護設定を操作し、Word ドキュメントのセキュリティ レベルをカスタマイズできる強力な API を提供します。文書の保護を解除すると、必要に応じて文書の内容や書式を柔軟に変更できるようになります。

### Word 文書の文書保護を解除するための FAQ

#### Q: Aspose.Words for .NET のドキュメント保護とは何ですか?

A: Aspose.Words for .NET のドキュメント保護とは、Word ドキュメントにセキュリティ対策を適用して、編集、書式設定、コンテンツの変更を制限できる機能を指します。これは、文書の完全性と機密性を確保するのに役立ちます。

#### Q: Aspose.Words for .NET を使用してドキュメントの保護を削除するにはどうすればよいですか?

A: Aspose.Words for .NET を使用してドキュメントの保護を削除するには、次の手順に従います。
1. のインスタンスを作成します。`Document`クラスと`DocumentBuilder`物体。
2. 使用`DocumentBuilder`ドキュメントにコンテンツを追加します。
3. 電話してください`Unprotect`の方法`Document`オブジェクトを使用して、ドキュメントから既存の保護を削除します。これは、パスワードを使用せずに行うことも、正しいパスワードを入力することによっても行うことができます。
4. 保護されていないドキュメントを保存するには、`Save`の方法`Document`物体。

#### Q: パスワードを使用せずに Word 文書の保護を解除できますか?

 A: はい、Aspose.Words for .NET を使用すると、パスワードなしで Word 文書から保護を削除できます。電話をかけることで、`Unprotect`の方法`Document`パスワードを指定せずにオブジェクトを削除すると、以前にパスワードなしで保護されていたドキュメントの保護を解除できます。

#### Q: Word 文書からパスワードによる保護を解除するにはどうすればよいですか?

 A: パスワードで保護された Word 文書から保護を解除するには、電話をかけるときに正しいパスワードを入力する必要があります。`Unprotect`の方法`Document`物体。これにより、正しいパスワードを持つユーザーのみが保護を解除してドキュメントにアクセスして編集できるようになります。

#### Q: Word 文書から特定の保護タイプを削除できますか?

 A: はい、Aspose.Words for .NET を使用すると、Word 文書から特定の保護タイプを選択的に削除できます。電話をかけることで、`Unprotect`の方法`Document`オブジェクトを削除すると、他の保護タイプをそのまま残したまま、読み取り専用保護やフォーム保護などの目的の保護タイプを削除できます。