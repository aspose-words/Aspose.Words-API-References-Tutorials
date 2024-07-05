---
title: Word文書の文書保護を解除する
linktitle: Word文書の文書保護を解除する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書の保護を解除する方法を学習します。
type: docs
weight: 10
url: /ja/net/document-protection/remove-document-protection/
---
このチュートリアルでは、Aspose.Words for .NET のドキュメント保護解除機能を使用する手順を説明します。この機能を使用すると、Word ドキュメントの保護を解除して、さらに編集できるようにすることができます。以下の手順に従ってください。

## ステップ1: ドキュメントの作成とコンテンツの追加

まず、Document クラスのインスタンスと DocumentBuilder オブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ2: ドキュメントにコンテンツを追加する

DocumentBuilder オブジェクトを使用してドキュメントにコンテンツを追加します。

```csharp
builder.Writeln("Text added to a document.");
```

## ステップ3: ドキュメントの保護を解除する

ドキュメントの保護を解除するには、Document オブジェクトの Unprotect() メソッドを使用します。パスワードなしで保護を解除するか、正しいパスワードを使用して保護を解除するかを選択できます。パスワードなしの保護の解除:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

必ず「newPassword」を正しいドキュメント パスワードに置き換えてください。

## ステップ4: 保護なしで文書を保存する

最後に、Document オブジェクトの Save() メソッドを使用して、ドキュメントを保護せずに保存します。

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

ドキュメントを保護せずに保存するには、正しいパスとファイル名を指定してください。

### Aspose.Words for .NET を使用してドキュメント保護を解除するためのサンプル ソース コード

Aspose.Words for .NET を使用してドキュメントの保護を解除するための完全なソース コードは次のとおりです。

```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Text added to a document.");

//ドキュメントの保護は、パスワードなしでも、正しいパスワードを使用しても解除できます。
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");

doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

これらの手順に従うと、Aspose.Words for .NET を使用して Word 文書から保護を簡単に削除できます。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のドキュメント保護を解除する方法について説明しました。提供されている手順に従うことで、簡単にドキュメントの保護を解除し、さらに編集できるようにすることができます。Aspose.Words for .NET は、ドキュメント保護設定を操作し、Word 文書のセキュリティ レベルをカスタマイズできる強力な API を提供します。ドキュメント保護を解除すると、必要に応じてドキュメントの内容や書式を柔軟に変更できるようになります。

### Word 文書の文書保護を解除するための FAQ

#### Q: Aspose.Words for .NET のドキュメント保護とは何ですか?

A: Aspose.Words for .NET のドキュメント保護とは、Word ドキュメントにセキュリティ対策を適用して、編集、書式設定、コンテンツの変更を制限できる機能のことです。ドキュメントの整合性と機密性を確保するのに役立ちます。

#### Q: Aspose.Words for .NET を使用してドキュメントの保護を解除するにはどうすればよいですか?

A: Aspose.Words for .NET を使用してドキュメントの保護を解除するには、次の手順に従います。
1. インスタンスを作成する`Document`クラスと`DocumentBuilder`物体。
2. 使用`DocumentBuilder`ドキュメントにコンテンツを追加します。
3. 電話する`Unprotect`方法の`Document`オブジェクトを使用して、ドキュメントから既存の保護を削除します。これは、パスワードなしで実行することも、正しいパスワードを入力して実行することもできます。
4. 保護されていない文書を保存するには、`Save`方法の`Document`物体。

#### Q: パスワードなしで Word 文書の保護を解除できますか?

 A: はい、Aspose.Words for .NETを使用して、パスワードなしでWord文書の保護を解除できます。`Unprotect`方法の`Document`パスワードを指定せずにオブジェクトにアクセスすると、以前にパスワードなしで保護されていたドキュメントの保護を解除できます。

#### Q: パスワードで保護された Word 文書を解除するにはどうすればよいですか?

 A: パスワードで保護されたWord文書の保護を解除するには、`Unprotect`方法の`Document`オブジェクト。これにより、正しいパスワードを持つユーザーだけが保護を解除し、ドキュメントにアクセスして編集できるようになります。

#### Q: Word 文書から特定の保護タイプを削除できますか?

 A: はい、Aspose.Words for .NETを使用すると、Word文書から特定の保護タイプを選択的に削除できます。`Unprotect`方法の`Document`オブジェクトでは、読み取り専用保護やフォーム保護などの必要な保護タイプを削除し、他の保護タイプはそのまま残すことができます。