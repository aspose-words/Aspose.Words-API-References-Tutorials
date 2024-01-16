---
title: ドキュメントビルダーを使用せずにフィールドにテキストを含める挿入
linktitle: ドキュメント ビルダーを使用せずに FieldIncludeText を挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に FieldIncludeText フィールドを挿入する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-field-include-text-without-document-builder/
---

ここでは、Aspose.Words for .NET の「FieldIncludeText フィールドの挿入」機能を使用する、以下の C# ソース コードを説明するステップバイステップ ガイドを示します。望ましい結果を得るために、各ステップを慎重に実行してください。

## ステップ 1: ドキュメント ディレクトリのセットアップ

提供されたコードでは、ドキュメントのディレクトリを指定する必要があります。 「YOUR DOCUMENT DIRECTORY」という値を、ドキュメント ディレクトリへの適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントと段落を作成する

まず、新しいドキュメントを作成し、段落を初期化します。

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## ステップ 3: FieldIncludeText フィールドの挿入

私たちが使用するのは、`AppendField()`メソッドを使用して、FieldIncludeText フィールドを段落に挿入します。

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

次に、ブックマークの名前とソース ファイルの名前を指定して、FieldIncludeText フィールドのプロパティを構成します。

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

次に、文書の本文に段落を追加します。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

最後に、`Update()`フィールドを更新するメソッド。

```csharp
fieldIncludeText.Update();
```

### Aspose.Words for .NET を使用して FieldIncludeText フィールドを挿入するためのソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文書と段落を作成します。
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// FieldIncludeText フィールドを挿入します。
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

この例では、新しいドキュメントを作成し、段落を初期化し、ブックマーク名とソース ファイル名を指定する FieldIncludeTexten を挿入し、指定したファイル名でドキュメントを保存しました。

これで、Aspose.Words for .NET での「FieldIncludeText の挿入」機能の使用に関するガイドは終了です。

### よくある質問

#### Q: Aspose.Words for .NET のテキスト挿入フィールドのソース ファイルを指定するにはどうすればよいですか?

 A: Aspose.Words for .NET のテキスト挿入フィールドのソース ファイルを指定するには、`FieldIncludeText.SourceFullName`プロパティを使用してソース ファイルのフル パスを設定します。ソース ファイルがアクセス可能であり、テキスト挿入フィールドに含めたいコンテンツが含まれていることを確認してください。

#### Q: Aspose.Words for .NET のテキスト挿入フィールドにマクロのテキストを含めることはできますか?

 A: はい、Aspose.Words for .NET を使用すると、マクロのテキストをテキスト挿入フィールドに含めることができます。使用できます`FieldIncludeText.IncludeText`プロパティを使用して、フィールドに内容を含めるマクロの名前を指定します。

#### Q: ドキュメント ビルダーを使用せずにテキスト インクルード フィールドを挿入すると、Aspose.Words for .NET を使用した Word ドキュメントの構造に影響しますか?

A: ドキュメント ビルダーを使用せずにテキスト インクルード フィールドを挿入しても、Word 文書の構造には直接影響しません。ただし、ドキュメントのコンテンツに新しいフィールド要素が追加されます。必要に応じて既存の要素を追加、削除、または変更することで、ドキュメントの構造を操作できます。

#### Q: Aspose.Words for .NET を使用して、Word 文書内のテキスト挿入フィールドの外観をカスタマイズできますか?

A: テキスト挿入フィールドは、Word 文書内の外観を直接カスタマイズしません。ただし、段落プロパティ、フォント プロパティ、および Aspose.Words for .NET で利用可能なその他の書式設定オブジェクトを使用して、含まれるテキストを書式設定することができます。