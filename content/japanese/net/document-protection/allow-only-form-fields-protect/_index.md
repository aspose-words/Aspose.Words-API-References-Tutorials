---
title: Word 文書でフォーム フィールドのみの保護を許可する
linktitle: Word 文書でフォーム フィールドのみの保護を許可する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を保護し、フォーム フィールドのみを編集できるようにする方法を学習します。
type: docs
weight: 10
url: /ja/net/document-protection/allow-only-form-fields-protect/
---
ドキュメント保護は、C# アプリケーション内でファイルを処理する場合に不可欠な機能です。Aspose.Words ライブラリ for .NET を使用すると、ドキュメントを簡単に保護し、フォーム フィールドのみの編集を許可できます。このステップ バイ ステップ ガイドでは、Aspose.Words for .NET の [フォーム フィールドのみの保護を許可] 機能を使用して、C# ソース コードでフォーム フィールドのみの編集を許可する方法について説明します。

## ステップ1: ドキュメントディレクトリの設定

最初のステップは、ドキュメントのディレクトリを定義することです。保護されたドキュメントを保存するパスを指定する必要があります。例:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

「YOUR DOCUMENTS DIRECTORY」を、ドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ2: セクションとテキストの挿入

次に、ドキュメントにセクションとテキストを挿入する必要があります。Aspose.Words が提供する DocumentBuilder クラスを使用して、ドキュメントのコンテンツを構築します。簡単な例を次に示します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

この例では、新しい空白のドキュメントを作成し、DocumentBuilder を使用してテキストの行を追加します。

## ステップ3: ドキュメント保護を有効にする

ドキュメント保護は、ドキュメント保護が有効になっている場合にのみ機能します。ドキュメント保護を有効にするには、`Protect` Document クラスのメソッド。方法は次のとおりです。

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

この例では、保護タイプ`を指定してドキュメント保護を有効にします。

AllowOnlyFormFields` とパスワードの設定。

## ステップ4: フォームフィールドのみを許可する

ドキュメント保護が有効になったので、フォーム フィールドの編集のみを許可するように指定する必要があります。これにより、ユーザーはフォーム フィールドであるドキュメントの部分のみを編集できるようになります。手順は次のとおりです。

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

「password」は必ず先ほど設定したパスワードに置き換えてください。

## ステップ5: 保護されたドキュメントを保存する

最後に、保護された文書を`Save`Document クラスのメソッド。完全なファイル パスと目的のファイル名を指定します。例:

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

必ず「dataDir」をドキュメント ディレクトリへのパスに置き換えてください。

### Aspose.Words for .NET を使用したフォーム フィールド保護機能のみを許可するサンプル ソース コード

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

//テキストを含む 2 つのセクションを挿入します。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

//ドキュメント保護は、ドキュメント保護がオンになっている場合にのみ機能し、フォーム フィールドでの編集のみが許可されます。
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//保護されたドキュメントを保存します。
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリを使用してドキュメントを保護し、フォーム フィールドのみを編集できるようにする方法について説明しました。提供されている手順に従うことで、この機能を C# アプリケーションに簡単に実装できます。ドキュメントの保護は、ドキュメントのセキュリティと機密性を確保するために不可欠です。

### Word 文書でフォーム フィールドのみの保護を許可する方法に関する FAQ

#### Q: Aspose.Words for .NET のドキュメント保護とは何ですか?

A: Aspose.Words for .NET のドキュメント保護は、編集、書式設定、コンテンツの変更などの特定のアクションを制限することでドキュメントを保護できる機能です。不正な変更を防ぐことで、ドキュメントの整合性と機密性を維持するのに役立ちます。

#### Q: Aspose.Words for .NET を使用してドキュメントを保護し、フォーム フィールドのみを編集できるようにするにはどうすればよいですか?

A: Aspose.Words for .NET を使用してドキュメントを保護し、フォーム フィールドのみを編集できるようにするには、次の手順に従います。
1. ドキュメントのディレクトリ パスを定義します。
2. セクションとテキストをドキュメントに挿入するには、`DocumentBuilder`クラス。
3. ドキュメント保護を有効にするには、`Protect`方法の`Document`クラス、保護タイプを次のように指定`AllowOnlyFormFields`パスワードを入力します。
4. 保護された文書を保存するには、`Save`方法の`Document`クラス。

#### Q: Aspose.Words for .NET を使用して、保護されたドキュメントにフォーム フィールドを挿入できますか?

A: はい、Aspose.Words for .NETを使用して保護されたドキュメントにフォームフィールドを挿入できます。`AllowOnlyFormFields`このタイプでは、ユーザーはフォームフィールドのみを編集でき、ドキュメントの残りのコンテンツは保護されます。`DocumentBuilder`保護を有効にする前に、ドキュメントにフォーム フィールドを挿入するクラス。

#### Q: 保護されたドキュメントからドキュメント保護を削除できますか?

 A: はい、Aspose.Words for .NETを使用して保護されたドキュメントからドキュメント保護を解除できます。保護を解除するには、`Unprotect`方法の`Document`クラスを開き、正しいパスワードを入力してください。これにより保護が解除され、ドキュメントを制限なく編集できるようになります。

#### Q: 複数の保護タイプでドキュメントを保護することは可能ですか?

 A: いいえ、Aspose.Words for .NETでは、一度に1つの保護タイプのみをドキュメントに適用できます。ただし、`AllowOnlyFormFields`保護タイプは、フォームフィールドへの編集を効果的に制限しながら、他の保護タイプを許可します。`AllowOnlyComments`または`AllowOnlyRevisions`フォーム フィールド保護と組み合わせることができます。

#### Q: ドキュメント内の異なる保護タイプに異なるパスワードを設定できますか?

A: いいえ、Aspose.Words for .NET では、保護の種類に関係なく、ドキュメント保護に 1 つのパスワードを設定できます。ドキュメント保護の有効化と無効化には同じパスワードが使用されます。