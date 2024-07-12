---
title: ドキュメント ビルダーなしでテキストを含むフィールドを挿入する
linktitle: ドキュメント ビルダーを使用せずに FieldIncludeText を挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に FieldIncludeText フィールドを挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fields/insert-field-include-text-without-document-builder/
---

ここでは、Aspose.Words for .NET の「FieldIncludeText フィールドの挿入」機能を使用する以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。目的の結果を得るには、各手順を慎重に実行してください。

## ステップ1: ドキュメントディレクトリの設定

提供されたコードでは、ドキュメントのディレクトリを指定する必要があります。値「YOUR DOCUMENT DIRECTORY」をドキュメント ディレクトリへの適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: 文書と段落を作成する

まず、新しいドキュメントを作成し、段落を初期化します。

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## ステップ3: FieldIncludeTextフィールドを挿入する

私たちは`AppendField()`段落に FieldIncludeText フィールドを挿入するメソッド。

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

次に、ブックマークの名前とソース ファイルの名前を指定して、FieldIncludeText フィールドのプロパティを構成します。

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

次に、ドキュメントの本文に段落を追加します。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

最後に、`Update()`フィールドを更新するメソッド。

```csharp
fieldIncludeText.Update();
```

### Aspose.Words for .NET を使用して FieldIncludeText フィールドを挿入するためのソース コードの例

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントと段落を作成します。
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

この例では、新しいドキュメントを作成し、段落を初期化し、ブックマーク名とソース ファイル名を指定する FieldIncludeTexten を挿入し、指定されたファイル名でドキュメントを保存しました。

これで、Aspose.Words for .NET の「FieldIncludeText の挿入」機能の使用に関するガイドは終了です。

### よくある質問

#### Q: Aspose.Words for .NET のテキスト包含フィールドのソース ファイルを指定するにはどうすればよいですか?

 A: Aspose.Words for .NETのテキスト包含フィールドのソースファイルを指定するには、`FieldIncludeText.SourceFullName`プロパティを使用して、ソース ファイルの完全なパスを設定します。ソース ファイルがアクセス可能であり、テキスト包含フィールドに含めるコンテンツが含まれていることを確認します。

#### Q: Aspose.Words for .NET のテキスト包含フィールドにマクロからのテキストを含めることはできますか?

 A: はい、Aspose.Words for .NETのテキスト挿入フィールドにマクロのテキストを挿入することができます。`FieldIncludeText.IncludeText`フィールドに含める内容のマクロの名前を指定するプロパティ。

#### Q: ドキュメント ビルダーを使用せずにテキスト インクルード フィールドを挿入すると、Aspose.Words for .NET を使用した Word ドキュメントの構造に影響しますか?

A: ドキュメント ビルダーを使用せずにテキスト インクルード フィールドを挿入しても、Word ドキュメントの構造に直接影響はありません。ただし、ドキュメント コンテンツに新しいフィールド要素が追加されます。必要に応じて既存の要素を追加、削除、または変更することで、ドキュメント構造を操作できます。

#### Q: Aspose.Words for .NET を使用して Word 文書内のテキスト包含フィールドの外観をカスタマイズできますか?

A: テキスト挿入フィールドは、Word 文書内での外観を直接カスタマイズするものではありません。ただし、段落プロパティ、フォント プロパティ、および Aspose.Words for .NET で使用できるその他の書式設定オブジェクトを使用して、挿入テキストを書式設定できます。