---
title: Word 文書内のブックマークされたコンテンツを表示する非表示にする
linktitle: Word 文書内のブックマークされたコンテンツを表示する非表示にする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のブックマーク コンテンツを表示または非表示にする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

この記事では、Aspose.Words for .NET ライブラリのブックマークされたコンテンツの表示/非表示関数の使用方法を理解するために、上記の C# ソース コードを調べます。この機能を使用すると、データを結合するときに、特定の条件に基づいて Word 文書のブックマークの内容を表示または非表示にすることができます。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: ブックマークを取得する

私たちが使用するのは、`Bookmarks`ドキュメント範囲のプロパティを使用して、コンテンツを表示または非表示にする特定のブックマークを取得します。

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## ステップ 2: 差し込みフィールドの挿入

ドキュメントビルダーを使用します`DocumentBuilder`必要な差し込みフィールドを挿入します。これらの差し込みフィールドは、ブックマークの値に応じてブックマークの内容を表示または非表示にする条件を設定します。`showHide`変数：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## ステップ 3: ブックマークのコンテンツを移動する

ブックマークの内容をループして移動し、ブックマークが表示されるようにします。

ブックマークの前にあります。これは、指定された条件に基づいてコンテンツの表示または非表示を制御します。

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## ステップ 4: ブックマークの残りのコンテンツを移動する

ブックマークの終了ノードを挿入ポイントとして使用して、ブックマークの残りのコンテンツをブックマークの後に移動します。

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## ステップ 5: マージの実行

私たちが使用するのは、`Execute`書類の方法`s `差し込み印刷` object to execute the merge using the bookmark name and the value of the `showHide` 変数:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Aspose.Words for .NET を使用したブックマークされたコンテンツの表示、非表示のソース コードの例

Aspose.Words for .NET を使用してブックマーク コンテンツの表示または非表示を示すソース コードの完全な例を次に示します。

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD ブックマーク}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET のブックマークされたコンテンツの表示/非表示機能の使用方法を理解しました。データを結合するときに、特定の条件に基づいてブックマークの内容を表示または非表示にするためのステップバイステップのガイドに従いました。

### Word 文書でブックマークされたコンテンツを表示、非表示にするに関する FAQ

#### Q: 同じドキュメント内の複数のブックマークに同じ条件を使用できますか?

A: はい、同じドキュメント内の複数のブックマークに同じ条件を使用できます。ブックマークごとに手順 2 ～ 5 を繰り返し、ブックマーク名とオプションでブックマークの値を調整するだけです。`showhide`必要に応じて変数を指定します。

#### Q: ブックマークのコンテンツを表示または非表示にする条件を追加するにはどうすればよいですか?

 A: さらに条件を追加するには、次のような論理演算子を使用できます。`AND`そして`OR`手順 2 で差し込みフィールドを挿入するコードに追加の条件を追加します。次のコードの条件を編集して、追加の条件を追加します。

```csharp
builder. Write("\" = \"true\" ");
```

#### Q: Aspose.Words for .NET を使用して Word 文書内のブックマークを削除するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して Word 文書内のブックマークを削除するには、`Remove`からのメソッド`Bookmarks`ドキュメント範囲のコレクション。特定のブックマークを削除するサンプル コードは次のとおりです。

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### Q: Aspose.Words ライブラリは無料ですか?

 A: Aspose.Words ライブラリは商用ライブラリであり、プロジェクトで使用するには有効なライセンスが必要です。確認してもいい[Aspose.Words for .NET API リファレンス](https://reference.aspose.com/words/net/)ライセンスのオプションと価格について詳しくは、こちらをご覧ください。

#### Q: .NET の Word ドキュメントでのワード処理に利用できるライブラリは他にもありますか?

A: はい、Open XML SDK や GemBox.Document など、.NET の Word ドキュメントでのワード処理に使用できるライブラリは他にもあります。特定のニーズや好みに基づいて、Aspose.Words の代替としてこれらのライブラリを探索できます。