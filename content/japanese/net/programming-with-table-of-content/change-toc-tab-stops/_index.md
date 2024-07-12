---
title: Word 文書の目次タブ位置を変更する
linktitle: Word 文書の目次タブ位置を変更する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書の目次タブを変更する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words for .NET は、C# アプリケーションで Word 文書を作成、編集、操作するための強力なライブラリです。Aspose.Words が提供する機能の中には、Word 文書の目次で使用されるタブを変更する機能があります。このガイドでは、Aspose.Words for .NET の C# ソース コードを使用して、文書の目次のタブを変更する方法を説明します。

## Aspose.Words ライブラリを理解する

コードに進む前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。Aspose.Words は、Word ドキュメントでの Words 処理を簡単かつ効率的にする人気のライブラリです。目次タブの変更など、Word ドキュメントの作成、編集、操作のための幅広い機能を提供します。

## 目次を含むドキュメントを読み込む

最初のステップは、変更する目次を含む Word 文書を読み込むことです。Document クラスを使用して、ソース ファイルから文書を読み込みます。次に例を示します。

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

この例では、ドキュメント ディレクトリにあるドキュメント「Table of Contents.docx」を読み込みます。

## 目次のタブを変更する

ドキュメントが読み込まれたら、ドキュメントの各段落を調べて、目次 (TOC) 結果スタイルを使用してフォーマットされているかどうかを確認します。フォーマットされている場合は、ページ番号を揃えるために使用されるタブを変更します。方法は次のとおりです。

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

この例では、ループを使用してドキュメント内の各段落をループします。次に、段落が目次結果 (TOC) スタイルを使用してフォーマットされているかどうかを確認します。フォーマットされている場合は、この段落で使用されている最初のタブにアクセスし、古いタブを削除して位置を変更した新しいタブを追加してタブを変更します。

## 変更した文書を保存する

目次のタブに必要な変更を加えたら、Document クラスの Save メソッドを使用して変更したドキュメントを保存できます。次に例を示します。

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

この例では、変更されたドキュメントを「WorkingWithTableOfContent.ChangeTocTabStops.docx」として保存します。

### Aspose.Words for .NET の「目次タブの編集」機能のサンプル ソース コード

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//目次を含む文書を読み込む
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

このガイドでは、提供されている C# ソース コードを使用して、Aspose.Words for .NET で Word 文書の目次のタブを変更する方法について説明しました。提供されている手順に従うことで、C# アプリケーションで Word 文書の目次のタブを簡単にカスタマイズできます。Aspose.Words は、文書のスタイルと書式設定を操作するための優れた柔軟性とパワーを提供し、魅力的でプロフェッショナルな Word 文書を作成できます。

### Word 文書の目次タブ ストップの変更に関する FAQ

#### Q: Aspose.Words for .NET の「Word 文書の目次タブ ストップの変更」機能の目的は何ですか?

A: Aspose.Words for .NET の「Word 文書の目次タブ ストップ変更」機能を使用すると、Word 文書の目次で使用されるタブ ストップを変更できます。これにより、目次内のページ番号と対応する見出しの配置と位置をカスタマイズできます。

#### Q: Aspose.Words for .NET とは何ですか?

A: Aspose.Words for .NET は、.NET アプリケーションで Word 文書を処理するために設計された強力なライブラリです。C# またはその他の .NET 言語を使用してプログラムで Word 文書を作成、編集、操作、変換するための包括的な機能を提供します。

#### Q: Aspose.Words for .NET を使用して目次を含む Word 文書を読み込むにはどうすればよいでしょうか?

 A: Aspose.Words for .NETを使用して目次を含むWord文書を読み込むには、`Document`クラスとそのコンストラクタ。ドキュメントのファイルパスを指定すると、`Document`オブジェクト。次に例を示します。

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

このコード スニペットは、指定されたディレクトリにあるドキュメント「Table of Contents.docx」を読み込みます。

#### Q: Aspose.Words for .NET を使用して目次で使用されるタブを変更するにはどうすればよいですか?

 A: ドキュメントが読み込まれたら、ドキュメントの各段落を反復処理して、目次 (TOC) 結果スタイルを使用して書式設定されているかどうかを確認できます。段落が TOC スタイルとして書式設定されている場合は、ページ番号を揃えるために使用されるタブを変更できます。Aspose.Words for .NET では、`ParagraphFormat`各段落のプロパティを使用してタブ ストップを取得および変更します。次に例を示します。

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

このコードでは、ループはドキュメント内の各段落を反復処理します。段落に TOC スタイルがある場合は、その段落で使用されている最初のタブ ストップにアクセスしてそれを削除し、位置を変更した新しいタブ ストップを追加します。

#### Q: Aspose.Words for .NET を使用して、目次内の複数レベルのタブを変更できますか?

A: はい、Aspose.Words for .NET を使用すると、目次の複数のレベルのタブを変更できます。各段落を反復処理して TOC スタイルを確認することで、各レベルのタブを個別に変更できます。目次の目的のレベルにアクセスし、それに応じてタブ ストップを調整できます。

#### Q: Aspose.Words for .NET を使用して目次のタブを変更した後、変更したドキュメントを保存するにはどうすればよいですか?

 A: 目次のタブに必要な変更を加えた後、`Save`方法の`Document`クラス。出力ドキュメントのファイルパスと名前をパラメータとして指定します。`Save`方法。次に例を示します。

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

このコードは、変更されたドキュメントを「WorkingWithTableOfContent.ChangeTocTabStops.docx」として保存します。

#### Q: Aspose.Words for .NET を使用して目次の他の側面をカスタマイズできますか?

A: はい、Aspose.Words for .NET を使用すると、目次のさまざまな側面をカスタマイズできます。タブの変更以外にも、目次のエントリやページ番号のフォント スタイル、サイズ、配置、その他の書式設定プロパティを変更できます。さらに、対応する見出しのインデント、間隔、書式設定を調整できます。

#### Q: Aspose.Words for .NET を使用して目次のタブ配置とリーダー文字を変更できますか?

A: はい、Aspose.Words for .NET を使用して、目次のタブ配置とリーダー文字を変更できます。タブ ストップにアクセスし、その配置とリーダーのプロパティを調整することで、目次のページ番号と対応する見出しの配置と外観を制御できます。

#### Q: Aspose.Words for .NET は、Word 文書内の他のスタイルや書式の変更をサポートしていますか?

A: はい、Aspose.Words for .NET は、Word 文書のさまざまなスタイルや書式を変更するための広範なサポートを提供します。段落、見出し、表、リストなどのさまざまな要素のスタイルを変更できます。フォント、色、配置、インデント、間隔、その他の書式設定の側面を、要件に応じて変更できます。

#### Q: Aspose.Words for .NET を使用して、既存の Word 文書の目次のタブを変更できますか?

A: はい、Aspose.Words for .NET を使用して、既存の Word ドキュメントの目次のタブを変更できます。ドキュメントを読み込み、段落を反復処理し、タブ ストップに必要な変更を加えることで、目次のタブを更新できます。最後に、ドキュメントを保存して変更を適用します。