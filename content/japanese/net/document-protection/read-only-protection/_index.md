---
title: Word 文書の読み取り専用保護
linktitle: Word 文書の読み取り専用保護
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書の読み取り専用を保護する方法を学びます。
type: docs
weight: 10
url: /ja/net/document-protection/read-only-protection/
---
このチュートリアルでは、Aspose.Words for .NET の読み取り専用保護機能を使用する手順を説明します。この機能を使用すると、Word 文書を読み取り専用にして、不正な変更を防ぐことができます。以下の手順に従います。

## ステップ 1: ドキュメントの作成と保護の適用

まず、Document クラスのインスタンスと DocumentBuilder オブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: ドキュメントにコンテンツを書き込む
DocumentBuilder オブジェクトを使用して、ドキュメントにコンテンツを書き込みます。

```csharp
builder.Write("Open document as read-only");
```

## ステップ 3: パスワードを設定し、ドキュメントを読み取り専用にします

WriteProtection オブジェクトの SetPassword() プロパティを使用して、ドキュメントのパスワードを設定します。

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

「MyPassword」を実際に使用するパスワードに置き換えてください。

## ステップ 4: 読み取り専用ドキュメントを適用する

ReadOnlyRecommend プロパティを true に設定して、ドキュメントを読み取り専用にします。

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## ステップ 5: 読み取り専用保護を適用してドキュメントを保存する

最後に、Document オブジェクトの Protect() メソッドを使用して読み取り専用保護を適用します。

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

保護されたドキュメントを保存するには、必ず正しいパスとファイル名を指定してください。

### Aspose.Words for .NET を使用した読み取り専用保護のソース コード例

Aspose.Words for .NET を使用した読み取り専用保護の完全なソース コードは次のとおりです。

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

//パスワードを 15 文字以内で入力します。
doc.WriteProtection.SetPassword("MyPassword");

//ドキュメントを読み取り専用にします。
doc.WriteProtection.ReadOnlyRecommended = true;

//書き込み保護を読み取り専用として適用します。
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

次の手順に従うことで、ドキュメントを簡単に保護できます

## 結論

このチュートリアルでは、Aspose.Words for .NET の読み取り専用保護機能について説明しました。この機能を使用すると、Word ドキュメントを読み取り専用にして、不正な変更を防ぐことができます。指定された手順に従うことで、ドキュメントに読み取り専用保護を簡単に適用し、ドキュメントのセキュリティを強化できます。読み取り専用保護は、編集機能を制限することで、ドキュメントのコンテンツの整合性と正確性を確保するのに役立ちます。 Aspose.Words for .NET は、文書保護を処理するための強力で柔軟な API を提供し、Word 文書をカスタマイズして保護するためのその他のさまざまな機能をサポートします。

### Word 文書の読み取り専用保護に関する FAQ

#### Q: Aspose.Words for .NET の読み取り専用保護とは何ですか?

A: Aspose.Words for .NET の読み取り専用保護は、Word ドキュメントを読み取り専用にして、不正な変更を防止できる機能です。ドキュメントが読み取り専用に設定されている場合、ユーザーはドキュメントを開いて表示することはできますが、そのコンテンツを変更することはできません。

#### Q: Aspose.Words for .NET を使用して Word 文書に読み取り専用保護を適用するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書に読み取り専用保護を適用するには、次の手順に従います。
1. のインスタンスを作成します。`Document`クラスと`DocumentBuilder`物体。
2. 使用`DocumentBuilder`コンテンツをドキュメントに書き込みます。
3. を使用してドキュメントのパスワードを設定します。`SetPassword`の方法`WriteProtection`物体。
4. をセットする`ReadOnlyRecommended`の財産`WriteProtection`に反対する`true`ドキュメントを読み取り専用で開くことをお勧めします。
5. を使用して読み取り専用保護を適用します。`Protect`の方法`Document`オブジェクトを指定して、`ProtectionType`として`ReadOnly`.
6. 保護されたドキュメントを保存するには、`Save`の方法`Document`物体。

#### Q: Aspose.Words for .NET を使用して Word 文書から読み取り専用保護を削除できますか?

A: はい、Aspose.Words for .NET を使用して Word 文書から読み取り専用保護を削除できます。これを行うには、`Unprotect`の方法`Document`クラスを使用して、ドキュメントから既存の保護を削除します。

#### Q: Word 文書の読み取り専用保護に別のパスワードを設定できますか?

 A: いいえ、Aspose.Words for .NET の読み取り専用保護では、読み取り専用保護専用の別のパスワードを設定することはできません。を使用して設定したパスワード`SetPassword`の方法`WriteProtection`オブジェクトは、読み取り専用保護と読み取り/書き込み保護の両方を含むドキュメント保護全体に適用されます。

#### Q: ユーザーは Word 文書の読み取り専用保護をバイパスできますか?

A: Word 文書の読み取り専用保護は、偶発的または不正な変更を阻止し、防止することを目的としています。これは一定レベルの保護を提供しますが、十分な技術的知識または編集権限を持つユーザーによってバイパスされる可能性があります。ただし、読み取り専用保護は抑止力として機能し、ドキュメントの整合性を維持するのに役立ちます。