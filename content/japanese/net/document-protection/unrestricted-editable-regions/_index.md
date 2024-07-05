---
title: Word 文書内の無制限の編集可能領域
linktitle: Word 文書内の無制限の編集可能領域
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書に制限のない編集可能な領域を作成する方法を学習します。
type: docs
weight: 10
url: /ja/net/document-protection/unrestricted-editable-regions/
---
このチュートリアルでは、Aspose.Words for .NET の無制限編集可能領域機能を使用する手順を説明します。この機能を使用すると、ドキュメントの残りの部分が読み取り専用であっても、コンテンツを制限なく編集できる Word ドキュメント内の領域を定義できます。以下の手順に従ってください。

## ステップ1: ドキュメントの読み込みと保護の設定

まず、既存のドキュメントを読み込みます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

読み取り専用保護タイプとパスワードを設定してドキュメントを保護する

## ステップ2: 編集可能な領域を作成する

まず、EditableRangeStart オブジェクトと EditableRangeEnd オブジェクトを使用して編集可能な領域を作成します。

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
//今作成した EditableRangeStart に対して EditableRange オブジェクトが作成されます。
EditableRange editableRange = edRangeStart.EditableRange;

//編集範囲内に何かを入れてください。
builder.Writeln("Paragraph inside first editable range");

//編集可能な範囲は、開始と終了がある場合に適切に形成されます。
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## ステップ3: 編集可能領域外にコンテンツを追加する

編集可能な領域外にコンテンツを追加できますが、編集可能な領域は読み取り専用のままです。

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## ステップ4: ドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

編集可能な領域を含むドキュメントを保存するには、正しいパスとファイル名を指定してください。

### Aspose.Words for .NET を使用した無制限編集可能領域のサンプル ソース コード

以下は、Aspose.Words for .NET を使用した無制限の編集可能領域の完全なソース コードです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントをアップロードし、読み取り専用にします。
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

//編集可能な範囲を開始します。
EditableRangeStart edRangeStart = builder.StartEditableRange();
//今作成した EditableRangeStart に対して EditableRange オブジェクトが作成されます。
EditableRange editableRange = edRangeStart.EditableRange;

//編集範囲内に何かを入れてください。
builder.Writeln("Paragraph inside first editable range");

//編集可能な範囲は、開始と終了がある場合に適切に形成されます。
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
これらの手順に従うと、Aspose.Words for .NET を使用して Word 文書内に無制限の編集可能な領域を簡単に作成できます。

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内に無制限の編集可能領域を作成する方法を学習しました。提供されている手順に従うことで、文書内の特定の領域を定義し、その領域ではユーザーが自由にコンテンツを編集でき、文書の残りの部分は読み取り専用のままにすることができます。Aspose.Words for .NET は、文書の保護とカスタマイズのための強力な機能を提供し、Word 文書の編集機能を制御できるようにします。

### Word 文書の無制限編集可能領域に関する FAQ

#### Q: Aspose.Words for .NET の無制限編集可能領域とは何ですか?

A: Aspose.Words for .NET の無制限編集可能領域とは、Word 文書内の領域であり、文書の残りの部分が読み取り専用に設定されている場合でも、コンテンツを制限なく編集できます。これらの領域は、文書全体の保護を維持しながら、ユーザーが変更できる文書の特定の部分を定義する方法を提供します。

#### Q: Aspose.Words for .NET を使用して、制限のない編集可能な領域を作成するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書に制限のない編集可能な領域を作成するには、次の手順に従います。
1. 既存のドキュメントをロードするには、`Document`クラス。
2. ドキュメントの保護を読み取り専用に設定するには、`Protect`方法の`Document`物体。
3. 使用`DocumentBuilder`クラスを追加して編集可能な範囲を作成します`EditableRangeStart`オブジェクトと`EditableRangeEnd`物体。
4. 編集可能な範囲内にコンテンツを追加するには、`DocumentBuilder`.
5. 変更した文書を保存するには、`Save`方法の`Document`物体。

#### Q: Word 文書内に、制限のない編集可能な領域を複数作成できますか?

A: はい、Word文書内に複数の無制限の編集可能領域を設けることができます。これを実現するには、複数のセットを作成します。`EditableRangeStart`そして`EditableRangeEnd`オブジェクトを使用する`DocumentBuilder`クラス。各オブジェクト セットは、ユーザーが制限なくコンテンツを変更できる個別の編集可能な領域を定義します。

#### Q: 編集可能な領域を互いにネストすることはできますか?

 A: いいえ、Aspose.Words for .NETでは編集可能な領域を互いにネストすることはできません。`EditableRangeStart`そして`EditableRangeEnd`ペアは独立している必要があり、重複したり、別の編集可能領域内にネストされたりしてはなりません。ネストされた編集可能領域はサポートされていません。

#### Q: 編集可能な領域内のドキュメントから読み取り専用保護を削除できますか?

A: いいえ、編集可能領域内のドキュメントから読み取り専用保護を削除することはできません。読み取り専用保護はドキュメント全体に適用され、特定の編集可能領域内で選択的に削除することはできません。編集可能領域の目的は、ドキュメント全体を読み取り専用のままにして、コンテンツを変更できるようにすることです。