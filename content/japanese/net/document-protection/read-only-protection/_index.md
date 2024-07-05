---
title: Word 文書の読み取り専用保護
linktitle: Word 文書の読み取り専用保護
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書の読み取り専用を保護する方法を学習します。
type: docs
weight: 10
url: /ja/net/document-protection/read-only-protection/
---
このチュートリアルでは、Aspose.Words for .NET の読み取り専用保護機能を使用する手順を説明します。この機能を使用すると、Word 文書を読み取り専用にして、不正な変更を防ぐことができます。以下の手順に従ってください。

## ステップ1: ドキュメントの作成と保護の適用

まず、Document クラスのインスタンスと DocumentBuilder オブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ2: ドキュメントにコンテンツを書き込む
DocumentBuilder オブジェクトを使用してドキュメントにコンテンツを書き込みます。

```csharp
builder.Write("Open document as read-only");
```

## ステップ3: パスワードを設定し、ドキュメントを読み取り専用にする

WriteProtection オブジェクトの SetPassword() プロパティを使用してドキュメントのパスワードを設定します。

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

必ず「MyPassword」を実際に使用するパスワードに置き換えてください。

## ステップ4: 読み取り専用ドキュメントを適用する

ReadOnlyRecommended プロパティを true に設定して、ドキュメントを読み取り専用にします。

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## ステップ5: 読み取り専用保護を適用してドキュメントを保存する

最後に、Document オブジェクトの Protect() メソッドを使用して読み取り専用保護を適用します。

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

保護されたドキュメントを保存するには、正しいパスとファイル名を指定してください。

### Aspose.Words for .NET を使用した読み取り専用保護のサンプル ソース コード

以下は、Aspose.Words for .NET を使用した読み取り専用保護の完全なソース コードです。

```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

//最大 15 文字のパスワードを入力してください。
doc.WriteProtection.SetPassword("MyPassword");

//ドキュメントを読み取り専用にします。
doc.WriteProtection.ReadOnlyRecommended = true;

//書き込み保護を読み取り専用として適用します。
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

これらの手順に従うことで、文書を簡単に保護できます

## 結論

このチュートリアルでは、Word ドキュメントを読み取り専用にして不正な変更を防ぐことができる Aspose.Words for .NET の読み取り専用保護機能について説明しました。提供されている手順に従うことで、ドキュメントに読み取り専用保護を簡単に適用し、セキュリティを強化できます。読み取り専用保護は、編集機能を制限してドキュメントのコンテンツの整合性と正確性を確保するのに役立ちます。Aspose.Words for .NET は、ドキュメント保護を処理するための強力で柔軟な API を提供し、Word ドキュメントをカスタマイズして保護するためのさまざまな機能をサポートしています。

### Word 文書の読み取り専用保護に関する FAQ

#### Q: Aspose.Words for .NET の読み取り専用保護とは何ですか?

A: Aspose.Words for .NET の読み取り専用保護は、Word 文書を読み取り専用にして、不正な変更を防ぐ機能です。文書が読み取り専用に設定されている場合、ユーザーは文書を開いて表示することはできますが、その内容を変更することはできません。

#### Q: Aspose.Words for .NET を使用して Word 文書に読み取り専用保護を適用するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書に読み取り専用保護を適用するには、次の手順に従います。
1. インスタンスを作成する`Document`クラスと`DocumentBuilder`物体。
2. 使用`DocumentBuilder`ドキュメントにコンテンツを書き込みます。
3. 文書にパスワードを設定するには、`SetPassword`方法の`WriteProtection`物体。
4. をセットする`ReadOnlyRecommended`の財産`WriteProtection`反対する`true`ドキュメントを読み取り専用で開くことを推奨します。
5. 読み取り専用保護を適用するには、`Protect`方法の`Document`オブジェクト、指定`ProtectionType`として`ReadOnly`.
6. 保護された文書を保存するには、`Save`方法の`Document`物体。

#### Q: Aspose.Words for .NET を使用して Word 文書から読み取り専用保護を削除できますか?

A: はい、Aspose.Words for .NETを使用してWord文書から読み取り専用保護を解除できます。これを行うには、`Unprotect`方法の`Document`クラスは、ドキュメントから既存の保護を削除します。

#### Q: Word 文書の読み取り専用保護に別のパスワードを設定できますか?

 A: いいえ、Aspose.Words for .NETの読み取り専用保護では、読み取り専用保護専用の別のパスワードを設定することはできません。`SetPassword`方法の`WriteProtection`オブジェクトは、読み取り専用保護と読み取り/書き込み保護の両方を含むドキュメント全体の保護に適用されます。

#### Q: ユーザーは Word 文書の読み取り専用保護を回避できますか?

A: Word 文書の読み取り専用保護は、偶発的または不正な変更を阻止し、防止することを目的としています。一定の保護レベルは提供されますが、十分な技術的知識または編集権限を持つユーザーによって回避される可能性があります。ただし、読み取り専用保護は抑止力として機能し、文書の整合性を維持するのに役立ちます。