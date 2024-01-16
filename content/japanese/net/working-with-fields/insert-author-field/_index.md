---
title: 著者フィールドを挿入
linktitle: 著者フィールドを挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に AUTHOR フィールドを挿入する方法を学びます。作成者の名前を指定してドキュメントをカスタマイズします。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-author-field/
---


ここでは、Aspose.Words for .NET の「AUTHOR フィールドの挿入」機能を使用する、以下の C# ソース コードを説明するステップバイステップ ガイドを示します。望ましい結果を得るために、各ステップを慎重に実行してください。

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

## ステップ 3: AUTHOR フィールドを挿入する

私たちが使用するのは、`AppendField()`AUTHOR フィールドを段落に挿入するメソッド。

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

次に、フィールドの設定を行います。`AuthorName`プロパティを使用して作成者の名前を指定します。

```csharp
field. AuthorName = "Test1";
```

最後に、`Update()`フィールドを更新するメソッド。

```csharp
field. Update();
```

### Aspose.Words for .NET で AUTHOR フィールドを挿入するソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//書類作成。
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

//AUTHORフィールドを挿入します。
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

この例では、新しいドキュメントを作成し、AUTHOR フィールドを挿入し、作成者名を構成して、指定したファイル名でドキュメントを保存しました。

これで、Aspose.Words for .NET での「AUTHOR フィールドの挿入」機能の使用に関するガイドは終わりです。

### よくある質問

#### Q: Aspose.Words の作成者フィールドとは何ですか?

A: Aspose.Words の作成者フィールドは、Word 文書に作成者の名前を自動的に挿入して更新する特別なフィールドです。文書の作成者または変更者を示すためによく使用されます。

#### Q: Aspose.Words を使用して Word 文書の作成者フィールドを更新するにはどうすればよいですか?

A: Word 文書の作成者フィールドは、現在の作成者の名前を反映するように更新できます。このために、Document クラスで使用可能な UpdateFields メソッドを使用できます。このメソッドは、著者フィールドを含むドキュメント内のすべてのフィールドを更新します。

#### Q: Word 文書の作成者フィールドの形式をカスタマイズすることはできますか?

A: はい、Word 文書の作成者フィールドの形式をカスタマイズできます。デフォルトでは、作成者フィールドには単純に作成者の名前が表示されます。ただし、Aspose.Words で使用できる書式設定オプションを使用して、変更日時などの追加情報を追加できます。

#### Q: 著者フィールドは、その後の著者名変更の影響を受けやすいですか?

A: はい、著者フィールドは、その後の著者名変更の影響を受けます。ドキュメントのプロパティで作成者名を変更すると、ドキュメント フィールドの更新時に作成者フィールドが新しい名前で自動的に更新されます。