---
title: Word 文書内のブックマークされたコンテンツの表示/非表示
linktitle: Word 文書内のブックマークされたコンテンツの表示/非表示
second_title: Aspose.Words ドキュメント処理 API
description: この包括的なステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word 文書内のブックマークされたコンテンツを動的に表示または非表示にする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## 導入

こんにちは! 特定の条件に基づいて Word 文書内の特定のコンテンツの表示を制御したいと思ったことはありませんか? Aspose.Words for .NET を使用すると、数行のコードでブックマークされたコンテンツを動的に表示または非表示にすることができます。このチュートリアルでは、コードの各部分を理解できるように、プロセスをステップごとに説明します。最後には、Word 文書内のブックマークの操作のプロになれるでしょう。さあ、始めましょう!

## 前提条件

チュートリアルに進む前に、必要なものがすべて揃っていることを確認しましょう。

1. C# の基礎知識: C# の構文と概念に精通している必要があります。
2.  Aspose.Words for .NET: ダウンロード[ここ](https://releases.aspose.com/words/net/)購入の準備ができていない場合は、[無料トライアル](https://releases.aspose.com/).
3. Visual Studio: 最新バージョンであればどれでも動作しますが、最新バージョンの使用をお勧めします。
4. .NET Framework: マシンにインストールされていることを確認します。

始める準備はできましたか? 素晴らしい! まず、必要な名前空間をインポートすることから始めましょう。

## 名前空間のインポート

Aspose.Words for .NET を使用するには、必要な名前空間をインポートする必要があります。この手順により、使用するすべてのクラスとメソッドにアクセスできるようになります。

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

これらの名前空間は、Word 文書を操作し、そのコンテンツを操作するために不可欠です。

## ステップ1: ドキュメントの設定

まず、新しい Word 文書とドキュメント ビルダーを作成しましょう。ドキュメント ビルダーを使用すると、文書内のコンテンツを簡単に追加および操作できます。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

このステップでは、新しいドキュメントとドキュメント ビルダーを初期化します。これにより、以降の操作のための環境が設定されます。

## ステップ2: ブックマークしたコンテンツを追加する

次に、ドキュメントにコンテンツを追加し、その周りにブックマークを作成します。このブックマークは、コンテンツを識別して操作するのに役立ちます。

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

ここでは、ブックマークされたコンテンツの前後にテキストを追加します。`StartBookmark`そして`EndBookmark`メソッドはブックマークの境界を定義します。

## ステップ3: 条件付きフィールドの挿入

ブックマークされたコンテンツの表示を制御するには、条件付きフィールドを使用します。このフィールドは条件をチェックし、それに応じてコンテンツを表示または非表示にします。

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

この手順では、ブックマークの値をチェックする IF フィールドを挿入します。値が「true」の場合は「表示」と表示され、それ以外の場合は「非表示」と表示されます。

## ステップ4: ノードの並べ替え

次に、条件付きロジックがブックマークされたコンテンツに正しく適用されるように、ノードを再配置する必要があります。

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
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
```

ここでは、ノードを移動して、条件がブックマークされたコンテンツを適切に包含していることを確認します。

## ステップ5: 差し込み印刷を実行する

最後に、差し込み印刷を実行してブックマークの値を設定し、コンテンツを表示するか非表示にするかを決定します。

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

このステップでは、ブックマークの値を「true」に設定し、条件に基づいてコンテンツが表示されるようにします。

## ステップ6: ドキュメントを保存する

すべての操作が完了したら、最後のステップとして変更したドキュメントを保存します。

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

ここでは、変更内容を示すわかりやすいファイル名を付けてドキュメントを保存します。

## 結論

これで完了です。Aspose.Words for .NET を使用して Word 文書内のブックマークされたコンテンツを表示または非表示にする方法を学習しました。このチュートリアルでは、文書の作成、ブックマークの追加、条件付きフィールドの挿入、ノードの並べ替え、差し込み印刷の実行について説明しました。Aspose.Words には豊富な機能が用意されているので、ぜひ試してみてください。[APIドキュメント](https://reference.aspose.com/words/net/)より高度な機能を実現します。

## よくある質問

### 1. Aspose.Words for .NET とは何ですか?

Aspose.Words for .NET は、開発者がプログラムで Word ドキュメントを作成、変更、変換できるようにする強力なライブラリです。ドキュメント自動化タスクに広く使用されています。

### 2. Aspose.Words for .NET を無料で使用できますか?

 Aspose.Words for .NETを試すには、[無料トライアル](https://releases.aspose.com/)長期使用にはライセンスを購入する必要があります。

### 3. ブックマークのその他のプロパティを変更するにはどうすればよいですか?

 Aspose.Wordsでは、テキストや位置など、ブックマークのさまざまなプロパティを操作できます。[APIドキュメント](https://reference.aspose.com/words/net/)詳細な手順については、こちらをご覧ください。

### 4. Aspose.Words for .NET のサポートを受けるにはどうすればよいですか?

サポートを受けるには、[Aspose サポート フォーラム](https://forum.aspose.com/c/words/8).

### 5. Aspose.Words for .NET を使用して他の種類のコンテンツを操作できますか?

はい、Aspose.Words for .NET は、テキスト、画像、表など、さまざまな種類のコンテンツ操作をサポートしています。