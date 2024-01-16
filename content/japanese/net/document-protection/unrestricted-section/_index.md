---
title: Word 文書内の無制限のセクション
linktitle: Word 文書内の無制限のセクション
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内に制限のないセクションを定義する方法を学びます。
type: docs
weight: 10
url: /ja/net/document-protection/unrestricted-section/
---
このチュートリアルでは、Aspose.Words for .NET の無制限セクション機能を使用する手順を説明します。この機能を使用すると、文書の残りの部分が保護されている場合でも、Word 文書内の保護されていない特定のセクションを定義できます。以下の手順に従います。

## ステップ 1: ドキュメントとセクションの作成

まず、Document クラスのインスタンスと DocumentBuilder オブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: ドキュメントにコンテンツを追加する
DocumentBuilder オブジェクトを使用してドキュメントにコンテンツを追加し、セクション区切りを挿入します。

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## ステップ 3: ドキュメントとセクションを保護する

セクション保護は、ドキュメント保護が有効で、フォーム フィールドでの編集のみが許可されている場合にのみ機能します。 Document オブジェクトの Protect() メソッドを使用してドキュメントを保護できます。

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

必ず正しい保護の種類を指定し、必要なパスワードを設定してください。

## ステップ 4: 特定のセクションの保護を無効にする

デフォルトでは、すべてのセクションが保護されていますが、Section オブジェクトの ProtectedForForms プロパティを使用して、特定のセクションの保護を選択的に無効にすることができます。

```csharp
doc.Sections[0].ProtectedForForms = false;
```

この例では、最初のセクションの保護が無効になっています。

## ステップ 5: ドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

制限のないセクションを含むドキュメントを保存するには、必ず正しいパスとファイル名を指定してください。

### Aspose.Words for .NET を使用した無制限セクションのソース コードの例

Aspose.Words for .NET を使用した制限なしセクションの完全なソース コードは次のとおりです。


```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//テキストを含む 2 つのセクションを挿入します。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

//セクション保護は、ドキュメント保護がオンになっており、フォーム フィールドでの編集のみが許可されている場合にのみ機能します。
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//デフォルトでは、すべてのセクションが保護されていますが、選択的に保護をオフにすることができます。
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

これらの手順に従うことで、Aspose.Words for .NET を使用して Word 文書内に制限のないセクションを簡単に定義できるようになります。

## 結論

このチュートリアルでは、Aspose.Words for .NET の無制限セクション機能について説明しました。この機能により、Word 文書内の特定のセクションを保護せずに、文書の残りの部分を保護できます。示されている手順に従うことで、他のセクションの保護を維持しながら、ユーザーがコンテンツを自由に編集できるセクションをドキュメント内に簡単に定義できます。 Aspose.Words for .NET は、ドキュメントの保護とカスタマイズのための強力な機能を提供し、Word ドキュメント内の編集権限を制御できるようにします。

### Word 文書の制限されていないセクションに関する FAQ

#### Q: Aspose.Words for .NET の制限されていないセクションとは何ですか?

A: Aspose.Words for .NET の制限されていないセクションとは、文書の残りの部分が保護されている場合でも、保護されていない Word 文書内の特定のセクションです。これらのセクションを使用すると、ユーザーはドキュメントの残りの部分の保護を維持しながら、セクション内のコンテンツを変更できます。

#### Q: Aspose.Words for .NET を使用して制限のないセクションを作成するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書内に無制限のセクションを作成するには、次の手順に従います。
1. のインスタンスを作成します。`Document`クラスと`DocumentBuilder`物体。
2. 使用`DocumentBuilder`ドキュメントにコンテンツを追加し、セクション区切りを挿入します。
3. を使用して文書を保護します。`Protect`の方法`Document`オブジェクトを使用して、必要な保護タイプとパスワードを指定します。
4. 特定のセクションの保護を無効にするには、`ProtectedForForms`対応するプロパティ`Section`に反対する`false`.
5. 変更したドキュメントを保存します。

#### Q: Word 文書内に複数の無制限のセクションを含めることはできますか?

 A: はい、Word 文書内に複数の無制限のセクションを含めることができます。を使用して特定のセクションの保護を選択的に無効にすることで、`ProtectedForForms`の財産`Section`オブジェクトでは、他のセクションを保護したままユーザーがコンテンツを自由に変更できる複数のセクションを定義できます。

#### Q4.最初に保護されていたセクションから保護を解除できますか?
はい、最初に保護されていたセクションから保護を削除するには、`ProtectedForForms`対応するプロパティ`Section`に反対する`false`。これにより、ユーザーはその特定のセクション内のコンテンツを制限なく編集できるようになります。

#### Q: Word 文書にはどのような保護タイプを適用できますか?

A: Aspose.Words for .NET は、Word ドキュメントに適用できる次のようなさまざまな保護タイプを提供します。
- NoProtection: 保護は適用されません。
- AllowOnlyRevisions: ユーザーはドキュメントの修正のみを行うことができます。
- AllowOnlyComments: ユーザーはドキュメントにコメントのみを追加できます。
- AllowOnlyFormFields: ユーザーはドキュメント内のフォーム フィールドのみを編集できます。
- ReadOnly: ドキュメントは読み取り専用であり、編集は許可されません。


