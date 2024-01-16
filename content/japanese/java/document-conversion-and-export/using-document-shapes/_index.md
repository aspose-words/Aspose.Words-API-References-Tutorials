---
title: Aspose.Words for Java での文書図形の使用
linktitle: 文書の形状の使用
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java の文書図形の力を解き放ちます。ステップバイステップの例を使用して、視覚的に魅力的なドキュメントを作成する方法を学びます。
type: docs
weight: 14
url: /ja/java/document-conversion-and-export/using-document-shapes/
---

## Aspose.Words for Java でのドキュメント図形の使用の概要

この包括的なガイドでは、Aspose.Words for Java のドキュメント シェイプの世界を詳しく説明します。図形は、視覚的に魅力的でインタラクティブなドキュメントを作成する場合に不可欠な要素です。吹き出し、ボタン、画像、透かしを追加する必要がある場合でも、Aspose.Words for Java はそれを効率的に行うためのツールを提供します。ソース コードの例を使用して、これらの形状の使用方法を段階的に見てみましょう。

## ドキュメントの図形の使用を開始する

コードに入る前に、環境をセットアップしましょう。 Aspose.Words for Java がプロジェクトに統合されていることを確認してください。まだダウンロードしていない場合は、Aspose Web サイトからダウンロードできます。[Java 用 Aspose.Words をダウンロード](https://releases.aspose.com/words/java/)

## ドキュメントへの図形の追加

### GroupShape の挿入

あ`GroupShape`複数の図形をグループ化できます。を作成して挿入する方法は次のとおりです。`GroupShape`:

```java
Document doc = new Document();
doc.ensureMinimum();

GroupShape groupShape = new GroupShape(doc);
Shape accentBorderShape = new Shape(doc, ShapeType.ACCENT_BORDER_CALLOUT_1);
accentBorderShape.setWidth(100.0);
accentBorderShape.setHeight(100.0);

groupShape.appendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ACTION_BUTTON_BEGINNING);
actionButtonShape.setLeft(100.0);
actionButtonShape.setWidth(100.0);
actionButtonShape.setHeight(200.0);

groupShape.appendChild(actionButtonShape);

groupShape.setWidth(200.0);
groupShape.setHeight(200.0);
groupShape.setCoordSize(new Dimension(200, 200));

DocumentBuilder builder = new DocumentBuilder(doc);
builder.insertNode(groupShape);

doc.save("Your Directory Path" + "WorkingWithShapes.AddGroupShape.docx");
```

### テキストボックス図形の挿入

テキスト ボックスの図形を挿入するには、`insertShape`以下の例に示すようなメソッドです。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertShape(ShapeType.TEXT_BOX, RelativeHorizontalPosition.PAGE, 100.0,
    RelativeVerticalPosition.PAGE, 100.0, 50.0, 50.0, WrapType.NONE);

shape.setRotation(30.0);
builder.writeln();

shape = builder.insertShape(ShapeType.TEXT_BOX, 50.0, 50.0);
shape.setRotation(30.0);

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.DOCX);
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);

doc.save("Your Directory Path" + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## 形状プロパティの操作

### アスペクト比の管理

図形のアスペクト比をロックするかどうかを制御できます。シェイプのアスペクト比のロックを解除する方法は次のとおりです。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertImage(getImagesDir() + "Transparent background logo.png");
shape.setAspectRatioLocked(false);

doc.save("Your Directory Path" + "WorkingWithShapes.AspectRatioLocked.docx");
```

### 表のセルに図形を配置する

表のセル内に図形を配置する必要がある場合は、次のコードを使用してこれを実現できます。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.startTable();
builder.getRowFormat().setHeight(100.0);
builder.getRowFormat().setHeightRule(HeightRule.EXACTLY);

for (int i = 0; i < 31; i++) {
    if (i != 0 && i % 7 == 0)
        builder.endRow();

    builder.insertCell();
    builder.write("Cell contents");
}

builder.endTable();

Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.isLayoutInCell(true); //図形をセル内に配置する場合は、表のセルの外側に図形を表示します。
watermark.setWidth(300.0);
watermark.setHeight(70.0);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setRotation(-40);
watermark.setFillColor(Color.GRAY);
watermark.setStrokeColor(Color.GRAY);
watermark.getTextPath().setText("watermarkText");
watermark.getTextPath().setFontFamily("Arial");
watermark.setName("WaterMark_{Guid.NewGuid()}");
watermark.setWrapType(WrapType.NONE);

Run run = (Run) doc.getChildNodes(NodeType.RUN, true).get(doc.getChildNodes(NodeType.RUN, true).getCount() - 1);
builder.moveTo(run);
builder.insertNode(watermark);

doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2010);
doc.save("Your Directory Path" + "WorkingWithShapes.LayoutInCell.docx");
```

## SmartArt シェイプの操作

### SmartArt シェイプの検出

次のコードを使用して、ドキュメント内の SmartArt 図形を検出できます。

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
List<Shape> shapes = IterableUtils.toList(doc.getChildNodes(NodeType.SHAPE, true));
int count = (int) shapes.stream().filter(s -> s.hasSmartArt()).count();
System.out.println("The document has " + count + " shapes with SmartArt.");
```

### SmartArt 図面の更新

ドキュメント内の SmartArt 図面を更新するには、次のコードを使用します。

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true)) {
    if (shape.hasSmartArt())
        shape.updateSmartArtDrawing();
}
```

## 結論

このガイドでは、Aspose.Words for Java のドキュメント シェイプの世界について説明しました。ドキュメントにさまざまな図形を追加し、そのプロパティを操作し、SmartArt 図形を操作する方法を学習しました。この知識があれば、視覚的に魅力的でインタラクティブなドキュメントを簡単に作成できます。

## よくある質問

### Aspose.Words for Java とは何ですか?

Aspose.Words for Java は、開発者が Word ドキュメントをプログラムで作成、変更、変換できるようにする Java ライブラリです。さまざまな形式のドキュメントを操作するための幅広い機能とツールを提供します。

### Aspose.Words for Java をダウンロードするにはどうすればよいですか?

次のリンクに従って、Aspose Web サイトから Aspose.Words for Java をダウンロードできます。[Java 用 Aspose.Words をダウンロード](https://releases.aspose.com/words/java/)

### ドキュメントシェイプを使用する利点は何ですか?

ドキュメントの図形により、ドキュメントに視覚的な要素とインタラクティブ性が追加され、ドキュメントがより魅力的で有益なものになります。図形を使用すると、吹き出し、ボタン、画像、透かしなどを作成でき、全体的なユーザー エクスペリエンスが向上します。

### 図形の外観をカスタマイズできますか?

はい、サイズ、位置、回転、塗りつぶしの色などのプロパティを調整することで、図形の外観をカスタマイズできます。 Aspose.Words for Java には、形状をカスタマイズするための広範なオプションが用意されています。

### Aspose.Words for Java は SmartArt と互換性がありますか?

はい、Aspose.Words for Java は SmartArt 図形をサポートしているため、ドキュメント内の複雑な図やグラフィックを操作できます。