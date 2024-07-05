---
title: Word 文書にブックマークされたテキストを追加する
linktitle: Word 文書にブックマークされたテキストを追加する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書のブックマークからテキストを追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/append-bookmarked-text/
---

この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Append Bookmarked Text 関数の使用方法を理解します。この機能を使用すると、Word 文書の特定のブックマークに含まれるテキストを別の文書に追加できます。

## 前提条件

- C# 言語に関する基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ1: ブックマークから段落を取得する

ブックマークテキストを追加する前に、ブックマークの開始と終了を含む段落を取得する必要があります。これは、`BookmarkStart`そして`BookmarkEnd`ブックマークのプロパティ:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## ステップ2: 親段落を確認する

開始段落と終了段落に有効な親があるかどうか、つまり実際に段落に属しているかどうかを確認します。そうでない場合は、例外を生成します。

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## ステップ3: 段落の親を確認する

開始段落と終了段落の親が同じかどうかを確認します。そうでない場合は、段落が同じセクションまたはドキュメントに含まれていないことを意味し、例外をスローします。

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## ステップ4: 段落をコピーする

開始段落から終了段落までのノード (段落) を反復処理します。各ノードに対してコピーを作成し、それを宛先ドキュメントのコンテキストにインポートします。

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Aspose.Words for .NET を使用してブックマークされたテキストを追加するサンプル ソース コード

以下は、Aspose.Words for .NET を使用してブックマークからテキストを追加する方法を示す完全なサンプル ソース コードです。

```csharp

	//これはブックマークの始まりを含む段落です。
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	//これはブックマークの終わりを含む段落です。
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	//かなり単純なシナリオに限定します。
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	//開始段落から終了段落まで（終了段落も含む）すべての段落をコピーしたいのですが、
	//したがって、停止するノードは最後の段落の 1 つ後になります。
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//これは現在のノードのコピーを作成し、それをコンテキストにインポート（有効にする）します。
		//インポートとは、スタイルとリスト識別子を正しく調整することを意味します。
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET のブックマーク テキスト追加機能の使用方法を理解しました。ブックマークから段落を取得し、親を検証し、段落を別のドキュメントにコピーする手順をステップ バイ ステップで説明しました。

### ワード文書にブックマークされたテキストを追加する方法に関する FAQ

#### Q1: Aspose.Words for .NET の「ブックマーク付きテキストの追加」機能を使用するための前提条件は何ですか?

A: Aspose.Words for .NET の「ブックマーク付きテキストの追加」機能を使用するには、C# 言語の基本的な知識が必要です。また、Aspose.Words ライブラリがインストールされた .NET 開発環境も必要です。

#### Q2: Word 文書内のブックマークの始まりと終わりを含む段落を取得するにはどうすればよいですか?

A: Word文書内のブックマークの開始と終了を含む段落を取得するには、`BookmarkStart`そして`BookmarkEnd`ブックマークのプロパティ。サンプルコードは次のとおりです。

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Q3: 開始段落と終了段落に有効な親がない場合はどうなりますか?

A: 開始段落と終了段落に有効な親がない場合、つまり実際には段落ではない場合、例外がスローされます。現時点では、この状況を管理することはできません。
