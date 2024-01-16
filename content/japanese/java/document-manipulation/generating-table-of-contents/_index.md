---
title: Aspose.Words for Java での目次の生成
linktitle: 目次の生成
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java を使用して目次 (TOC) を生成およびカスタマイズする方法を学びます。整理されたプロフェッショナルな文書を簡単に作成できます。
type: docs
weight: 21
url: /ja/java/document-manipulation/generating-table-of-contents/
---

## Aspose.Words for Java での目次の生成の概要

このチュートリアルでは、Aspose.Words for Java を使用して目次 (TOC) を生成するプロセスを説明します。目次は、整理されたドキュメントを作成するために重要な機能です。目次の外観とレイアウトをカスタマイズする方法について説明します。

## 前提条件

始める前に、Aspose.Words for Java がインストールされ、Java プロジェクトに設定されていることを確認してください。

## ステップ 1: 新しいドキュメントを作成する

まず、作業する新しいドキュメントを作成しましょう。

```java
Document doc = new Document();
```

## ステップ 2: 目次スタイルをカスタマイズする

目次の外観をカスタマイズするには、目次に関連付けられているスタイルを変更します。この例では、第 1 レベルの目次エントリを太字にします。

```java
doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_1).getFont().setBold(true);
```

## ステップ 3: ドキュメントにコンテンツを追加する

コンテンツをドキュメントに追加できます。このコンテンツは目次を生成するために使用されます。

## ステップ 4: 目次を生成する

目次を生成するには、文書内の目的の場所に目次フィールドを挿入します。このフィールドは、文書内の見出しとスタイルに基づいて自動的に入力されます。

```java
//文書内の目的の場所に目次フィールドを挿入します。
FieldToc fieldToc = new FieldToc();
doc.getFirstSection().getBody().getFirstParagraph().appendChild(fieldToc);
```

## ステップ 5: ドキュメントを保存する

最後に、目次を付けてドキュメントを保存します。

```java
doc.save("your_output_path_here");
```

## 目次のタブストップのカスタマイズ

目次内のタブストップをカスタマイズして、ページ番号のレイアウトを制御することもできます。タブストップを変更する方法は次のとおりです。

```java
Document doc = new Document("Table of contents.docx");

for (Paragraph para : (Iterable<Paragraph>) doc.getChildNodes(NodeType.PARAGRAPH, true))
{
    if (para.getParagraphFormat().getStyle().getStyleIdentifier() >= StyleIdentifier.TOC_1 &&
        para.getParagraphFormat().getStyle().getStyleIdentifier() <= StyleIdentifier.TOC_9)
    {
        //この段落で使用されている、ページ番号を揃える最初のタブを取得します。
        TabStop tab = para.getParagraphFormat().getTabStops().get(0);
        
        //古いタブを取り外します。
        para.getParagraphFormat().getTabStops().removeByPosition(tab.getPosition());
        
        //変更した位置 (例: 50 単位左) に新しいタブを挿入します。
        para.getParagraphFormat().getTabStops().add(tab.getPosition() - 50.0, tab.getAlignment(), tab.getLeader());
    }
}

doc.save("output.docx");
```

これで、ページ番号の配置のためにタブ位置が調整された、カスタマイズされた目次が文書内に作成されました。


## 結論

このチュートリアルでは、Word ドキュメントを操作するための強力なライブラリである Aspose.Words for Java を使用して目次 (TOC) を生成する方法を説明しました。適切に構造化された目次は、長い文書を整理してナビゲートするために不可欠であり、Aspose.Words は、目次を簡単に作成およびカスタマイズするためのツールを提供します。

## よくある質問

### 目次エントリの形式を変更するにはどうすればよいですか?

次を使用して、目次レベルに関連付けられたスタイルを変更できます。`doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_X)`ここで、X は TOC レベルです。

### 目次にさらにレベルを追加するにはどうすればよいですか?

目次にさらに多くのレベルを含めるには、TOC フィールドを変更し、必要なレベル数を指定します。

### 特定の目次エントリのタブストップ位置を変更できますか?

はい、上記のコード例に示すように、段落を反復処理し、それに応じてタブ ストップを変更することで、特定の目次エントリのタブ ストップの位置を変更できます。