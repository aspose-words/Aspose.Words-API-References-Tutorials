---
title: 差し込み印刷時に文書を挿入
linktitle: 差し込み印刷時に文書を挿入
second_title: Aspose.Words ドキュメント処理 API
description: この包括的なステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して差し込み印刷フィールドにドキュメントを挿入する方法を学びます。
type: docs
weight: 10
url: /ja/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## 導入

Aspose.Words for .NET によるドキュメント自動化の世界へようこそ!差し込み印刷操作中に、メイン文書内の特定のフィールドに文書を動的に挿入する方法を考えたことはありますか?そうですね、あなたは正しい場所にいます。このチュートリアルでは、Aspose.Words for .NET を使用して差し込み印刷フィールドにドキュメントを挿入するプロセスを段階的に説明します。それはパズルをつなぎ合わせるようなもので、各ピースが完璧に所定の位置に収まります。それでは、飛び込んでみましょう！

## 前提条件

始める前に、以下のものがあることを確認してください。

1.  Aspose.Words for .NET: できること[最新バージョンをここからダウンロードしてください](https://releases.aspose.com/words/net/)。ライセンスを購入する必要がある場合は、購入できます[ここ](https://purchase.aspose.com/buy)。あるいは、[仮免許](https://purchase.aspose.com/temporary-license/)または、[無料トライアル](https://releases.aspose.com/).
2. 開発環境: Visual Studio またはその他の C# IDE。
3. C# の基本知識: C# プログラミングに精通していると、このチュートリアルを簡単に進めることができます。

## 名前空間のインポート

まず最初に、必要な名前空間をインポートする必要があります。これらはプロジェクトの構成要素のようなものです。

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

プロセスを管理可能なステップに分割してみましょう。各ステップは前のステップに基づいて構築され、完全な解決策に導きます。

## ステップ 1: ディレクトリを設定する

ドキュメントの挿入を開始する前に、ドキュメント ディレクトリへのパスを定義する必要があります。ここに書類が保管されます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: メインドキュメントのロード

次に、メインドキュメントをロードします。この文書には、他の文書が挿入される差し込みフィールドが含まれています。

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## ステップ 3: フィールドマージコールバックの設定

マージ プロセスを処理するには、コールバック関数を設定する必要があります。この関数は、指定された差し込みフィールドにドキュメントを挿入する役割を果たします。

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## ステップ 4: 差し込み印刷の実行

次に、差し込み印刷を実行します。ここで魔法が起こります。差し込みフィールドと、このフィールドに挿入するドキュメントを指定します。

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## ステップ 5: ドキュメントを保存する

差し込み印刷が完了したら、変更した文書を保存します。この新しいドキュメントには、必要な場所にコンテンツが挿入されます。

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## ステップ 6: コールバック ハンドラーの作成

コールバック ハンドラーは、差し込みフィールドに対する特別な処理を行うクラスです。フィールド値で指定されたドキュメントをロードし、現在の差し込みフィールドに挿入します。

```csharp
private class InsertDocumentAtMailMergeHandler : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "Document_1")
        {
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);

            Document subDoc = new Document((string)args.FieldValue);
            InsertDocument(builder.CurrentParagraph, subDoc);

            if (!builder.CurrentParagraph.HasChildNodes)
                builder.CurrentParagraph.Remove();

            args.Text = null;
        }
    }
}
```

## ステップ 7: ドキュメントを挿入する

このメソッドは、指定されたドキュメントを現在の段落または表のセルに挿入します。

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;
        NodeImporter importer = new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

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

## 結論

そして、それができました！ Aspose.Words for .NET を使用して、差し込み印刷操作中に特定のフィールドにドキュメントを正常に挿入しました。この強力な機能により、特に大量のドキュメントを扱う場合に、時間と労力を大幅に節約できます。それは、面倒な作業をすべて引き受けてくれるパーソナルアシスタントを持つようなものだと考えてください。さあ、試してみてください。コーディングを楽しんでください!

## よくある質問

### 複数の文書を異なる差し込みフィールドに挿入できますか?
はい、できます。適切な差し込みフィールドと対応するドキュメント パスを`MailMerge.Execute`方法。

### 挿入した文書をメイン文書とは異なるフォーマットにすることはできますか?
絶対に！使用できます`ImportFormatMode`のパラメータ`NodeImporter`書式設定を制御します。

### 差し込みフィールド名が動的である場合はどうなるでしょうか?
動的差し込みフィールド名をパラメータとしてコールバック ハンドラに渡すことで、動的差し込みフィールド名を処理できます。

### この方法をさまざまなファイル形式で使用できますか?
はい、Aspose.Words は、DOCX、PDF などを含むさまざまなファイル形式をサポートしています。

### 文書挿入プロセス中のエラーはどのように処理すればよいですか?
コールバック ハンドラーにエラー処理を実装して、発生する可能性のある例外を管理します。