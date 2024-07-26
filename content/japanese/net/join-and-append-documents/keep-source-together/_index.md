---
title: ソースをまとめる
linktitle: ソースをまとめる
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、書式設定を保持しながら Word 文書を結合する方法を学びます。この包括的なガイドでは、セットアップから実行まですべてをカバーしています。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/keep-source-together/
---
## 導入

今日のデジタル時代では、Word 文書をプログラムで操作することが、さまざまな業界で不可欠です。Aspose.Words for .NET を使用すると、開発者は文書処理タスクを効率的に自動化できます。この包括的なガイドでは、Aspose.Words for .NET を使用してソースの書式設定を保持しながら文書を結合するプロセスを順を追って説明します。

## 前提条件

Aspose.Words for .NET を使用してドキュメントの結合を開始する前に、次のものを用意してください。

- Visual Studio: .NET 開発用の統合開発環境 (IDE)。
- Aspose.Words for .NET: 開発環境にインストールしてセットアップします。
- C# の知識: C# プログラミング言語の基本的な理解。

## 名前空間のインポート

まず、必要な名前空間をインポートします。

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## ステップ1: ドキュメントを読み込む

まず、ソースドキュメントと宛先ドキュメントをAspose.Wordsに読み込みます。`Document`オブジェクト。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR_DOCUMENT_DIRECTORY/";

//ソースドキュメントと宛先ドキュメントを読み込む
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## ステップ2: セクションの開始を設定する

セクションの開始を構成して、ソース ドキュメントのコンテンツが宛先ドキュメントの後に連続して流れるようにします。

```csharp
//ソース文書を宛先文書のコンテンツの直後に表示されるように設定する
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## ステップ3: 段落をまとめる

書式の整合性を維持するには、ソース ドキュメント内の各段落が次の段落と一致するようにマークします。

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## ステップ4: ドキュメントを追加する

ドキュメントを結合するには、`AppendDocument`メソッドは、ソース ドキュメントの書式設定を保持することを保証します。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ5: 結合した文書を保存する

最後に、結合したドキュメントを目的の場所に保存します。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

## 結論

結論として、Aspose.Words for .NET は、元の書式設定をシームレスに維持しながら Word 文書を結合するタスクを簡素化します。この機能は、自動化された文書処理を必要とするアプリケーションにとって非常に重要です。

## よくある質問

### Aspose.Words for .NET は異なる形式のドキュメントを結合できますか?
はい、ソースの書式を維持しながら、形式に関係なくドキュメントを結合できます。

### Aspose.Words for .NET は、大規模なドキュメントの効率的な結合をサポートしていますか?
はい、大きなドキュメントを最適なパフォーマンスで処理します。

### Aspose.Words for .NET の試用版はありますか?
はい、無料トライアルをダウンロードできます[ここ](https://releases.aspose.com/).

### Aspose.Words for .NET のテクニカル サポートを受けるにはどうすればよいですか?
テクニカルサポートは、[Aspose.Words フォーラム](https://forum.aspose.com/c/words/8).

### Aspose.Words for .NET の一時ライセンスを購入できますか?
はい、一時ライセンスを取得できます[ここ](https://purchase.aspose.com/temporary-license/).