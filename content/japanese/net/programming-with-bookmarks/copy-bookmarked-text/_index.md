---
title: Word文書内のブックマークされたテキストをコピーする
linktitle: Word文書内のブックマークされたテキストをコピーする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内のブックマーク テキストを別の文書にコピーする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/copy-bookmarked-text/
---

この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Copy Bookmarked Text 関数の使用方法を理解します。この機能を使用すると、特定のブックマークの内容をソース ドキュメントから別のドキュメントにコピーできます。

## 前提条件

- C# 言語に関する基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ1: ソースドキュメントの読み込み

ブックマークテキストをコピーする前に、ソース文書を`Document`ファイルパスを使用するオブジェクト:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## ステップ2: ソースブックマークを取得する

私たちは`Bookmarks`コピーする特定のブックマークを取得するには、ソース ドキュメント範囲のプロパティを使用します。

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## ステップ3: 宛先ドキュメントの作成

ブックマークの内容をコピーするための宛先ドキュメントとして機能する新しいドキュメントを作成します。

```csharp
Document dstDoc = new Document();
```

## ステップ4: コピー場所の指定

コピーしたテキストを追加する場所を指定します。この例では、コピー先ドキュメントの最後のセクションの本文の末尾にテキストを追加します。

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## ステップ5: ブックマークテキストをインポートしてコピーする

私たちは`NodeImporter`ソース ドキュメントから宛先ドキュメントにブックマーク テキストをインポートしてコピーするオブジェクト:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Aspose.Words for .NET を使用してブックマークされたテキストをコピーするためのサンプル ソース コード

以下は、Aspose.Words for .NET を使用してブックマークからテキストをコピーする方法を示す完全なサンプル ソース コードです。

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	//これは、内容をコピーするブックマークです。
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	//このドキュメントに追加していきます。
	Document dstDoc = new Document();

	//最後のセクションの本文の末尾に追加されるとします。
	CompositeNode dstNode = dstDoc.LastSection.Body;

	//単一のコンテキストなしで複数回インポートすると、多くのスタイルが作成されます。
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### AppendBookmarkedText ソースコード

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
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
        }

```
## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の「ブックマークされたテキストをコピー」関数の使用方法を理解しました。ステップ バイ ステップ ガイドに従って、ソース ドキュメントから別のドキュメントにブックマークの内容をコピーしました。

### Word 文書内のブックマークされたテキストをコピーするための FAQ

#### Q: Aspose.Words for .NET の「ブックマーク付きのテキストのコピー」機能を使用するための要件は何ですか?

A: Aspose.Words for .NET の「ブックマーク付きのテキストのコピー」機能を使用するには、C# 言語の基本的な知識が必要です。また、Aspose.Words ライブラリがインストールされた .NET 開発環境も必要です。

#### Q: ソース ドキュメントを Aspose.Words for .NET に読み込むにはどうすればよいですか?

 A: Aspose.Words for .NETでソースドキュメントを読み込むには、`Document`ドキュメントのファイル パスを指定してクラスを作成します。サンプル コードは次のとおりです。

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### Q: Aspose.Words for .NET を使用してソース ドキュメント内の特定のブックマークの内容を取得するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用してソースドキュメント内の特定のブックマークの内容を取得するには、`Bookmarks`ソース ドキュメント範囲の プロパティを使用し、ブックマーク名を使用して特定のブックマークを取得します。サンプル コードは次のとおりです。

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### Q: Aspose.Words for .NET を使用して、宛先ドキュメント内のブックマーク テキスト コピーの場所を指定する方法を教えてください。

 A: Aspose.Words for .NETを使用してコピーしたブックマークテキストを宛先ドキュメントのどこに追加するかを指定するには、宛先ドキュメントの最後のセクションの本文に移動します。`LastSection`最後のセクションにアクセスするためのプロパティと`Body`プロパティを使用して、そのセクションの本文にアクセスします。サンプル コードは次のとおりです。

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### Q: Aspose.Words for .NET を使用して、ソース ドキュメントから宛先ドキュメントにブックマーク テキストをインポートしてコピーするにはどうすればよいですか?

 A: Aspose.Words for .NETを使用して、ソースドキュメントから宛先ドキュメントにブックマークテキストをインポートしてコピーするには、`NodeImporter`クラスは、ソース文書、宛先文書、および保持する書式モードを指定します。その後、`AppendBookmarkedText`メソッドを使用して、宛先ドキュメントにブックマーク テキストを追加します。サンプル コードは次のとおりです。

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### Q: Aspose.Words for .NET を使用してブックマーク テキストをコピーした後、コピー先のドキュメントを保存するにはどうすればよいですか?

A: Aspose.Words for .NETを使用してブックマークからテキストをコピーした後、コピー先のドキュメントを保存するには、`Save`方法の`Document`宛先ファイル パスを指定するオブジェクト。サンプル コードは次のとおりです。

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```