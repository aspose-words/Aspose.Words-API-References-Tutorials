---
title: 置換時にドキュメントを挿入
linktitle: 置換時にドキュメントを挿入
second_title: Aspose.Words ドキュメント処理 API
description: 詳細なステップバイステップ ガイドで、Aspose.Words for .NET を使用して、ある Word ドキュメントを別の Word ドキュメントにシームレスに挿入する方法を学びましょう。ドキュメント処理を合理化したい開発者に最適です。
type: docs
weight: 10
url: /ja/net/clone-and-combine-documents/insert-document-at-replace/
---
## 導入

こんにちは、ドキュメントマエストロの皆さん！ある Word 文書を別の Word 文書にシームレスに挿入する方法を見つけようとして、コードに夢中になったことはありませんか?心配しないでください。今日は、そのタスクを簡単にするために、Aspose.Words for .NET の世界に飛び込みます。この強力なライブラリを使用して、検索と置換操作中に特定のポイントにドキュメントを挿入する方法について、詳細なステップバイステップのガイドを見ていきます。 Aspose.Words ウィザードになる準備はできましたか?始めましょう！

## 前提条件

コードに入る前に、いくつかの準備をしておく必要があります。

-  Visual Studio: マシンに Visual Studio がインストールされていることを確認してください。まだお持ちでない場合は、からダウンロードできます[ここ](https://visualstudio.microsoft.com/).
- Aspose.Words for .NET: Aspose.Words ライブラリが必要です。から入手できます。[Aspose ウェブサイト](https://releases.aspose.com/words/net/).
- C# の基本知識: C# と .NET の基本を理解していると、このチュートリアルを進めるのに役立ちます。

さて、これらは邪魔にならないので、実際にコードを作成してみましょう。

## 名前空間のインポート

まず最初に、Aspose.Words を操作するために必要な名前空間をインポートする必要があります。これは、プロジェクトを開始する前にすべてのツールを集めるようなものです。これらの using ディレクティブを C# ファイルの先頭に追加します。

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

前提条件が整ったので、プロセスをいくつかのステップに分割してみましょう。各ステップは非常に重要であり、私たちを目標に近づけてくれます。

## ステップ 1: ドキュメント ディレクトリのセットアップ

まず、ドキュメントが保存されているディレクトリを指定する必要があります。これは、大事なパフォーマンスの前に舞台を整えるようなものです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ディレクトリへのパスを含めます。ここは、ドキュメントが生き生きと息づく場所です。

## ステップ 2: メインドキュメントをロードする

次に、別のドキュメントを挿入するメインドキュメントをロードします。ここがすべてのアクションが行われるメインステージであると考えてください。

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

このコードは、指定されたディレクトリからメインドキュメントを読み込みます。

## ステップ 3: 検索と置換のオプションを設定する

文書を挿入する特定の場所を見つけるには、検索と置換機能を使用します。これは、地図を使用して新しく追加する場所の正確な場所を見つけるのと似ています。

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

ここでは、方向を逆方向に設定し、次に定義するカスタム コールバック ハンドラーを指定しています。

## ステップ 4: 置換操作を実行する

次に、カスタム コールバックを使用して別のドキュメントを挿入しながら、メイン ドキュメントに特定のプレースホルダー テキストを検索して何も置き換えないように指示します。

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

このコードは、検索と置換操作を実行し、更新されたドキュメントを保存します。

## ステップ 5: カスタムの置換コールバック ハンドラーを作成する

カスタム コールバック ハンドラーで魔法が起こります。このハンドラーは、検索と置換操作中にドキュメントの挿入がどのように実行されるかを定義します。

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        //一致するテキストを含む段落の後に文書を挿入します。
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        //一致するテキストを含む段落を削除します。
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

ここでは、挿入するドキュメントをロードし、ヘルパー メソッドを呼び出して挿入を実行します。

## ステップ 6: ドキュメントの挿入メソッドを定義する

パズルの最後のピースは、指定された場所にドキュメントを実際に挿入するメソッドです。

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		//セクション本体内のすべてのブロックレベルのノードをループします。
		//次に、セクションの最後の空の段落ではないすべてのノードを複製して挿入します。
		foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
		foreach (Node srcNode in srcSection.Body)
		{
			if (srcNode.NodeType == NodeType.Paragraph)
			{
				Paragraph para = (Paragraph)srcNode;
				if (para.IsEndOfSection && !para.HasChildNodes)
					continue;
			}

			Node newNode = importer.ImportNode(srcNode, true);

			destinationParent.InsertAfter(newNode, insertionDestination);
			insertionDestination = newNode;
		}
	}
	else
	{
		throw new ArgumentException("The destination node should be either a paragraph or table.");
	}
}
```

このメソッドは、挿入するドキュメントからノードをインポートし、メインドキュメント内の適切な場所にノードを配置します。

## 結論

そして、それができました！ Aspose.Words for .NET を使用して、あるドキュメントを別のドキュメントに挿入するための包括的なガイド。これらの手順に従うことで、ドキュメントの組み立てと操作のタスクを簡単に自動化できます。ドキュメント管理システムを構築している場合でも、単にドキュメント処理ワークフローを合理化する必要がある場合でも、Aspose.Words は信頼できる相棒です。

## よくある質問

### Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、Word ドキュメントをプログラムで操作するための強力なライブラリです。 Word 文書を簡単に作成、変更、変換、処理できます。

### 複数の文書を一度に挿入できますか?
はい、コールバック ハンドラーを変更して、ドキュメントのコレクションを反復処理することで複数の挿入を処理できます。

### 無料トライアルはありますか?
絶対に！無料試用版はからダウンロードできます[ここ](https://releases.aspose.com/).

### Aspose.Words のサポートを受けるにはどうすればよいですか?
にアクセスしてサポートを受けることができます。[Aspose.Words フォーラム](https://forum.aspose.com/c/words/8).

### 挿入した文書の書式を維持できますか?
はい`NodeImporter`クラスを使用すると、あるドキュメントから別のドキュメントにノードをインポートするときに書式設定がどのように処理されるかを指定できます。