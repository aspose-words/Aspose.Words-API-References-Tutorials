---
title: Word 文書内のブックマークされたコンテンツを表示する非表示にする
linktitle: Word 文書内のブックマークされたコンテンツを表示する非表示にする
second_title: Aspose.Words ドキュメント処理 API
description: この包括的なステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word 文書内のブックマークされたコンテンツを動的に表示または非表示にする方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## 導入

ちょっと、そこ！特定の条件に基づいて、Word 文書内の特定のコンテンツの表示/非表示を制御したいと考えたことはありますか? Aspose.Words for .NET を使用すると、わずか数行のコードでブックマークされたコンテンツを動的に表示または非表示にすることができます。このチュートリアルでは、コードの各部分を理解できるように、プロセスを段階的に説明します。最終的には、Word 文書内のブックマークを操作するプロになれるでしょう。始めましょう！

## 前提条件

チュートリアルに入る前に、必要なものがすべて揃っていることを確認してください。

1. C# の基本知識: C# の構文と概念に精通している必要があります。
2.  Aspose.Words for .NET: ダウンロードしてください[ここ](https://releases.aspose.com/words/net/) 。購入する準備ができていない場合は、以下から始めることができます。[無料トライアル](https://releases.aspose.com/).
3. Visual Studio: 最新バージョンであればどれでも動作しますが、最新バージョンを使用することをお勧めします。
4. .NET Framework: マシンにインストールされていることを確認してください。

始める準備はできていますか?素晴らしい！必要な名前空間をインポートすることから始めましょう。

## 名前空間のインポート

Aspose.Words for .NET を使用するには、必要な名前空間をインポートする必要があります。このステップにより、使用するすべてのクラスとメソッドに確実にアクセスできるようになります。

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

これらの名前空間は、Word 文書を操作し、そのコンテンツを操作するために重要です。

## ステップ 1: ドキュメントの設定

まず、新しい Word ドキュメントとドキュメント ビルダーを作成しましょう。ドキュメント ビルダーを使用すると、ドキュメント内のコンテンツを簡単に追加および操作できます。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

このステップでは、新しいドキュメントとドキュメント ビルダーを初期化します。これにより、さらなる操作のための環境がセットアップされます。

## ステップ 2: ブックマークしたコンテンツを追加する

次に、ドキュメントにコンテンツを追加し、その周りにブックマークを作成します。このブックマークは、コンテンツの識別と操作に役立ちます。

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

ここでは、ブックマークされたコンテンツの前後にテキストを追加します。の`StartBookmark`そして`EndBookmark`メソッドはブックマークの境界を定義します。

## ステップ 3: 条件付きフィールドの挿入

ブックマークされたコンテンツの表示を制御するには、条件付きフィールドを使用します。このフィールドは条件をチェックし、それに応じてコンテンツを表示または非表示にします。

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

このステップでは、ブックマークの値をチェックする IF フィールドを挿入します。値が「true」の場合は「Visible」と表示されます。それ以外の場合は、「非表示」と表示されます。

## ステップ 4: ノードの再配置

次に、条件付きロジックがブックマークされたコンテンツに正しく適用されるようにノードを再配置する必要があります。

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

## ステップ 5: 差し込み印刷を実行する

最後に、差し込み印刷を実行してブックマークの値を設定し、コンテンツを表示するか非表示にするかを決定します。

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

このステップでは、ブックマークの値を「true」に設定します。これにより、条件に基づいてコンテンツが表示されるようになります。

## ステップ 6: ドキュメントを保存する

すべての操作が完了したら、最後のステップは、変更したドキュメントを保存することです。

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

ここでは、変更を示すわかりやすいファイル名を付けてドキュメントを保存します。

## 結論

以上です！ Aspose.Words for .NET を使用して Word 文書内のブックマークされたコンテンツを表示または非表示にする方法を学習しました。このチュートリアルでは、文書の作成、ブックマークの追加、条件フィールドの挿入、ノードの再配置、差し込み印刷の実行について説明しました。 Aspose.Words には豊富な機能が用意されているので、ぜひ試してみてください。[APIドキュメント](https://reference.aspose.com/words/net/)より高度な機能を実現します。

## よくある質問

### 1. Aspose.Words for .NET とは何ですか?

Aspose.Words for .NET は、開発者が Word ドキュメントをプログラムで作成、変更、変換できるようにする強力なライブラリです。ドキュメント自動化タスクに広く使用されています。

### 2. Aspose.Words for .NET は無料で使用できますか?

 Aspose.Words for .NET を試すことができます。[無料トライアル](https://releases.aspose.com/)。長期間使用するには、ライセンスを購入する必要があります。

### 3. ブックマークの他のプロパティを変更するにはどうすればよいですか?

 Aspose.Words を使用すると、ブックマークのテキストや場所など、ブックマークのさまざまなプロパティを操作できます。を参照してください。[APIドキュメント](https://reference.aspose.com/words/net/)詳細な手順については、

### 4. Aspose.Words for .NET のサポートを受けるにはどうすればよいですか?

にアクセスしてサポートを受けることができます。[Aspose サポート フォーラム](https://forum.aspose.com/c/words/8).

### 5. Aspose.Words for .NET を使用して他の種類のコンテンツを操作できますか?

はい、Aspose.Words for .NET は、テキスト、画像、表などを含むさまざまな種類のコンテンツ操作をサポートしています。