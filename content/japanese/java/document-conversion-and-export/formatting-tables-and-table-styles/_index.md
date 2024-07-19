---
title: Aspose.Words for Java でのテーブルとテーブル スタイルの書式設定
linktitle: 表の書式設定と表スタイル
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java でテーブルをフォーマットし、テーブル スタイルを適用する方法を学びます。効果的なテーブル フォーマットのためのソース コード付きのステップ バイ ステップ ガイドを調べます。Aspose.Words を使用してドキュメント レイアウトを強化します。
type: docs
weight: 17
url: /ja/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Aspose.Words for Java での表の書式設定と表スタイルの概要

表は、ドキュメント内の情報を構造化および整理する上で重要な役割を果たします。Aspose.Words for Java は、表の書式設定や表スタイルの適用を行う強力な機能を提供し、ドキュメントの見た目を向上します。このステップ バイ ステップ ガイドでは、Aspose.Words for Java を使用して表を書式設定し、表スタイルを適用するさまざまな側面について説明します。

## 前提条件

詳細に入る前に、Aspose.Words for Java ライブラリがプロジェクトに統合されていることを確認してください。Aspose の Web サイトからダウンロードできます。[Aspose.Words for Java をダウンロード](https://releases.aspose.com/words/java/).

## 表と周囲のテキスト間の距離を取得する

まず、ドキュメント内の表と周囲のテキスト間の距離を取得する方法を見てみましょう。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## 表にアウトライン罫線を適用する

次のコードを使用すると、表をページの中央に揃え、既存の境界線をクリアし、カスタムのアウトライン境界線を設定できます。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAlignment(TableAlignment.CENTER);
table.clearBorders();
table.setBorder(BorderType.LEFT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.RIGHT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.TOP, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.BOTTOM, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setShading(TextureIndex.TEXTURE_SOLID, Color.lightGray, new Color(0, true));
```

## 境界線付きの表を作成する

このコード スニペットは、テーブルを作成し、テーブルとそのセルの両方に境界線を設定する方法を示しています。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## 行の書式を変更する

テーブル内の特定の行の書式を変更する方法を学習します。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## 行の書式設定を適用する

この例では、テーブル内の行全体に書式を適用する方法を示します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
builder.insertCell();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## セルの余白を設定する

テーブル内の個々のセルにパディングを設定する方法を確認します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## セルの書式を変更する

テーブル内の特定のセルの書式を変更する方法について説明します。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## 表とセルを異なる境界線で書式設定する

表内の個々のセルに異なる境界線を設定する方法を学習します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
//表の境界線を設定する
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
//個々のセルのセルの網掛けを設定する
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
//セルにコンテンツを追加する
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
//次の行のセルの書式をクリアする
builder.getCellFormat().clearFormatting();
//この行の最初のセルに大きい境界線を作成します
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## テーブルのタイトルと説明を設定する

テーブルにタイトルと説明を追加します。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## ステップ10: セルの間隔を許可する

セル間隔を許可し、テーブルのその値を設定します。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## ステップ11: スタイル付きのテーブルを作成する

定義済みのスタイルでテーブルを作成します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## ステップ12: スタイルからセルと行の書式設定を展開する

表スタイルを展開してセルと行に書式を適用する方法を学習します。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## ステップ13: 表スタイルを作成する

特定の書式でカスタム テーブル スタイルを作成します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## ステップ14: 条件付き書式を定義する

表の行に条件付き書式を適用します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## ステップ15: TableCellの書式設定

個々のセルに特定の書式を設定します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
CellFormat cellFormat = builder.getCellFormat();
cellFormat.setWidth(250.0);
cellFormat.setLeftPadding(30.0);
cellFormat.setRightPadding(30.0);
cellFormat.setTopPadding(30.0);
cellFormat.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## ステップ16: TableRowの書式設定を設定する

表の行全体に書式を適用します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## 結論

Aspose.Words for Java を使用すると、表の書式設定や表スタイルを正確に適用できます。個々のセルの書式設定の変更からカスタム表スタイルの作成まで、ドキュメントを視覚的に魅力的で整理されたものにするためのツールが用意されています。

## よくある質問

### Aspose.Words for Java をダウンロードするにはどうすればいいですか?

 Aspose.Words for Java は Aspose の Web サイトからダウンロードできます。[Aspose.Words for Java をダウンロード](https://releases.aspose.com/words/java/).

### 表内の個々のセルに異なる境界線を適用できますか?

はい、このガイドで説明されているように、Aspose.Words for Java を使用して、テーブル内の個々のセルに異なる境界線を設定できます。

### 表のタイトルと説明を設定する目的は何ですか?

表のタイトルと説明を設定すると、ドキュメントのアクセシビリティと構成が向上し、読者や支援技術がコンテンツを理解しやすくなります。

### 表内の特定の行に条件付き書式を適用するにはどうすればよいですか?

このガイドに示すように、条件付き書式設定ルールを使用してカスタム テーブル スタイルを定義することで、テーブル内の特定の行に条件付き書式を適用できます。

### Aspose.Words for Java の詳細なドキュメントやリソースはどこで入手できますか?

包括的なドキュメントと追加リソースについては、Aspose.Words for Java のドキュメントをご覧ください。[Aspose.Words for Java ドキュメント](https://reference.aspose.com/words/java/).