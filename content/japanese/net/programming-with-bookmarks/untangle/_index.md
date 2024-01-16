---
title: Word文書のもつれを解く
linktitle: Word文書のもつれを解く
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word ドキュメント内で隣接するテーブル行にネストされたブックマークを解く方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/untangle/
---

この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Untangle 関数の使用方法を理解します。この関数は、隣接するテーブル行にあるネストされたブックマークを解明します。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: ドキュメントのブックマークを参照する

foreach ループを使用して、ドキュメント内に存在するすべてのブックマークをループします。

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     //ブックマークを処理するコードはこちら
}
```

## ステップ 2: ブックマークから親行を取得する

私たちが使用するのは、`GetAncestor`ブックマークの開始ノードと終了ノードの親行を取得するメソッド:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## ステップ 3: ネストされたブックマークを解く

両方の親行が見つかり、ブックマークが隣接する行で始まり、終わる場合は、ブックマークの終了ノードを最上行の最後のセルの最後の段落の終わりに移動します。

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Aspose.Words for .NET を使用した Untangle のソース コード例

Aspose.Words for .NET を使用してネストされたブックマークを解くための完全なソース コードの例を次に示します。

```csharp

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

```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の Untangle 関数の使用方法を理解しました。ステップバイステップのガイドに従って、テーブルの隣接する行にあるネストされたブックマークを解きました。

### よくある質問

#### Q: Untangle 関数は、テーブルの隣接する行にあるネストされたブックマークに対してのみ機能しますか?

A: はい、もつれを解く機能は、テーブルの隣接する行にあるネストされたブックマークを解くために特別に設計されています。ブックマークが隣接する行にない場合、この機能は適用されません。

#### Q: Word 文書内のネストされたブックマークを識別するにはどうすればよいですか?

A: ネストされたブックマークを識別するには、文書内のブックマークをループし、開始ブックマークと終了ブックマークが隣接するテーブル行にあるかどうかを確認します。この記事で提供されているソース コードを開始点として使用して、この機能を実装できます。

#### Q: スクランブル解除機能は、元の文書の内容を変更しますか?

A: はい。Untangle 関数は、ブックマークの終了ノードを最上行の最後のセルの最後の段落の末尾に移動することにより、元のドキュメントを変更します。この機能を適用する前に、必ずドキュメントのバックアップ コピーを保存してください。

#### Q: セクションや段落など、他のタイプの文書要素にあるネストされたブックマークを解くにはどうすればよいですか?

A: この記事で紹介する Untangle 関数は、隣接するテーブル行にあるネストされたブックマークを解くように特別に設計されています。他のドキュメント要素にあるネストされたブックマークを解きたい場合は、それに応じてコードを調整し、適切なメソッドを使用して目的の要素にアクセスする必要があります。

#### Q: Aspose.Words for .NET を使用して Word 文書内のネストされたブックマークを解く他の方法はありますか?

 A: この記事で紹介する方法は、テーブルの隣接する行にあるネストされたブックマークを解くための一般的な方法です。ただし、プロジェクトの特定のニーズに応じて、他のアプローチやテクニックが存在する場合があります。チェックアウトできます[Aspose.Words for .NET API リファレンス](https://reference.aspose.com/words/net/)利用可能な機能をさらに詳しく調べるために。