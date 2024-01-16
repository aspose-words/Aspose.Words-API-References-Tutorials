---
title: Word文書内の表のセルに移動
linktitle: Word文書内の表のセルに移動
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の Word ドキュメント機能で表のセルに移動を使用するためのステップバイステップ ガイド
type: docs
weight: 10
url: /ja/net/add-content-using-documentbuilder/move-to-table-cell/
---
この例では、提供された C# ソース コードを使用して、Aspose.Words for .NET の Word ドキュメントでテーブル セルに移動機能を使用する方法をステップごとに説明します。この機能を使用すると、Word 文書の表内の特定のセルに移動して操作できます。この機能をアプリケーションに統合するには、次の手順に従ってください。

## ステップ 1: 表を含むドキュメントをロードする

まず、セルを移動するテーブルを含むドキュメントをロードする必要があります。この手順を実行するには、次のコードを使用します。

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

このコードは、指定されたドキュメントをロードします (「MyDir +」Tables.docx を置き換えます)「」テーブルを含むドキュメントの実際のパスに置き換えます)。

## ステップ 2: DocumentBuilder を特定の表のセルに移動する

次に、DocumentBuilder を特定のテーブル セルに移動します。このステップを実行するには、次のコードを使用します。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

このコードは、既存のドキュメントから DocumentBuilder を作成し、カーソルを DocumentBuilder から指定された表のセルに移動します。最後に、DocumentBuilder のメソッドを使用してそのセルにコンテンツを追加します。`Write()`方法。

## ステップ 3: 結果を確認する

これで、表のセルへの移動が成功したことを確認できます。この手順を実行するには、次のコードを使用します。

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

このコードは、指定されたセルが実際に DocumentBuilder の現在のセルであることを検証します。また、DocumentBuilder によって追加されたコンテンツが表のセルに正しく保存されていることも検証します。

それだけです ！提供されたソース コードを使用して、Aspose.Words for .NET のテーブル セルへの移動機能を使用する方法を理解しました。この機能を独自のアプリケーションに統合し、Word 文書内の特定の表のセルを操作できるようになりました。


### Aspose.Words for .NET を使用してテーブルのセルに移動するソース コードの例


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

//ビルダーを最初のテーブルの行 3、セル 4 に移動します。
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

## 結論

この例では、Aspose.Words for .NET のテーブル セルへの移動機能を調べました。表を含むドキュメントをロードし、DocumentBuilder を特定の表のセルに移動し、そのセルにコンテンツを追加する方法を学習しました。この機能は、Aspose.Words for .NET を使用してプログラムで Word ドキュメント テーブル内の特定のセルを移動および操作するための強力なツールを開発者に提供します。これは、動的な Word 文書処理やテーブル コンテンツ管理のためのアプリケーションに有益な追加機能となります。

### Word文書内の表のセルへの移動に関するFAQ

#### Q: Aspose.Words for .NET のテーブル セルへ移動機能の目的は何ですか?

A: Aspose.Words for .NET の表セルへの移動機能を使用すると、開発者は Word 文書内の表内の特定のセルにプログラム的に移動して操作できます。特定のセル内のコンテンツを挿入、変更、または削除する機能を提供します。

#### Q: DocumentBuilder を Word 文書内の特定の表のセルに移動するにはどうすればよいですか?

A: DocumentBuilder を Word 文書内の特定の表のセルに移動するには、DocumentBuilder クラスの MoveToCell メソッドを使用できます。このメソッドは、テーブル内のターゲット行とセルのインデックスをパラメータとして受け取り、そのセルの先頭にカーソルを配置します。

#### Q: 表のセルに移動機能を使用して特定の表のセルに移動した後、コンテンツを追加または変更できますか?

A: はい、MoveToCell を使用して DocumentBuilder を目的の表のセルに配置したら、Write、Writeln、InsertHtml などの DocumentBuilder クラスのさまざまなメソッドを使用して、そのセルのコンテンツを追加または変更できます。

#### Q: 表のセルへの移動が成功したことを確認するにはどうすればよいですか?

A: DocumentBuilder のカーソルの位置をチェックすることで、表のセルへの移動が成功したかどうかを確認できます。たとえば、DocumentBuilder の現在のノードと移動先のセルを比較し、DocumentBuilder によって追加されたコンテンツが表のセルに正しく保存されていることを確認できます。