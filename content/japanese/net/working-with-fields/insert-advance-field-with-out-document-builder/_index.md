---
title: ドキュメントビルダーを使用せずに高度なフィールドを挿入する
linktitle: ドキュメントビルダーを使用せずに高度なフィールドを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に高度なフィールドを挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

ここでは、Aspose.Words for .NET の「DocumentBuilder を使用しない高度なフィールド挿入」機能を使用する以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。目的の結果を得るには、各手順を慎重に実行してください。

## ステップ1: ドキュメントディレクトリの設定

提供されたコードでは、ドキュメントのディレクトリを指定する必要があります。値「YOUR DOCUMENT DIRECTORY」をドキュメント ディレクトリへの適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: 文書と段落を作成する

まず、新しいドキュメントを作成し、最初の段落を取得します。

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## ステップ3: 高度なフィールドを挿入する

私たちは`AppendField()`段落に高度なフィールドを挿入する方法。

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

次に、必要な値を指定して、高度なフィールドのさまざまなプロパティを構成します。

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

### Aspose.Words for .NET を使用して DocumentBuilder を使用せずに高度なフィールドを挿入するソース コードの例

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントの作成。
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

この例では、新しいドキュメントを作成し、DocumentBuilder を使用せずに高度なフィールドを挿入し、さまざまなフィールド プロパティを構成し、指定されたファイル名でドキュメントを保存しました。

これで、Aspose.Words for .NET で「DocumentBuilder を使用せずに高度なフィールドを挿入」機能を使用する方法に関するガイドは終了です。

### よくある質問

#### Q: Aspose.Words の高度なフィールドとは何ですか?

A: Aspose.Words の Advance Field は、Word 文書内で計算を実行したり、条件を含めたり、複雑な操作を実行したりできる特殊なタイプのフィールドです。動的フィールドやカスタム フィールドを作成するための優れた柔軟性を提供します。

#### Q: Aspose.Words の Document Builder を使用せずに Word 文書に高度なフィールドを挿入するにはどうすればよいですか?

A: Aspose.Words の Document Builder を使用せずに Word 文書に高度なフィールドを挿入するには、次の手順に従います。

1. Aspose.Words.Fields 名前空間から Document クラスと Field クラスをインポートします。
2. 既存のドキュメントを読み込んで Document のインスタンスを作成します。
3. 高度なフィールド コードを指定して高度なフィールドを挿入するには、InsertField メソッドを使用します。
4. ドキュメントを保存します。

#### Q: Word 文書の詳細フィールドの結果を取得するにはどうすればよいですか?

A: Word 文書の高度なフィールドの結果を取得するには、Field クラスで使用可能な Result プロパティを使用できます。このプロパティは、フィールドの計算結果を返します。

#### Q: Word 文書に高度なフィールドを挿入した後で、そのフィールドの数式を変更できますか?

A: はい、Word 文書に挿入した後で、高度なフィールドの数式を編集できます。これを行うには、Field クラスの FieldCode プロパティにアクセスし、数式テキストを変更して数式を更新します。