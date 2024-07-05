---
title: 著者フィールドを挿入
linktitle: 著者フィールドを挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に AUTHOR フィールドを挿入する方法を学びます。作成者の名前を指定して、文書をカスタマイズします。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-author-field/
---


ここでは、Aspose.Words for .NET の「AUTHOR フィールドの挿入」機能を使用する以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。目的の結果を得るには、各手順を慎重に実行してください。

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

## ステップ3: AUTHORフィールドを挿入する

私たちは`AppendField()`段落に AUTHOR フィールドを挿入する方法。

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

次にフィールドの`AuthorName`著者名を指定するプロパティ。

```csharp
field. AuthorName = "Test1";
```

最後に、`Update()`フィールドを更新するメソッド。

```csharp
field. Update();
```

### Aspose.Words for .NET を使用して AUTHOR フィールドを挿入するソース コードの例

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントの作成。
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

//AUTHOR フィールドを挿入します。
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

この例では、新しいドキュメントを作成し、AUTHOR フィールドを挿入し、作成者名を設定し、指定したファイル名でドキュメントを保存しました。

これで、Aspose.Words for .NET の「AUTHOR フィールドの挿入」機能の使用に関するガイドは終了です。

### よくある質問

#### Q: Aspose.Words の著者フィールドとは何ですか?

A: Aspose.Words の Author フィールドは、Word 文書に作成者の名前を自動的に挿入および更新する特別なフィールドです。このフィールドは、文書の作成者または変更者を示すためによく使用されます。

#### Q: Aspose.Words を使用して Word 文書の作成者フィールドを更新するにはどうすればよいですか?

A: Word 文書の作成者フィールドを更新して、現在の作成者の名前を反映させることができます。そのためには、Document クラスで使用できる UpdateFields メソッドを使用します。このメソッドは、作成者フィールドを含む文書内のすべてのフィールドを更新します。

#### Q: Word 文書の作成者フィールドの形式をカスタマイズすることは可能ですか?

A: はい、Word 文書の作成者フィールドの書式をカスタマイズできます。既定では、作成者フィールドには作成者の名前のみが表示されます。ただし、Aspose.Words で使用可能な書式設定オプションを使用して、変更日時などの追加情報を追加できます。

#### Q: 著者フィールドは、著者名のその後の変更に影響を受けますか?

A: はい、著者フィールドは著者名のその後の変更に敏感です。ドキュメントのプロパティで著者名を変更すると、ドキュメントのフィールドを更新するときに著者フィールドが新しい名前で自動的に更新されます。