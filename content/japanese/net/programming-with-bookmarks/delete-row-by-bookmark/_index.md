---
title: Word文書のブックマークによる行の削除
linktitle: Word文書のブックマークによる行の削除
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の特定のブックマークに基づいてテーブル行を削除する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/delete-row-by-bookmark/
---

この記事では、Aspose.Words for .NET ライブラリの Delete Row By Bookmark 関数の使用方法を理解するために、上記の C# ソース コードを調べます。この機能を使用すると、Word 文書内の特定のブックマークに基づいて表の行を削除できます。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: ブックマークを取得する

私たちが使用するのは、`Bookmarks`ドキュメント範囲のプロパティを使用して、テーブル行を削除するために使用する特定のブックマークを取得します。

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## ステップ 2: テーブルの行を削除する

私たちが使用するのは、`GetAncestor`を取得する方法`Row`ブックマークの親要素を入力します。次に、`Remove`テーブルの行を削除するメソッド:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Aspose.Words for .NET を使用したブックマークによる行の削除のソース コード例

Aspose.Words for .NET を使用して特定のブックマークに基づいてテーブル行を削除する方法を示す完全なサンプル ソース コードを次に示します。

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET のブックマークによる行の削除機能の使用方法を理解しました。ステップバイステップのガイドに従って、ドキュメント内の特定のブックマークに基づいてテーブルの行を削除しました。

### Word文書のブックマークによる行の削除に関するFAQ

#### Q: 同じブックマークを使用して複数の行を削除できますか?

A: はい、同じブックマークを使用して複数の行を削除できます。ただし、コード内のロジックを処理して、削除する行数を決定し、提供されたコード スニペットに必要な調整を行う必要があります。

#### Q: ドキュメント内にブックマークが存在しない場合はどうなりますか?

A: 指定されたブックマークがドキュメント内に存在しない場合、コード スニペットはブックマーク オブジェクトに対して null 値を返します。したがって、テーブル行を削除する前に適切なチェックを追加して、コード内でこのシナリオを処理する必要があります。

#### Q: Aspose.Words ライブラリは無料で使用できますか?

 A: Aspose.Words ライブラリは商用ライブラリであり、プロジェクトで使用するには有効なライセンスが必要な場合があります。訪問できます。[Aspose.Words for .NET API リファレンス](https://reference.aspose.com/words/net/)ライセンス オプションと価格について詳しくは、こちらをご覧ください。

#### Q: Word 文書の特定のセクションにある表から行を削除できますか?

A: はい、Word 文書の特定のセクションにある表から行を削除できます。提供されたコード スニペットを変更して、そのセクション内の適切な範囲またはブックマークを使用して、特定のセクションをターゲットにすることができます。