---
title: Word 文書内の無制限の編集可能領域
linktitle: Word 文書内の無制限の編集可能領域
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内に無制限の編集可能領域を作成する方法を学びます。
type: docs
weight: 10
url: /ja/net/document-protection/unrestricted-editable-regions/
---
このチュートリアルでは、Aspose.Words for .NET の無制限の編集可能領域機能を使用する手順を説明します。この機能を使用すると、文書の残りの部分が読み取り専用であっても、コンテンツを制限なく編集できる Word 文書内の領域を定義できます。以下の手順に従います。

## ステップ 1: 文書の読み込みと保護の設定

まず、既存のドキュメントをロードします。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

読み取り専用の保護タイプとパスワードを設定してドキュメントを保護します

## ステップ 2: 編集可能領域の作成

まず、EditableRangeStart オブジェクトと EditableRangeEnd オブジェクトを使用して編集可能領域を作成します。

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
//先ほど作成した EditableRangeStart に対して EditableRange オブジェクトが作成されます。
EditableRange editableRange = edRangeStart.EditableRange;

//編集可能範囲内に何かを入れます。
builder.Writeln("Paragraph inside first editable range");

//編集可能な範囲は、開始点と終了点がある場合に整形式です。
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## ステップ 3: 編集可能領域の外側にコンテンツを追加する

編集可能領域の外側にコンテンツを追加できますが、その領域は読み取り専用のままになります。

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## ステップ 4: ドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

編集可能な領域を含むドキュメントを保存するには、必ず正しいパスとファイル名を指定してください。

### Aspose.Words for .NET を使用した無制限の編集可能領域のソース コードの例

Aspose.Words for .NET を使用した、無制限の編集可能領域の完全なソース コードを次に示します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントをアップロードし、読み取り専用にします。
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

//編集可能な範囲を開始します。
EditableRangeStart edRangeStart = builder.StartEditableRange();
//先ほど作成した EditableRangeStart に対して EditableRange オブジェクトが作成されます。
EditableRange editableRange = edRangeStart.EditableRange;

//編集可能範囲内に何かを入れます。
builder.Writeln("Paragraph inside first editable range");

//編集可能な範囲は、開始点と終了点がある場合に整形式です。
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
これらの手順に従うと、Aspose.Words for .NET を使用して Word 文書内に無制限の編集可能領域を簡単に作成できます。

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内に無制限の編集可能領域を作成する方法を学びました。指定された手順に従うことで、ドキュメント内の残りの部分を読み取り専用のままにして、ユーザーがコンテンツを自由に編集できる特定の領域をドキュメント内に定義できます。 Aspose.Words for .NET は、文書の保護とカスタマイズのための強力な機能を提供し、Word 文書の編集機能を制御できるようにします。

### Word 文書内の制限のない編集可能領域に関する FAQ

#### Q: Aspose.Words for .NET の無制限の編集可能領域とは何ですか?

A: Aspose.Words for .NET の無制限の編集可能領域は、文書の残りの部分が読み取り専用に設定されている場合でも、コンテンツを制限なく編集できる Word 文書内の領域です。これらの領域は、ドキュメント全体の保護を維持しながら、ユーザーが変更できるドキュメントの特定の部分を定義する方法を提供します。

#### Q: Aspose.Words for .NET を使用して無制限の編集可能領域を作成するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書内に無制限の編集可能領域を作成するには、次の手順に従います。
1. を使用して既存のドキュメントをロードします。`Document`クラス。
2. を使用してドキュメント保護を読み取り専用に設定します。`Protect`の方法`Document`物体。
3. 使用`DocumentBuilder`クラスを追加して編集可能な範囲を作成します。`EditableRangeStart`オブジェクトと`EditableRangeEnd`物体。
4. 編集可能な範囲にコンテンツを追加するには、`DocumentBuilder`.
5. 変更したドキュメントを保存するには、`Save`の方法`Document`物体。

#### Q: Word 文書内に複数の無制限の編集可能領域を設定できますか?

A: はい、Word 文書内に複数の無制限の編集可能領域を設定できます。これを実現するには、複数のセットを作成できます。`EditableRangeStart`そして`EditableRangeEnd`を使用したオブジェクト`DocumentBuilder`クラス。オブジェクトの各セットは、ユーザーが制限なくコンテンツを変更できる個別の編集可能領域を定義します。

#### Q: 編集可能な領域を相互にネストできますか?

 A: いいえ、Aspose.Words for .NET を使用して編集可能領域を相互にネストすることはできません。各編集可能な領域は、`EditableRangeStart`そして`EditableRangeEnd`ペアは独立している必要があり、別の編集可能な領域内で重複したりネストしたりしてはなりません。ネストされた編集可能領域はサポートされていません。

#### Q: 編集可能領域内のドキュメントから読み取り専用保護を削除できますか?

A: いいえ、編集可能領域内のドキュメントから読み取り専用保護を削除することはできません。読み取り専用保護はドキュメント全体に適用され、特定の編集可能領域内で選択的に削除することはできません。編集可能領域の目的は、ドキュメント全体を読み取り専用に保ちながら、コンテンツを変更できるようにすることです。