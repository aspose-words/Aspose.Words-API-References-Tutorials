---
title: フィールドビルダーを使用してフィールドを挿入する
linktitle: フィールドビルダーを使用してフィールドを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書にカスタム フィールドを挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-field-using-field-builder/
---

ここでは、Aspose.Words for .NET の「FieldBuilder を使用してフィールドを挿入する」機能を使用する、以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。目的の結果を得るには、各手順を慎重に実行してください。

## ステップ1: ドキュメントディレクトリの設定

提供されたコードでは、ドキュメントのディレクトリを指定する必要があります。値「YOUR DOCUMENT DIRECTORY」をドキュメント ディレクトリへの適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントの作成

まず、新しいドキュメントを作成します。

```csharp
Document doc = new Document();
```

## ステップ3: FieldBuilderを使用してIFフィールドを構築する

FieldBuilder クラスを使用して、2 つのネストされた MERGEFIELD フィールドを持つ IF フィールドを構築します。この例では、IF フィールドは条件に基づいて名と姓を表示します。

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## ステップ4: ドキュメントにIFフィールドを挿入する

私たちは`BuildAndInsert()`ドキュメント内の特定の場所に IF フィールドを構築して挿入する方法。

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Aspose.Words for .NET で FieldBuilder を使用してフィールドを挿入するためのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントの作成。
Document doc = new Document();

//FieldBuilder を使用した IF フィールドの構築。
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

//ドキュメントに IF フィールドを挿入します。
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

この例では、新しいドキュメントを作成し、ネストされた MERGEFIELD フィールドを含む IF フィールドを構築し、そのフィールドをドキュメントの指定された場所に挿入しました。その後、ドキュメントは特定のファイル名で保存されます。

### よくある質問

#### Q: Aspose.Words のフィールド コンストラクターとは何ですか?

A: Aspose.Words のフィールド ビルダーは、Word 文書内のフィールドを作成および操作するための強力なツールです。フィールド コードの挿入や書式設定オプションの管理など、フィールドの構築とカスタマイズのための高度な機能を提供します。

#### Q: フィールド ビルダーを使用して挿入できるフィールドの種類は何ですか?

A: Aspose.Words のフィールド ビルダーを使用すると、さまざまな種類のフィールドを Word 文書に挿入できます。よく使用されるフィールドの種類の例を次に示します。

- MERGEFIELD: 外部ソースからのデータをマージするために使用されます。
- DATE: 現在の日付を表示します。
- PAGE: 現在のページ番号を表示します。
- IF: 条件に応じてコンテンツの表示を制限できます。
- TOC: ドキュメントのタイトル スタイルに基づいて目次を自動的に生成します。

#### Q: フィールド ビルダーで挿入されたフィールドをカスタマイズするにはどうすればよいですか?

A: フィールド ビルダーには、挿入されたフィールドのカスタマイズ オプションが用意されています。フィールド コンストラクター メソッドとプロパティを使用して、フィールドの書式設定、引数、スイッチ、既定値などのオプションを設定できます。たとえば、日付形式、数値形式、3 桁ごとの区切りなどを設定できます。
  