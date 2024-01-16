---
title: Aspose.Words for Java でのテーブルとテーブル スタイルの書式設定
linktitle: 表と表スタイルの書式設定
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java でテーブルをフォーマットし、テーブル スタイルを適用する方法を学びます。ソースコードを含むステップバイステップのガイドを参照して、効果的な表の書式設定を行ってください。 Aspose.Words を使用してドキュメントのレイアウトを強化します。
type: docs
weight: 17
url: /ja/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Aspose.Words for Java でのテーブルとテーブル スタイルの書式設定の概要

表は、文書内の情報を構造化および整理する上で重要な役割を果たします。 Aspose.Words for Java は、表の書式を設定し、表のスタイルを適用して文書の視覚的な魅力を高めるための強力な機能を提供します。このステップバイステップ ガイドでは、Aspose.Words for Java を使用したテーブルの書式設定とテーブル スタイルの適用のさまざまな側面を説明します。

## 前提条件

詳細に入る前に、Aspose.Words for Java ライブラリがプロジェクトに統合されていることを確認してください。 Aspose Web サイトからダウンロードできます。[Java 用 Aspose.Words をダウンロード](https://releases.aspose.com/words/java/).

## 表と周囲のテキストの間の距離を取得する

まず、文書内の表と周囲のテキストとの間の距離を取得する方法を見てみましょう。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## 表にアウトライン枠を適用する

次のコードを使用して、表をページの中央に配置したり、既存の境界線をクリアしたり、カスタムのアウトライン境界線を設定したりできます。

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

## 枠線付きの表を作成する

このコード スニペットは、テーブルを作成し、テーブルとそのセルの両方に境界線を設定する方法を示しています。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## 行の書式設定を変更する

テーブル内の特定の行の書式設定を変更する方法を学びます。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## 行の書式設定を適用する

この例は、テーブル内の行全体に書式設定を適用する方法を示しています。

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

## セルのパディングを設定する

テーブル内の個々のセルにパディングを設定する方法を調べます。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## セルの書式設定を変更する

テーブル内の特定のセルの書式設定を変更する方法を説明します。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## テーブルとセルを異なる枠線で書式設定する

表内の個々のセルに異なる境界線を設定する方法を学びます。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
//テーブルの境界線を設定する
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
//個々のセルにセルのシェーディングを設定する
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
//セルにコンテンツを追加する
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
//次の行のセルの書式設定をクリアします
builder.getCellFormat().clearFormatting();
//この行の最初のセルに大きな境界線を作成します
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

## ステップ 10: セル間隔を許可する

セル間隔を許可し、テーブルの値を設定します。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## ステップ 11: スタイルのある表を作成する

事前定義されたスタイルを使用してテーブルを作成します。

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

## ステップ 12: スタイルからセルと行の書式設定を展開する

表のスタイルを展開してセルと行に書式設定を適用する方法を学びます。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## ステップ 13: 表スタイルを作成する

特定の書式設定を使用してカスタム表スタイルを作成します。

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

## ステップ 14: 条件付き書式を定義する

テーブル内の行に条件付き書式設定を適用します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## ステップ 15: TableCell の書式設定を設定する

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

## ステップ 16: TableRow の書式設定を設定する

テーブル内の行全体に書式設定を適用します。

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

Aspose.Words for Java を使用すると、表をフォーマットし、表のスタイルを正確に適用できます。個々のセルの書式設定の変更からカスタム表スタイルの作成まで、ドキュメントを視覚的に魅力的で整理するためのツールが用意されています。

## よくある質問

### Aspose.Words for Java をダウンロードするにはどうすればよいですか?

 Aspose.Words for Java は、Aspose Web サイトからダウンロードできます。[Java 用 Aspose.Words をダウンロード](https://releases.aspose.com/words/java/).

### 表内の個々のセルに異なる枠線を適用できますか?

はい、このガイドで説明するように、Aspose.Words for Java を使用してテーブル内の個々のセルに異なる境界線を設定できます。

### テーブルのタイトルと説明を設定する目的は何ですか?

表のタイトルと説明を設定すると、文書のアクセシビリティと構成が強化され、読者や支援技術が内容を理解しやすくなります。

### テーブル内の特定の行に条件付き書式設定を適用するにはどうすればよいですか?

このガイドで示すように、条件付き書式設定ルールを使用してカスタム テーブル スタイルを定義することにより、テーブル内の特定の行に条件付き書式設定を適用できます。

### Aspose.Words for Java のドキュメントやリソースはどこで見つけられますか?

包括的なドキュメントと追加リソースについては、Aspose.Words for Java ドキュメントを参照してください。[Aspose.Words for Java ドキュメント](https://reference.aspose.com/words/java/).