---
title: Word 文書内のブックマークされたテキストをコピーする
linktitle: Word 文書内のブックマークされたテキストをコピーする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word ドキュメント内のブックマーク テキストを別のドキュメントにコピーする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/copy-bookmarked-text/
---

この記事では、Aspose.Words for .NET ライブラリの Copy Bookmarked Text 関数の使用方法を理解するために、上記の C# ソース コードを調べます。この機能を使用すると、特定のブックマークの内容をソース ドキュメントから別のドキュメントにコピーできます。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: ソースドキュメントのロード

ブックマークテキストをコピーする前に、ソースドキュメントを`Document`ファイルパスを使用したオブジェクト:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## ステップ 2: ソース ブックマークを取得する

私たちが使用するのは、`Bookmarks`ソースドキュメント範囲のプロパティを使用して、コピーしたい特定のブックマークを取得します。

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## ステップ 3: 宛先ドキュメントの作成

ブックマークの内容をコピーする宛先ドキュメントとして機能する新しいドキュメントを作成します。

```csharp
Document dstDoc = new Document();
```

## ステップ 4: コピー場所の指定

コピーしたテキストを追加する場所を指定します。この例では、宛先ドキュメントの最後のセクションの本文の末尾にテキストを追加します。

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## ステップ 5: ブックマーク テキストをインポートしてコピーする

私たちは、`NodeImporter`ソースドキュメントから宛先ドキュメントにブックマークテキストをインポートしてコピーするオブジェクト:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Aspose.Words for .NET を使用してブックマークされたテキストをコピーするためのソース コードの例

Aspose.Words for .NET を使用してブックマークからテキストをコピーする方法を示す完全なソース コード例を次に示します。

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	//これは、コンテンツをコピーするブックマークです。
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	//この文書に追加していきます。
	Document dstDoc = new Document();

	//最後のセクションの本文の最後に追加するとします。
	CompositeNode dstNode = dstDoc.LastSection.Body;

	//単一のコンテキストを使用せずに複数回インポートすると、多数のスタイルが作成されます。
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### AppendBookmarkedText ソース コード

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
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
        }

```
## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET からブックマークされたテキストをコピーする関数の使用方法を理解しました。ステップバイステップのガイドに従って、ブックマークの内容をソース文書から別の文書にコピーしました。

### Word 文書内のブックマークされたテキストをコピーする場合の FAQ

#### Q: Aspose.Words for .NET の「ブックマーク付きテキストのコピー」機能を使用するための要件は何ですか?

A: Aspose.Words for .NET の「ブックマーク付きテキストのコピー」機能を使用するには、C# 言語の基本的な知識が必要です。 Aspose.Words ライブラリがインストールされた .NET 開発環境も必要です。

#### Q: ソース ドキュメントを Aspose.Words for .NET にロードするにはどうすればよいですか?

 A: Aspose.Words for .NET でソース ドキュメントをロードするには、`Document`ドキュメントのファイルパスを指定してクラスを作成します。サンプルコードは次のとおりです。

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### Q: Aspose.Words for .NET を使用してソース ドキュメント内の特定のブックマークのコンテンツを取得するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用してソース ドキュメント内の特定のブックマークの内容を取得するには、`Bookmarks`ソース ドキュメント範囲のプロパティを使用し、ブックマーク名を使用して特定のブックマークを取得します。サンプルコードは次のとおりです。

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### Q: Aspose.Words for .NET を使用して、宛先ドキュメント内のブックマーク テキスト コピーの場所を指定するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用してコピー先ドキュメント内のコピーしたブックマーク テキストを追加する場所を指定するには、コピー先ドキュメントの最後のセクションの本文に移動します。使用できます`LastSection`最後のセクションにアクセスするためのプロパティと、`Body`プロパティを使用してそのセクションの本文にアクセスします。サンプルコードは次のとおりです。

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### Q: Aspose.Words for .NET を使用して、ブックマーク テキストをソース ドキュメントから宛先ドキュメントにインポートしてコピーするにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して、ソース ドキュメントからターゲット ドキュメントにブックマーク テキストをインポートしてコピーするには、`NodeImporter`ソースドキュメント、宛先ドキュメント、保持する書式設定モードを指定するクラス。その後、使用できます`AppendBookmarkedText`宛先ドキュメントにブックマーク テキストを追加するメソッド。サンプルコードは次のとおりです。

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### Q: Aspose.Words for .NET を使用してブックマーク テキストをコピーした後、宛先ドキュメントを保存するにはどうすればよいですか?

A: Aspose.Words for .NET を使用してブックマークからテキストをコピーした後に宛先ドキュメントを保存するには、`Save`の方法`Document`宛先ファイルのパスを指定するオブジェクト。サンプルコードは次のとおりです。

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```