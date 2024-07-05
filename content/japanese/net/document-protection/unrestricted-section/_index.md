---
title: Word 文書の制限なしセクション
linktitle: Word 文書の制限なしセクション
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の制限のないセクションを定義する方法を学習します。
type: docs
weight: 10
url: /ja/net/document-protection/unrestricted-section/
---
このチュートリアルでは、Aspose.Words for .NET の無制限セクション機能を使用する手順を説明します。この機能を使用すると、Word 文書の残りの部分が保護されている場合でも、保護されていない特定のセクションを定義できます。以下の手順に従ってください。

## ステップ1: ドキュメントとセクションの作成

まず、Document クラスのインスタンスと DocumentBuilder オブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ2: ドキュメントにコンテンツを追加する
DocumentBuilder オブジェクトを使用して、ドキュメントにコンテンツを追加し、セクション区切りを挿入します。

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## ステップ3: ドキュメントとセクションを保護する

セクション保護は、ドキュメント保護が有効になっていて、フォーム フィールドでの編集のみが許可されている場合にのみ機能します。ドキュメントは、Document オブジェクトの Protect() メソッドを使用して保護できます。

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

必ず正しい保護の種類を指定し、必要なパスワードを設定してください。

## ステップ4: 特定のセクションの保護を無効にする

デフォルトではすべてのセクションが保護されていますが、Section オブジェクトの ProtectedForForms プロパティを使用して、特定のセクションの保護を選択的に無効にすることができます。

```csharp
doc.Sections[0].ProtectedForForms = false;
```

この例では、最初のセクションの保護は無効になっています。

## ステップ5: ドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

制限のないセクションを含むドキュメントを保存するには、正しいパスとファイル名を指定してください。

### Aspose.Words for .NET を使用した無制限セクションのサンプル ソース コード

以下は、Aspose.Words for .NET を使用した制限のないセクションの完全なソース コードです。


```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//テキストを含む 2 つのセクションを挿入します。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

//セクション保護は、ドキュメント保護がオンになっている場合にのみ機能し、フォーム フィールドでの編集のみが許可されます。
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//デフォルトではすべてのセクションが保護されていますが、選択的に保護をオフにすることができます。
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

これらの手順に従うと、Aspose.Words for .NET を使用して Word 文書内の制限のないセクションを簡単に定義できるようになります。

## 結論

このチュートリアルでは、Aspose.Words for .NET の無制限セクション機能について説明しました。この機能により、Word 文書内の特定のセクションは保護されず、文書の残りの部分は保護されます。提供されている手順に従うことで、文書内のセクションを簡単に定義し、他のセクションは保護されたまま、ユーザーが自由にコンテンツを編集できます。Aspose.Words for .NET は、文書の保護とカスタマイズのための強力な機能を提供し、Word 文書内の編集権限を制御できます。

### Word 文書の無制限セクションに関する FAQ

#### Q: Aspose.Words for .NET の無制限セクションとは何ですか?

A: Aspose.Words for .NET の無制限セクションとは、Word 文書内の特定のセクションのことで、文書の残りの部分が保護されていても保護されません。これらのセクションでは、文書の残りの部分の保護を維持しながら、その中のコンテンツを変更できます。

#### Q: Aspose.Words for .NET を使用して制限のないセクションを作成するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書に制限のないセクションを作成するには、次の手順に従います。
1. インスタンスを作成する`Document`クラスと`DocumentBuilder`物体。
2. 使用`DocumentBuilder`ドキュメントにコンテンツを追加し、セクション区切りを挿入します。
3. 文書を保護するには`Protect`方法の`Document`オブジェクトに、必要な保護タイプとパスワードを指定します。
4. 特定のセクションの保護を無効にするには、`ProtectedForForms`対応する`Section`反対する`false`.
5. 変更したドキュメントを保存します。

#### Q: Word 文書内に複数の制限のないセクションを作成できますか?

 A: はい、Word文書内に複数の制限のないセクションを設けることができます。`ProtectedForForms`の財産`Section`オブジェクトを使用すると、他のセクションを保護したまま、ユーザーがコンテンツを自由に変更できる複数のセクションを定義できます。

#### Q4. 最初に保護されたセクションから保護を解除できますか?
はい、最初に保護されたセクションの保護を解除するには、`ProtectedForForms`対応する`Section`反対する`false`これにより、ユーザーは特定のセクション内のコンテンツを制限なく編集できるようになります。

#### Q: Word 文書にはどのような保護タイプを適用できますか?

A: Aspose.Words for .NET では、Word 文書に適用できる次のようなさまざまな保護タイプが提供されています。
- NoProtection: 保護は適用されません。
- AllowOnlyRevisions: ユーザーはドキュメントの修正のみ行うことができます。
- AllowOnlyComments: ユーザーはドキュメントにコメントを追加することのみできます。
- AllowOnlyFormFields: ユーザーはドキュメント内のフォーム フィールドのみを編集できます。
- ReadOnly: ドキュメントは読み取り専用であり、編集は許可されません。


