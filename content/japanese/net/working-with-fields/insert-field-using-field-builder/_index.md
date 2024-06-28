---
title: フィールドビルダーを使用してフィールドを挿入する
linktitle: フィールドビルダーを使用してフィールドを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書にカスタム フィールドを挿入する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-field-using-field-builder/
---

ここでは、Aspose.Words for .NET の「FieldBuilder を使用してフィールドを挿入」機能を使用する、以下の C# ソース コードを説明するステップバイステップ ガイドを示します。望ましい結果を得るために、各ステップを慎重に実行してください。

## ステップ 1: ドキュメント ディレクトリのセットアップ

提供されたコードでは、ドキュメントのディレクトリを指定する必要があります。 「YOUR DOCUMENT DIRECTORY」という値を、ドキュメント ディレクトリへの適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントの作成

新しいドキュメントを作成することから始めます。

```csharp
Document doc = new Document();
```

## ステップ 3: FieldBuilder を使用して IF フィールドを構築する

FieldBuilder クラスを使用して、2 つのネストされた MERGEFIELD フィールドを持つ IF フィールドを構築します。この例では、IF フィールドに条件に基づいて姓と名が表示されます。

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

## ステップ 4: IF フィールドをドキュメントに挿入する

私たちが使用するのは、`BuildAndInsert()`IF フィールドを作成し、ドキュメント内の特定の場所に挿入するメソッド。

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### FieldBuilder と Aspose.Words for .NET を使用してフィールドを挿入するためのソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//書類作成。
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

// IF フィールドをドキュメントに挿入します。
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

この例では、新しいドキュメントを作成し、ネストされた MERGEFIELD フィールドを含む IF フィールドを構築し、そのフィールドをドキュメントの指定された場所に挿入しました。ドキュメントは特定のファイル名で保存されます。

### よくある質問

#### Q: Aspose.Words のフィールド コンストラクターとは何ですか?

A: Aspose.Words のフィールド ビルダーは、Word 文書内のフィールドを作成および操作するための強力なツールです。フィールド コードの挿入や書式設定オプションの管理など、フィールドの構築とカスタマイズのための高度な機能を提供します。

#### Q: フィールド ビルダーを使用して挿入できるフィールドの種類は何ですか?

A: Aspose.Words のフィールド ビルダーを使用すると、さまざまな種類のフィールドを Word 文書に挿入できます。一般的に使用されるフィールド タイプの例をいくつか示します。

- MERGEFIELD: 外部ソースからのデータをマージするために使用されます。
- DATE: 現在の日付を表示します。
- PAGE: 現在のページ番号を表示します。
- IF: 条件に従ってコンテンツの表示を調整できます。
- 目次: ドキュメントのタイトル スタイルに基づいて目次を自動的に生成します。

#### Q: フィールド ビルダーで挿入されたフィールドをカスタマイズするにはどうすればよいですか?

A: フィールド ビルダーは、挿入されたフィールドのカスタマイズ オプションを提供します。フィールド コンストラクターのメソッドとプロパティを使用して、フィールドの書式設定、引数、スイッチ、デフォルト値などのオプションを設定できます。たとえば、日付形式、数値形式、桁区切り文字などを設定できます。
  