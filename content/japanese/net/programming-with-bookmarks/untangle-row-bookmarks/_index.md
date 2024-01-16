---
title: Word文書内の行ブックマークのもつれを解く
linktitle: Word文書内の行ブックマークのもつれを解く
second_title: Aspose.Words ドキュメント処理 API
description: Word 文書内のネストされた行ブックマークを解き、他のブックマークに影響を与えずに特定の行を削除する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/untangle-row-bookmarks/
---

この記事では、Aspose.Words for .NET ライブラリの Untangle Row Bookmarks 関数の使用方法を理解するために、上記の C# ソース コードを調べます。この機能を使用すると、行のしおりの末尾をしおりの先頭と同じ行に配置することができます。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: ドキュメントをロードする

私たちが使用するのは、`Document`ファイルから既存のドキュメントをロードするクラス:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## ステップ 2: 行ブックマークを解明する

私たちが使用するのは、`Untangle`行からブックマークを解く関数。この関数は、ブックマークの行末をブックマークの開始と同じ行に配置するカスタム タスクを実行します。

```csharp
Untangle(doc);
```

## ステップ 3: ブックマークによる行の削除

私たちが使用するのは、`DeleteRowByBookmark`ブックマークによって特定の行を削除する関数:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## ステップ 4: 他のブックマークの整合性を確認する

ブックマークの終わりがまだ存在するかどうかをチェックして、他のブックマークが損傷していないことを確認します。

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Aspose.Words for .NET を使用した Untangle Row Bookmarks のソース コード例

Aspose.Words for .NET を使用して行からブックマークを解くための完全なサンプル ソース コードを次に示します。


```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//これにより、行ブックマークの終了点をブックマークの開始点と同じ行に配置するカスタム タスクが実行されます。
	Untangle(doc);

	//他の行のブックマークを損なうことなく、ブックマークによって行を簡単に削除できるようになりました。
	DeleteRowByBookmark(doc, "ROW2");

	//これは、他のブックマークが破損していないかを確認するためだけです。
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### ソースコードのもつれを解く
```csharp

private void Untangle(Document doc)
        {
            foreach (Bookmark bookmark in doc.Range.Bookmarks)
            {
                //ブックマークとブックマーク終了ノードの両方の親行を取得します。
                Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
                Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

                //両方の行に問題がなく、ブックマークの開始と終了が隣接する行に含まれている場合は、
                //ブックマークの終了ノードを最上行の最後のセルの最後の段落の末尾に移動します。
                if (row1 != null && row2 != null && row1.NextSibling == row2)
                    row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
            }
        }

```

#### DeleteRowByBookmark ソース コード
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の Untangle Row Bookmarks 機能の使用方法を理解しました。ステップバイステップのガイドに従って、行ブックマークのもつれを解き、他のブックマークに損傷を与えることなく特定の行を削除しました。

### Word 文書の行ブックマークのもつれを解くための FAQ

#### Q: 行ブックマークのスクランブル解除は、テーブル内の行ブックマークでのみ機能しますか?

A: はい、行ブックマークのもつれを解く機能は、テーブル内の行ブックマークのもつれを解くように特別に設計されています。この関数を使用すると、配列内の行ブックマークを処理し、ブックマークの終了がブックマークの開始と同じ行にあることを確認できます。

#### Q: 行ブックマークのスクランブル解除機能は、元の文書の内容を変更しますか?

A: はい、行ブックマークのスクランブル解除機能は、行ブックマークの終端を移動してブックマークの先頭と同じ行に配置することにより、元の文書を変更します。この機能を適用する前に、必ずドキュメントのバックアップ コピーを保存してください。

#### Q: Word 文書内の行ブックマークを識別するにはどうすればよいですか?

A: 行ブックマークは通常、表で特定のセクションをマークするために使用されます。行ブックマークを識別するには、文書内のブックマークを参照し、ブックマークが表の行にあるかどうかを確認します。

#### Q: 隣接していないテーブルの行ブックマークを解くことはできますか?

A: この記事で紹介されている行ブックマークのもつれを解く機能は、隣接するテーブル内の行ブックマークのもつれを解くように設計されています。隣接しないテーブル内の行ブックマークのもつれを解消するには、ドキュメントの構造によっては、コードへの追加の調整が必要になる場合があります。

#### Q: 行ブックマークが解明された後、行ブックマークに対して他にどのような操作を実行できますか?

A: 行のブックマークが解けたら、必要に応じてさまざまな操作を実行できます。これには、ブックマークされた行へのコンテンツの編集、削除、追加が含まれる場合があります。文書の残りの部分に望ましくない影響が及ばないよう、行ブックマークは慎重に扱ってください。