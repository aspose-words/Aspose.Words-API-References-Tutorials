---
title: ドキュメントビルダーなしでASKFieldを挿入する
linktitle: ドキュメントビルダーなしでASKFieldを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に ASK フィールドを挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-askfield-with-out-document-builder/
---

ここでは、Aspose.Words for .NET の「DocumentBuilder を使用せずに ASK フィールドを挿入する」機能を使用する、以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。目的の結果を得るには、各手順を慎重に実行してください。

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

## ステップ3: ASKフィールドの挿入

私たちは`AppendField()`段落に ASK フィールドを挿入する方法。

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

次に、必要な値を指定して、ASK フィールドのさまざまなプロパティを構成します。

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

最後に、`Update()`フィールドを更新するメソッド。

```csharp
field. Update();
```

### Aspose.Words for .NET を使用して DocumentBuilder なしで ASK フィールドを挿入するソース コードの例

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントの作成。
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

//ASK フィールドを挿入します。
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

この例では、新しいドキュメントを作成し、DocumentBuilder を使用せずに ASK フィールドを挿入し、フィールドのさまざまなプロパティを構成し、指定されたファイル名でドキュメントを保存しました。

これで、Aspose.Words for .NET で「DocumentBuilder を使用せずに ASK フィールドを挿入」機能を使用するガイドは終了です。

### よくある質問

#### Q: Aspose.Words の ASK フィールドとは何ですか?

A: Aspose.Words の ASK フィールドは、ドキュメントを開くときにユーザーに質問するために使用されます。ユーザーごとに異なる特定の情報やフィードバックを要求するためによく使用されます。

#### Q: Aspose.Words の Document Builder を使用せずに Word 文書に ASK フィールドを挿入するにはどうすればよいですか?

A: Aspose.Words の Document Builder を使用せずに Word 文書に ASK フィールドを挿入するには、次の手順に従います。

1. Aspose.Words.Fields 名前空間から Document クラスと Field クラスをインポートします。
2. 既存のドキュメントを読み込んで Document のインスタンスを作成します。
3. 質問名を指定して ASK フィールドを挿入するには、InsertField メソッドを使用します。
4. ドキュメントを保存します。

#### Q: Word 文書の ASK フィールドに対するユーザーの応答を取得するにはどうすればよいですか?

A: Word 文書内の ASK フィールドに対するユーザーの応答を取得するには、Document クラスで使用可能な GetFieldNames メソッドを使用できます。このメソッドは、文書内に存在するフィールドの名前のリストを返します。次に、ASK フィールド名がリスト内に存在するかどうかを確認し、関連する応答を取得できます。

#### Q: ASK フィールドを使用して、ユーザーにさらに情報を要求できますか?

A: はい、ASK フィールドを使用して、ユーザーから複数の情報を要求できます。ドキュメントに複数の ASK フィールドを挿入し、それぞれに異なる質問を設定できます。ドキュメントを開くと、ユーザーは対応する回答を求められます。