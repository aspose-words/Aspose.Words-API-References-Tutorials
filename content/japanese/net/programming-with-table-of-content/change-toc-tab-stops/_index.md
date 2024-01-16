---
title: Word 文書の Toc タブストップを変更する
linktitle: Word 文書の Toc タブストップを変更する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書の目次タブを変更する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words for .NET は、C# アプリケーションで Word ドキュメントを作成、編集、操作するための強力なライブラリです。 Aspose.Words が提供する機能の中には、Word 文書の目次で使用されるタブを変更する機能があります。このガイドでは、Aspose.Words for .NET の C# ソース コードを使用してドキュメントの目次のタブを変更する方法を説明します。

## Aspose.Words ライブラリについて

コードに入る前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。 Aspose.Words は、Word 文書のワープロ処理を簡単かつ効率的に行う人気のライブラリです。目次タブの変更など、Word 文書の作成、編集、操作のための幅広い機能を提供します。

## 目次を含むドキュメントのロード

最初のステップは、変更する目次を含む Word 文書をロードすることです。 Document クラスを使用して、ソース ファイルからドキュメントを読み込みます。以下に例を示します。

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

この例では、ドキュメント ディレクトリにあるドキュメント「目次.docx」を読み込みます。

## 目次のタブを変更する

ドキュメントがロードされたら、ドキュメントの各段落を調べて、目次 (TOC) の結果スタイルを使用してフォーマットされているかどうかを確認します。その場合は、ページ番号を揃えるために使用されるタブを変更します。その方法は次のとおりです。

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

この例では、ループを使用して文書内の各段落をループ処理しています。次に、段落が目次結果 (TOC) スタイルを使用して書式設定されているかどうかを確認します。その場合、この段落で使用されている最初のタブにアクセスし、古いタブを削除し、位置を変更して新しいタブを追加することでタブを変更します。

## 変更したドキュメントを保存する

目次のタブに必要な変更を加えたら、Document クラスの Save メソッドを使用して、変更したドキュメントを保存できます。以下に例を示します。

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

この例では、変更したドキュメントを「WorkingWithTableOfContent.ChangeTocTabStops.docx」として保存します。

### Aspose.Words for .NET の「目次タブの編集」機能のサンプル ソース コード

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//目次を含むドキュメントをロードします
Document doc = new Document(dataDir + "Table of contents.docx");

//目次のタブを変更する
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

//変更したドキュメントを保存する
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## 結論

このガイドでは、Aspose.Words for .NET を使用して、提供されている C# ソース コードを使用して Word 文書の目次のタブを変更する方法について説明しました。示されている手順に従うことで、C# アプリケーションの Word 文書の目次タブを簡単にカスタマイズできます。 Aspose.Words は、文書のスタイルと書式設定を操作するための優れた柔軟性と機能を提供し、魅力的でプロフェッショナルな Word 文書を作成できます。

### Word 文書のタブストップの変更に関する FAQ

#### Q: Aspose.Words for .NET の「Word 文書内のタブ位置を変更する」機能の目的は何ですか?

A: Aspose.Words for .NET の「Word 文書のタブストップの変更」機能を使用すると、Word 文書の目次で使用されるタブストップを変更できます。これにより、目次内のページ番号と対応する見出しの配置と位置をカスタマイズできます。

#### Q: Aspose.Words for .NET とは何ですか?

A: Aspose.Words for .NET は、.NET アプリケーションで Word ドキュメントを使用したワード処理用に設計された強力なライブラリです。 C# またはその他の .NET 言語を使用してプログラムで Word ドキュメントを作成、編集、操作、変換するための包括的な機能を提供します。

#### Q: Aspose.Words for .NET を使用して、目次を含む Word 文書をロードするにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して目次を含む Word 文書をロードするには、`Document`クラスとそのコンストラクター。ドキュメントのファイル パスを指定すると、ドキュメントを`Document`物体。以下に例を示します。

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

このコード スニペットは、指定されたディレクトリにあるドキュメント「目次.docx」を読み込みます。

#### Q: Aspose.Words for .NET を使用して目次で使用されるタブを変更するにはどうすればよいですか?

 A: ドキュメントがロードされたら、ドキュメントの各段落を繰り返し処理し、目次 (TOC) の結果スタイルを使用して書式設定されているかどうかを確認できます。段落が目次スタイルとしてフォーマットされている場合は、ページ番号を揃えるために使用されるタブを変更できます。 Aspose.Words for .NET では、`ParagraphFormat`各段落のプロパティを使用してタブストップを取得および変更します。以下に例を示します。

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        TabStop tab = para.ParagraphFormat.TabStops[0];
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }
}
```

このコードでは、ループはドキュメント内の各段落を反復処理します。段落に目次スタイルがある場合、その段落で使用されている最初のタブ ストップにアクセスし、それを削除し、位置を変更して新しいタブ ストップを追加します。

#### Q: Aspose.Words for .NET を使用して、目次の複数のレベルのタブを変更できますか?

A: はい、Aspose.Words for .NET を使用して、目次の複数のレベルのタブを変更できます。各段落を繰り返して目次スタイルを確認することで、各レベルのタブを個別に変更できます。目次の目的のレベルにアクセスし、それに応じてタブ位置を調整できます。

#### Q: Aspose.Words for .NET を使用して目次のタブを変更した後、変更したドキュメントを保存するにはどうすればよいですか?

 A: 目次のタブに必要な変更を加えた後、`Save`の方法`Document`クラス。出力ドキュメントの目的のファイル パスと名前をパラメータとして指定します。`Save`方法。以下に例を示します。

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

このコードは、変更されたドキュメントを「WorkingWithTableOfContent.ChangeTocTabStops.docx」として保存します。

#### Q: Aspose.Words for .NET を使用して、目次の他の部分をカスタマイズできますか?

A: はい、Aspose.Words for .NET を使用すると、目次のさまざまな側面をカスタマイズできます。タブの変更とは別に、目次エントリとページ番号のフォント スタイル、サイズ、配置、その他の書式設定プロパティを変更できます。さらに、対応する見出しのインデント、間隔、書式設定を調整できます。

#### 質問:。 Aspose.Words for .NET を使用して目次のタブの配置とリーダー文字を変更できますか?

A: はい、Aspose.Words for .NET を使用して、目次のタブの配置とリーダー文字を変更できます。タブストップにアクセスし、その配置とリーダーのプロパティを調整することで、目次内のページ番号と対応する見出しの配置と外観を制御できます。

#### Q: Aspose.Words for .NET は、Word ドキュメント内の他のスタイルや書式設定の変更をサポートしていますか?

A: はい、Aspose.Words for .NET は、Word ドキュメントのさまざまなスタイルや書式設定を変更するための広範なサポートを提供します。段落、見出し、表、リストなどのさまざまな要素のスタイルを変更できます。要件に応じて、フォント、色、配置、インデント、間隔、その他の書式設定の側面を変更できます。

#### Q: Aspose.Words for .NET を使用して、既存の Word 文書の目次のタブを変更できますか?

A: はい、Aspose.Words for .NET を使用して、既存の Word 文書の目次のタブを変更できます。ドキュメントをロードし、段落を繰り返し処理し、タブストップに必要な変更を加えることで、目次のタブを更新できます。最後に、ドキュメントを保存して変更を適用します。