---
title: Word 文書の行のブックマークを解読する
linktitle: Word 文書の行のブックマークを解読する
second_title: Aspose.Words ドキュメント処理 API
description: Word 文書内のネストされた行のブックマークを解き、他のブックマークに影響を与えずに特定の行を削除する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/untangle-row-bookmarks/
---

この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Untangle Row Bookmarks 関数の使用方法を理解します。この関数を使用すると、行のブックマークの終了をブックマークの開始と同じ行に配置できます。

## 前提条件

- C# 言語に関する基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ1: ドキュメントの読み込み

私たちは`Document`ファイルから既存のドキュメントを読み込むクラス:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## ステップ2: 線のブックマークを解く

私たちは`Untangle`行からブックマークを解きほぐす関数。この関数は、行のブックマークの終了をブックマークの開始と同じ行に配置するというカスタム タスクを実行します。

```csharp
Untangle(doc);
```

## ステップ3: ブックマークで行を削除する

私たちは`DeleteRowByBookmark`ブックマークによって特定の行を削除する関数:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## ステップ4: 他のブックマークの整合性を確認する

ブックマークの末尾がまだ存在するかどうかをチェックして、他のブックマークが破損していないことを確認します。

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Aspose.Words for .NET を使用して行ブックマークを解読するためのサンプル ソース コード

Aspose.Words for .NET を使用して行からブックマークを分離する完全なサンプル ソース コードは次のとおりです。


```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//これは、行のブックマークの終了をブックマークの開始と同じ行に配置するカスタム タスクを実行します。
	Untangle(doc);

	//これで、他の行のブックマークを損傷することなく、ブックマークによって行を簡単に削除できるようになりました。
	DeleteRowByBookmark(doc, "ROW2");

	//これは、他のブックマークが破損していないことを確認するためのものです。
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### ソースコードを解読する
```csharp

private void Untangle(Document doc)
        {
            foreach (Bookmark bookmark in doc.Range.Bookmarks)
            {
                //ブックマークとブックマーク終了ノードの両方の親行を取得します。
                Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
                Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

                //両方の行が正常であり、ブックマークの開始と終了が隣接する行に含まれている場合、
                //ブックマークの終了ノードを、一番上の行の最後のセルの最後の段落の末尾に移動します。
                if (row1 != null && row2 != null && row1.NextSibling == row2)
                    row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
            }
        }

```

#### DeleteRowByBookmark ソースコード
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の Untangle Row Bookmarks 機能の使用方法を理解しました。ステップ バイ ステップ ガイドに従って、行ブックマークを解き、他のブックマークに損傷を与えることなく特定の行を削除しました。

### Word 文書の行のブックマークを解読するための FAQ

#### Q: 行ブックマークのアンスクランブルは、テーブル内の行ブックマークでのみ機能しますか?

A: はい、行ブックマークの解読機能は、テーブル内の行ブックマークを解読するために特別に設計されています。この機能を使用すると、配列内の行ブックマークを処理し、ブックマークの終了がブックマークの開始と同じ行にあることを確認できます。

#### Q: 行ブックマークの解読機能は元の文書の内容を変更しますか?

A: はい、行ブックマークの解読機能は、行ブックマークの末尾をブックマークの先頭と同じ行に移動して元の文書を変更します。この機能を適用する前に、必ず文書のバックアップ コピーを保存してください。

#### Q: Word 文書内の行ブックマークを識別するにはどうすればよいですか?

A: 行ブックマークは通常、表内の特定のセクションをマークするために使用されます。文書内のブックマークを参照し、ブックマークが表の行にあるかどうかを確認することで、行ブックマークを識別できます。

#### Q: 隣接していないテーブルの行ブックマークを解くことは可能ですか?

A: この記事で紹介されている行ブックマークの解読機能は、隣接する表の行ブックマークを解くように設計されています。隣接していない表の行ブックマークを解くには、ドキュメントの構造に応じてコードをさらに調整する必要がある場合があります。

#### Q: 行のブックマークを解いた後、他にどのような操作を実行できますか?

A: 行のブックマークが解除されると、必要に応じてさまざまな操作を実行できます。これには、ブックマークされた行の編集、削除、またはコンテンツの追加が含まれます。文書の残りの部分に不要な影響を与えないように、行のブックマークは慎重に扱ってください。