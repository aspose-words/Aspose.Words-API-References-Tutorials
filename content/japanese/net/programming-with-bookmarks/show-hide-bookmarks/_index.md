---
title: Word 文書のブックマークを表示/非表示
linktitle: Word 文書のブックマークを表示/非表示
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の特定のブックマークを表示または非表示にする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/show-hide-bookmarks/
---

この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリのブックマークの表示/非表示機能の使用方法を理解します。この機能を使用すると、Word 文書内の特定のブックマークを表示または非表示にすることができます。

## 前提条件

- C# 言語に関する基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ1: ドキュメントの読み込み

私たちは`Document`ファイルから既存のドキュメントを読み込むクラス:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## ステップ2: 特定のブックマークを表示または非表示にする

私たちは`ShowHideBookmarkedContent`ドキュメント内の特定のブックマークを表示または非表示にする関数。この関数は、ドキュメント、ブックマークの名前、およびブックマークを表示するか非表示にするかを示すブール値をパラメータとして受け取ります。

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## ステップ3: 変更したドキュメントを保存する

私たちは`Save`変更されたドキュメントをファイルに保存する方法:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Aspose.Words for .NET を使用したブックマークの表示/非表示のサンプル ソース コード

以下は、Aspose.Words for .NET を使用して特定のブックマークを表示または非表示にする方法を示す完全なサンプル ソース コードです。

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### ShowHideBookmarkedContent ソースコード

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
            Bookmark bm = doc.Range.Bookmarks[bookmarkName];

            DocumentBuilder builder = new DocumentBuilder(doc);
            builder.MoveToDocumentEnd();

            //{IF "{MERGEFIELD ブックマーク}" = "true" "" ""}
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
        }
		
```
## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET のブックマークの表示/非表示機能の使用方法を理解しました。ドキュメント内の特定のブックマークを表示または非表示にするには、ステップ バイ ステップ ガイドに従いました。

### Word 文書のブックマークの表示/非表示に関する FAQ

#### Q: 同じドキュメント内で複数のブックマークを表示または非表示にできますか?

A: はい、処理するブックマークごとに手順 2 と 3 を繰り返すことで、同じドキュメント内の複数のブックマークを表示または非表示にすることができます。

#### Q: 提供されたコードは、.doc や .docm などの他の Word 文書形式でも機能しますか?

A: はい、提供されているコードは、.doc や .docm など、Aspose.Words でサポートされているさまざまな Word ドキュメント形式で動作します。ドキュメントを読み込みおよび保存するときには、正しいファイル名とパスを使用するようにしてください。

#### Q: 非表示のブックマークを再度表示するにはどうすればよいですか?

 A: 非表示のブックマークを再度表示するには、同じ`ShowHideBookmarkedContent`値を渡す関数`true`ブックマークを表示するか非表示にするかを示すブール型パラメータ。

#### Q: 条件を使用して、ドキュメント内のマージ フィールドの値に基づいてブックマークを表示または非表示にできますか?

 A: はい、条件とマージフィールド値を使用して、ブックマークを表示するか非表示にするかを決定できます。`ShowHideBookmarkedContent`適切な条件と値を考慮する機能。

#### Q: Aspose.Words for .NET を使用して Word 文書内のブックマークを削除するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用してWord文書内のブックマークを削除するには、`RemoveBookmarks`方法の`Document`クラス。サンプルコードは次のとおりです。

```csharp
doc.RemoveBookmarks("BookmarkName");
```