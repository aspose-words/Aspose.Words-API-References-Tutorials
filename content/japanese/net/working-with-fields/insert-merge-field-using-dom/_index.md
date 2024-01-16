---
title: DOM を使用して差し込みフィールドを挿入
linktitle: DOM を使用して差し込みフィールドを挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してカスタム フィールド差し込みフィールドを Word 文書に挿入する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-merge-field-using-dom/
---

ここでは、Aspose.Words for .NET の「フィールド結合フィールドの挿入」機能を使用する以下の C# ソース コードを説明するステップバイステップ ガイドを示します。望ましい結果を得るために、各ステップを慎重に実行してください。

## ステップ 1: ドキュメント ディレクトリのセットアップ

提供されたコードでは、ドキュメントのディレクトリを指定する必要があります。 「YOUR DOCUMENT DIRECTORY」という値を、ドキュメント ディレクトリへの適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントと DocumentBuilder の作成

まず、新しいドキュメントを作成し、DocumentBuilder を初期化します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 3: カーソルを段落に移動する

私たちが使用するのは、`MoveTo()` DocumentBuilder のメソッドを使用して、フィールド差し込みフィールドを挿入する段落にカーソルを移動します。

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## ステップ 4: フィールド差し込みフィールドの挿入

DocumentBuilder を使用します。`InsertField()`フィールド差し込みフィールドを段落に挿入するメソッド。

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

次に、フィールド名、フィールドの前後のテキスト、垂直書式オプションなどの適切なオプションを指定して、フィールド差し込みフィールドのプロパティを構成します。

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

最後に、`Update()`フィールドを更新するメソッド。

```csharp
field. Update();
```

### Aspose.Words for .NET を使用してフィールド差し込みフィールドを挿入するためのサンプル ソース コード

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントとDocumentBuilderを作成します。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//カーソルを段落に移動します。
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

//フィールド差し込みフィールドを挿入します。
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

//フィールドを更新します。
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

この例では、新しい文書を作成し、カーソルを目的の段落に移動して、その文書にフィールド差し込みフィールドを挿入しました。

### よくある質問

#### Q: Aspose.Words for .NET と DOM を使用して Word 文書に差し込みフィールドを挿入するにはどうすればよいですか?

A: Aspose.Words for .NET と DOM を使用して Word 文書に差し込みフィールドを挿入するには、次の手順に従います。

1. 差し込みフィールドを挿入する段落に移動します。
2. を作成します`FieldMergeField`物体。
3. フィールド名や書式設定オプションなどの差し込みフィールドのプロパティを設定します。
4. を使用して段落に差し込みフィールドを追加します。`Paragraph.AppendChild`方法。

#### Q: Aspose.Words for .NET で差し込みフィールドのソース データを指定するにはどうすればよいですか?

A: Aspose.Words for .NET で差し込みフィールドのソース データを指定するには、`FieldMergeField.FieldName` CSV ファイルやデータベースなどの外部データ ソース内のフィールドの名前である差し込みフィールド名を設定するメソッド。`FieldMergeField.Text`差し込みフィールドの値を直接設定するメソッド。

#### Q: Aspose.Words for .NET を使用して Word 文書の差し込みフィールドの外観をカスタマイズできますか?

 A: はい、Aspose.Words for .NET を使用して Word 文書の差し込みフィールドの外観をカスタマイズできます。のプロパティを使用して、大文字と小文字、フォント、色などの書式設定オプションを設定できます。`FieldMergeField`物体。

#### Q: Aspose.Words for .NET を使用して差し込みフィールドが Word 文書に正常に挿入されたかどうかを確認するにはどうすればよいですか?

 A: 差し込みフィールドが正常に挿入されたかどうかを確認するには、ドキュメントのコンテンツを参照して、差し込みフィールドのインスタンスを検索します。のメソッドとプロパティを使用できます。`Document`オブジェクトを使用して、文書の段落、フィールド、その他の要素にアクセスします。

#### Q: DOM を使用して差し込みフィールドを挿入すると、Aspose.Words for .NET での Word ドキュメントの構造に影響しますか?

A: DOM を使用して差し込みフィールドを挿入しても、Word 文書の構造には直接影響しません。ただし、ドキュメントのコンテンツに新しいフィールド要素が追加されます。必要に応じて既存の要素を追加、削除、または変更することで、ドキュメントの構造を操作できます。