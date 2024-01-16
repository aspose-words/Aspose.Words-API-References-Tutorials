---
title: ドキュメントビルダーを使用しないアドバンスフィールドの挿入
linktitle: ドキュメントビルダーを使用しないアドバンスフィールドの挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に高度なフィールドを挿入する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

ここでは、Aspose.Words for .NET の「DocumentBuilder を使用しない高度なフィールド挿入」機能を使用する、以下の C# ソース コードを説明するステップバイステップ ガイドを示します。望ましい結果を得るために、各ステップを慎重に実行してください。

## ステップ 1: ドキュメント ディレクトリのセットアップ

提供されたコードでは、ドキュメントのディレクトリを指定する必要があります。 「YOUR DOCUMENT DIRECTORY」という値を、ドキュメント ディレクトリへの適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントと段落を作成する

まず、新しいドキュメントを作成し、最初の段落を取得します。

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## ステップ 3: 詳細フィールドの挿入

私たちが使用するのは、`AppendField()`高度なフィールドを段落に挿入するメソッド。

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

次に、必要な値を指定して、詳細フィールドのさまざまなプロパティを構成します。

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

最後に、`Update()`フィールドを更新するメソッド。

```csharp
field. Update();
```

### DocumentBuilder を使用せずに Aspose.Words for .NET を使用して詳細フィールドを挿入するソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//書類作成。
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

//詳細フィールドを挿入します。
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

この例では、新しいドキュメントを作成し、DocumentBuilder を使用せずに詳細フィールドを挿入し、さまざまなフィールド プロパティを構成して、指定したファイル名でドキュメントを保存しました。

これで、Aspose.Words for .NET で「DocumentBuilder を使用しない高度なフィールドの挿入」機能を使用する方法に関するガイドは終了です。

### よくある質問

#### Q: Aspose.Words の高度なフィールドとは何ですか?

A: Aspose.Words の Advance フィールドは、Word 文書内で計算を実行したり、条件を含めたり、複雑な操作を実行したりできる特別なタイプのフィールドです。動的フィールドとカスタムフィールドを作成するための優れた柔軟性を提供します。

#### Q: Aspose.Words のドキュメント ビルダーを使用せずに、Word ドキュメントに詳細フィールドを挿入するにはどうすればよいですか?

A: Aspose.Words のドキュメント ビルダーを使用せずに Word 文書に詳細フィールドを挿入するには、次の手順に従います。

1. Aspose.Words.Fields 名前空間から Document および Field クラスをインポートします。
2. 既存のドキュメントをロードして、Document のインスタンスを作成します。
3. InsertField メソッドを使用して、詳細フィールド コードを指定して詳細フィールドを挿入します。
4. 文書を保存します。

#### Q: Word 文書の詳細フィールドの結果を取得するにはどうすればよいですか?

A: Word 文書の詳細フィールドの結果を取得するには、Field クラスで使用できる Result プロパティを使用できます。このプロパティは、フィールドの計算結果を返します。

#### Q: 詳細フィールドを Word 文書に挿入した後にその数式を変更できますか?

A: はい、詳細フィールドの数式は、Word 文書に挿入した後に編集できます。これを行うには、Field クラスの FieldCode プロパティにアクセスし、数式テキストを変更して数式を更新します。