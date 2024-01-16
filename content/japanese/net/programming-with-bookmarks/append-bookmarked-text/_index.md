---
title: Word 文書にブックマークされたテキストを追加する
linktitle: Word 文書にブックマークされたテキストを追加する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書のブックマークからテキストを追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/append-bookmarked-text/
---

この記事では、Aspose.Words for .NET ライブラリの Append Bookmarked Text 関数の使用方法を理解するために、上記の C# ソース コードを調べます。この機能を使用すると、Word 文書の特定のブックマークに含まれるテキストを別の文書に追加できます。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: ブックマークから段落を取得する

ブックマーク テキストの追加を開始する前に、ブックマークの開始と終了を含む段落を取得する必要があります。これは、にアクセスすることで実行できます。`BookmarkStart`そして`BookmarkEnd`ブックマークのプロパティ:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## ステップ 2: 親段落を確認する

開始段落と終了段落に有効な親があるかどうか、つまり、それらが実際に段落に属しているかどうかを確認します。そうでない場合は、例外が生成されます。

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## ステップ 3: 段落の親を確認する

開始段落と終了段落に同じ親があるかどうかを確認します。そうでない場合は、その段落が同じセクションまたはドキュメントに含まれていないことを意味し、例外をスローします。

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## ステップ 4: 段落をコピーする

開始段落から終了段落までノード (段落) を反復処理します。ノードごとにコピーを作成し、それを宛先ドキュメントのコンテキストにインポートします。

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Aspose.Words for .NET を使用したブックマークされたテキストの追加のソース コード例

Aspose.Words for .NET を使用してブックマークからテキストを追加する方法を示す完全なソース コード例を次に示します。

```csharp

	//これはブックマークの先頭を含む段落です。
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	//これはブックマークの終わりを含む段落です。
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	//かなり単純なシナリオに限定してください。
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	//開始段落から終了段落まで (および終了段落を含む) のすべての段落をコピーしたいのですが、
	//したがって、停止するノードは終了段落の 1 つ後です。
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//これにより、現在のノードのコピーが作成され、コンテキストにインポート (有効化) されます。
		//宛先ドキュメントの。インポートとは、スタイルとリスト識別子を正しく調整することを意味します。
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET のブックマークされたテキストの追加機能の使用方法を理解しました。ステップバイステップのガイドに従って、ブックマークから段落を取得し、親を確認し、段落を別のドキュメントにコピーしました。

### Word 文書にブックマークされたテキストを追加する場合の FAQ

#### Q1: Aspose.Words for .NET の「ブックマーク付きテキストの追加」機能を使用するための前提条件は何ですか?

A: Aspose.Words for .NET の「ブックマーク付きテキストの追加」機能を使用するには、C# 言語の基本的な知識が必要です。 Aspose.Words ライブラリがインストールされた .NET 開発環境も必要です。

#### Q2: Word 文書内のブックマークの先頭と末尾を含む段落を取得するにはどうすればよいですか?

A: Word 文書内のブックマークの開始と終了を含む段落を取得するには、`BookmarkStart`そして`BookmarkEnd`ブックマークのプロパティ。サンプルコードは次のとおりです。

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Q3: 開始段落と終了段落に有効な親がない場合はどうなりますか?

A: 開始段落と終了段落に有効な親がない場合、つまり実際には段落ではない場合、例外がスローされます。現時点ではこの状況を管理することはできません。
