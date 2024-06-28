---
title: Word文書に目次を挿入する
linktitle: Word文書に目次を挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word に目次を挿入する方法を学習します。シームレスなドキュメント ナビゲーションについては、ステップバイステップのガイドに従ってください。
type: docs
weight: 10
url: /ja/net/add-content-using-documentbuilder/insert-table-of-contents/
---
## 導入
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に目次 (TOC) を効率的に追加する方法を学習します。この機能は、長い文書を整理してナビゲートし、読みやすさを向上させ、文書セクションの概要を素早く提供するために不可欠です。

## 前提条件

始める前に、次のものが揃っていることを確認してください。

- C# と .NET Framework の基本的な理解。
- Visual Studio がマシンにインストールされていること。
-  Aspose.Words for .NET ライブラリ。まだインストールしていない場合は、からダウンロードできます[ここ](https://releases.aspose.com/words/net/).

## 名前空間のインポート

まず、必要な名前空間を C# プロジェクトにインポートします。

```csharp
using Aspose.Words;
using Aspose.Words.Builder;
using Aspose.Words.Fields;
using Aspose.Words.Tables;
```

プロセスを明確なステップに分けてみましょう。

## ステップ 1: Aspose.Words ドキュメントと DocumentBuilder を初期化する

まず、新しい Aspose.Words を初期化します。`Document`オブジェクトと`DocumentBuilder`使用するもの:

```csharp
//ドキュメントとDocumentBuilderの初期化
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: 目次を挿入する

ここで、目次を挿入します。`InsertTableOfContents`方法：

```csharp
//目次を挿入
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## ステップ 3: 新しいページでドキュメントのコンテンツを開始する

適切な書式設定を確保するには、実際のドキュメントのコンテンツを新しいページで開始します。

```csharp
//改ページを挿入する
builder.InsertBreak(BreakType.PageBreak);
```

## ステップ 4: 見出しを使用して文書を構成する

適切な見出しスタイルを使用してドキュメントのコンテンツを整理します。

```csharp
//見出しスタイルを設定する
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## ステップ 5: 目次を更新して追加する

ドキュメントの構造を反映するように目次を更新します。

```csharp
//目次フィールドを更新する
doc.UpdateFields();
```

## ステップ 6: ドキュメントを保存する

最後に、ドキュメントを指定したディレクトリに保存します。

```csharp
//文書を保存する
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
doc.Save(dataDir + "InsertTableOfContentsUsingAsposeWords.docx");
```

## 結論

Aspose.Words for .NET を使用して目次を追加するのは簡単で、ドキュメントの使いやすさが大幅に向上します。これらの手順に従うことで、複雑なドキュメントを効率的に整理し、ナビゲートすることができます。

## よくある質問

### 目次の外観をカスタマイズできますか?
はい、Aspose.Words for .NET API を使用して、目次の外観と動作をカスタマイズできます。

### Aspose.Words はフィールドの自動更新をサポートしていますか?
はい、Aspose.Words を使用すると、ドキュメントの変更に基づいて目次などのフィールドを動的に更新できます。

### 1 つのドキュメントに複数の目次を生成できますか?
Aspose.Words は、1 つのドキュメント内で異なる設定を持つ複数の目次の生成をサポートしています。

### Aspose.Words は Microsoft Word のさまざまなバージョンと互換性がありますか?
はい、Aspose.Words は、さまざまなバージョンの Microsoft Word 形式との互換性を保証します。

### Aspose.Words に関するその他のヘルプとサポートはどこで入手できますか?
さらに詳しいサポートが必要な場合は、次のサイトを参照してください。[Aspose.Words フォーラム](https://forum.aspose.com/c/words/8)またはチェックしてください[公式ドキュメント](https://reference.aspose.com/words/net/).