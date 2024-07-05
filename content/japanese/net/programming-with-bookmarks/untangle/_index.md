---
title: Word文書のもつれを解く
linktitle: Word文書のもつれを解く
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の隣接する表の行にネストされたブックマークを解く方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/untangle/
---

この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Untangle 関数の使用方法を理解します。この関数は、隣接するテーブル行にあるネストされたブックマークを解きます。

## 前提条件

- C# 言語に関する基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ1: ドキュメントのブックマークを参照する

foreach ループを使用して、ドキュメント内に存在するすべてのブックマークをループします。

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     //ブックマークを処理するためのコードをここに記述します
}
```

## ステップ2: ブックマークから親行を取得する

私たちは`GetAncestor`ブックマークの開始ノードと終了ノードの親行を取得するメソッド:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## ステップ3: ネストされたブックマークを解く

両方の親行が見つかり、ブックマークが隣接する行で始まり、終了する場合は、ブックマークの終了ノードを最上行の最後のセルの最後の段落の末尾に移動します。

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Aspose.Words for .NET を使用した Untangle のサンプル ソース コード

以下は、Aspose.Words for .NET を使用してネストされたブックマークを解くための完全なソース コードの例です。

```csharp

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

```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の Untangle 関数の使用方法を理解しました。隣接するテーブル行のネストされたブックマークを解く手順をステップ バイ ステップで説明しました。

### よくある質問

#### Q: Untangle 機能は、隣接するテーブル行のネストされたブックマークでのみ機能しますか?

A: はい、Untangle 機能は、隣接する表の行にあるネストされたブックマークを解くために特別に設計されています。ブックマークが隣接する行にない場合、この機能は適用されません。

#### Q: Word 文書内のネストされたブックマークを識別するにはどうすればよいですか?

A: ドキュメント内のブックマークをループし、開始ブックマークと終了ブックマークが隣接するテーブル行にあるかどうかを確認することで、ネストされたブックマークを識別できます。 この記事で提供されているソース コードを出発点として使用して、この機能を実装できます。

#### Q: アンスクランブル機能は元の文書の内容を変更しますか?

A: はい、Untangle 機能は、ブックマークの終了ノードを最上行の最後のセルの最後の段落の末尾に移動することで、元のドキュメントを変更します。この機能を適用する前に、ドキュメントのバックアップ コピーを必ず保存してください。

#### Q: セクションや段落など、他の種類のドキュメント要素内のネストされたブックマークを分離するにはどうすればよいですか?

A: この記事で紹介されている Untangle 関数は、隣接するテーブル行のネストされたブックマークを解くために特別に設計されています。他のドキュメント要素のネストされたブックマークを解く場合は、それに応じてコードを調整し、適切な方法を使用して目的の要素にアクセスする必要があります。

#### Q: Aspose.Words for .NET を使用して Word 文書内のネストされたブックマークを解く他の方法はありますか?

 A: この記事で紹介した方法は、隣接する表の行にネストされたブックマークを解く一般的な方法です。ただし、プロジェクトの特定のニーズに応じて、他のアプローチやテクニックがある場合があります。[Aspose.Words for .NET API リファレンス](https://reference.aspose.com/words/net/)利用可能な機能をさらに詳しく調べます。