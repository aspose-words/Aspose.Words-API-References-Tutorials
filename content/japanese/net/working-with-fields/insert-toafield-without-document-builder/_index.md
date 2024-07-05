---
title: ドキュメントビルダーを使用せずに TOA フィールドを挿入する
linktitle: ドキュメントビルダーを使用せずに TOA フィールドを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、ドキュメント ビルダーを使用せずに TOA フィールドを挿入する手順ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-toafield-without-document-builder/
---

ここでは、Aspose.Words for .NET の「TOA フィールド挿入」機能を使用する以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。目的の結果を得るには、各ステップを慎重に実行してください。

## ステップ1: ドキュメントディレクトリの設定

提供されたコードでは、ドキュメントのディレクトリを指定する必要があります。値「YOUR DOCUMENT DIRECTORY」をドキュメント ディレクトリへの適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: 文書と段落を作成する

まず、新しいドキュメントを作成し、段落を初期化します。

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## ステップ3: TAフィールドの挿入

FieldTA クラスを使用して、段落に TA フィールドを挿入します。

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## ステップ4: 文書の本文に段落を追加する

TA フィールドを含む段落をドキュメントの本文に追加します。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## ステップ5: TOAフィールドの段落を作成する

TOA フィールドに新しい段落を作成します。

```csharp
para = new Paragraph(doc);
```

## ステップ6: TOAフィールドの挿入

FieldToa クラスを使用して、段落に TOA フィールドを挿入します。

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## ステップ7: 文書の本文に段落を追加する

TOA フィールドを含む段落をドキュメントの本文に追加します。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## ステップ8: TOAフィールドを更新する

最後に、`Update()`TOA フィールドを更新する方法。

```csharp
fieldToa.Update();
```

### Aspose.Words for .NET を使用した Document Builder なしの TOA フィールド挿入のソース コード例

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

//TA フィールドと TOA フィールドを次のように挿入します。
// { TA \c 1 \l "値 0" }
// {TOA \c 1}

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### よくある質問

#### Q: Aspose.Words for .NET を使用して Word 文書に挿入された TOA フィールドの外観をカスタマイズするにはどうすればよいですか?

A: 挿入されたTOAフィールドの外観は、`FieldTOA`書式設定オプションを指定するオブジェクト。

#### Q: Aspose.Words for .NET を使用して、単一の Word 文書に複数の TOA フィールドを追加できますか?

A: はい、Aspose.Words for .NET を使用して、1 つの Word 文書に複数の TOA フィールドを追加できます。各フィールドに対して挿入手順を繰り返すだけです。

#### Q: Aspose.Words for .NET を使用して TOA フィールドが Word 文書に正常に挿入されたかどうかを確認するにはどうすればよいですか?

A: TOA フィールドが正常に挿入されたかどうかを確認するには、ドキュメント コンテンツを参照して TOA フィールド インスタンスを検索します。

#### Q: DocumentBuilder を使用せずに TOA フィールドを挿入すると、Aspose.Words for .NET による Word 文書の書式設定に影響しますか?

A: DocumentBuilder を使用せずに TOA フィールドを挿入しても、Word 文書の書式設定には直接影響しません。ただし、TOA フィールドの書式設定オプションは、文書全体の書式設定に影響を与える可能性があります。