---
title: Word 文書でフォームフィールドの保護のみを許可する
linktitle: Word 文書でフォームフィールドの保護のみを許可する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word ドキュメントを保護し、フォーム フィールドのみを編集できるようにする方法を学びます。
type: docs
weight: 10
url: /ja/net/document-protection/allow-only-form-fields-protect/
---
ドキュメント保護は、C# アプリケーション内のファイルを文書処理する場合に不可欠な機能です。 .NET 用の Aspose.Words ライブラリを使用すると、ドキュメントを簡単に保護し、フォーム フィールドのみを編集できるようにすることができます。このステップバイステップ ガイドでは、C# ソース コードを使用して、Aspose.Words for .NET のフォーム フィールドのみ保護機能を使用してフォーム フィールドの編集のみを許可する方法を説明します。

## ステップ 1: ドキュメント ディレクトリの設定

最初のステップは、ドキュメントのディレクトリを定義することです。保護されたドキュメントを保存するパスを指定する必要があります。例えば ：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 2: セクションとテキストの挿入

次に、ドキュメントにセクションとテキストを挿入する必要があります。 Aspose.Words が提供する DocumentBuilder クラスを使用して、ドキュメントのコンテンツを構築します。簡単な例を次に示します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

この例では、新しい空のドキュメントを作成し、DocumentBuilder を使用してテキスト行を追加します。

## ステップ 3: ドキュメント保護を有効にする

ドキュメントの保護は、ドキュメントの保護が有効になっている場合にのみ機能します。ドキュメント保護を有効にするには、`Protect` Document クラスのメソッド。その方法は次のとおりです。

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

この例では、保護タイプ ` を指定してドキュメント保護を有効にします。

「AllowOnlyFormFields」とパスワードの設定。

## ステップ 4: フォームフィールドのみを許可する

ドキュメント保護が有効になったので、フォーム フィールドの編集のみを許可するように指定する必要があります。これにより、ユーザーはドキュメントのフォーム フィールドの部分のみを編集できるようになります。その方法は次のとおりです。

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

必ず「パスワード」を先ほど設定したパスワードに置き換えてください。

## ステップ 5: 保護されたドキュメントを保存する

最後に、次のコマンドを使用して、保護されたドキュメントを保存できます。`Save` Document クラスのメソッド。完全なファイル パスと目的のファイル名を指定します。例えば ：

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

必ず「dataDir」をドキュメント ディレクトリへのパスに置き換えてください。

### Aspose.Words for .NET を使用したフォーム フィールド保護のみを許可する機能のソース コード例

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

//テキストを含む 2 つのセクションを挿入します。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

//文書保護は、文書保護がオンになっていて、フォーム フィールドでの編集のみが許可されている場合にのみ機能します。
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//保護された文書を保存します。
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリを使用してドキュメントを保護し、フォーム フィールドのみを編集できるようにする方法を説明しました。示されている手順に従うことで、この機能を C# アプリケーションに簡単に実装できます。文書のセキュリティと機密性を確保するには、文書の保護が不可欠です。

### Word 文書でフォームフィールドのみを許可する保護に関する FAQ

#### Q: Aspose.Words for .NET のドキュメント保護とは何ですか?

A: Aspose.Words for .NET のドキュメント保護は、編集、書式設定、コンテンツの変更などの特定の操作を制限することでドキュメントを保護できる機能です。不正な変更を防止することで、ドキュメントの整合性と機密性を維持するのに役立ちます。

#### Q: Aspose.Words for .NET を使用してドキュメントを保護し、フォーム フィールドのみを編集できるようにするにはどうすればよいですか?

A: ドキュメントを保護し、Aspose.Words for .NET を使用してフォーム フィールドのみを編集できるようにするには、次の手順に従います。
1. ドキュメントのディレクトリ パスを定義します。
2. セクションとテキストをドキュメントに挿入するには、`DocumentBuilder`クラス。
3. を使用してドキュメント保護を有効にします`Protect`の方法`Document`クラス、保護タイプを次のように指定します`AllowOnlyFormFields`そしてパスワードを提供します。
4. 保護されたドキュメントを保存するには、`Save`の方法`Document`クラス。

#### Q: Aspose.Words for .NET を使用して、保護されたドキュメントにフォーム フィールドを挿入できますか?

A: はい、Aspose.Words for .NET を使用して、保護されたドキュメントにフォーム フィールドを挿入できます。文書保護`AllowOnlyFormFields`type を使用すると、ユーザーはドキュメントの残りのコンテンツを保護しながら、フォーム フィールドのみを編集できます。使用できます`DocumentBuilder`保護を有効にする前にフォーム フィールドをドキュメントに挿入するクラス。

#### Q: 保護されたドキュメントからドキュメントの保護を削除できますか?

 A: はい、Aspose.Words for .NET を使用して、保護されたドキュメントからドキュメントの保護を削除できます。保護を解除するには、`Unprotect`の方法`Document`クラスを選択し、正しいパスワードを入力します。これにより、保護が解除され、ドキュメントを無制限に編集できるようになります。

#### Q: 複数の保護タイプでドキュメントを保護することはできますか?

 A: いいえ、Aspose.Words for .NET では、ドキュメントに一度に 1 つの保護タイプのみを適用できます。しかし`AllowOnlyFormFields`保護タイプは、フォーム フィールドへの編集を効果的に制限しながら、次のような他の保護タイプを許可できます。`AllowOnlyComments`または`AllowOnlyRevisions`、フォームフィールド保護と組み合わせることができます。

#### Q: ドキュメント内の保護タイプごとに異なるパスワードを設定できますか?

A: いいえ、Aspose.Words for .NET では、保護の種類に関係なく、ドキュメントの保護に単一のパスワードを設定できます。ドキュメント保護の有効化と無効化には同じパスワードが使用されます。