---
title: ドキュメントビルダーを使用せずに ASKField を挿入する
linktitle: ドキュメントビルダーを使用せずに ASKField を挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に ASK フィールドを挿入する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-askfield-with-out-document-builder/
---

ここでは、Aspose.Words for .NET の「DocumentBuilder を使用せずに ASK フィールドを挿入」機能を使用する、以下の C# ソース コードを説明するステップバイステップ ガイドを示します。望ましい結果を得るために、各ステップを慎重に実行してください。

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

## ステップ 3: ASK フィールドの挿入

私たちが使用するのは、`AppendField()`ASK フィールドを段落に挿入するメソッド。

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

### DocumentBuilder を使用せずに Aspose.Words for .NET を使用して ASK フィールドを挿入するソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//書類作成。
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

//ASKフィールドを挿入します。
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

この例では、新しいドキュメントを作成し、DocumentBuilder を使用せずに ASK フィールドを挿入し、フィールドのさまざまなプロパティを構成して、指定したファイル名でドキュメントを保存しました。

これで、Aspose.Words for .NET での「DocumentBuilder を使用しない ASK フィールドの挿入」機能の使用に関するガイドは終了です。

### よくある質問

#### Q: Aspose.Words の ASK フィールドとは何ですか?

A: Aspose.Words の ASK フィールドは、ドキュメントを開いたときにユーザーに質問するために使用されます。ユーザーごとに異なる特定の情報やフィードバックを要求するためによく使用されます。

#### Q: Aspose.Words のドキュメント ビルダーを使用せずに Word 文書に ASK フィールドを挿入するにはどうすればよいですか?

A: Aspose.Words のドキュメント ビルダーを使用せずに Word 文書に ASK フィールドを挿入するには、次の手順に従います。

1. Aspose.Words.Fields 名前空間から Document および Field クラスをインポートします。
2. 既存のドキュメントをロードして、Document のインスタンスを作成します。
3. InsertField メソッドを使用して、質問名を指定して ASK フィールドを挿入します。
4. 文書を保存します。

#### Q: Word 文書の ASK フィールドに対するユーザーの応答を取得するにはどうすればよいですか?

A: Word 文書の ASK フィールドに対するユーザーの応答を取得するには、Document クラスで使用できる GetFieldNames メソッドを使用できます。このメソッドは、ドキュメント内に存在するフィールド名のリストを返します。その後、ASK フィールド名がリストに存在するかどうかを確認し、関連する応答を取得できます。

#### Q: ASK フィールドを使用して、ユーザーに詳細情報を要求できますか?

A: はい、ASK フィールドを使用してユーザーに複数の情報を要求できます。文書に複数の ASK フィールドを挿入し、それぞれに異なる質問を含めることができます。文書を開くと、ユーザーは対応する回答を求められます。