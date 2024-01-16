---
title: Aspose.Words for Java でのドキュメントへのウォーターマークの使用
linktitle: 文書への透かしの使用
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java でドキュメントに透かしを追加する方法を学びます。テキストと画像の透かしをカスタマイズして、プロフェッショナルな外観のドキュメントを作成します。
type: docs
weight: 15
url: /ja/java/document-conversion-and-export/using-watermarks-to-documents/
---

## Aspose.Words for Java でのドキュメントへのウォーターマークの追加の概要

このチュートリアルでは、Aspose.Words for Java API を使用してドキュメントにウォーターマークを追加する方法を検討します。透かしは、文書にテキストやグラフィックのラベルを付けて、文書のステータス、機密性、その他の関連情報を示す便利な方法です。このガイドでは、テキストと画像のウォーターマークの両方について説明します。

## Java 用 Aspose.Words のセットアップ

ドキュメントにウォーターマークを追加する前に、Aspose.Words for Java をセットアップする必要があります。開始するには、次の手順に従ってください。

1.  Aspose.Words for Java を次からダウンロードします。[ここ](https://releases.aspose.com/words/java/).
2. Aspose.Words for Java ライブラリを Java プロジェクトに追加します。
3. Java コードに必要なクラスをインポートします。

ライブラリを設定したので、透かしの追加に進みましょう。

## テキストの透かしを追加する

テキスト透かしは、文書にテキスト情報を追加する場合によく使用されます。 Aspose.Words for Java を使用してテキストの透かしを追加する方法は次のとおりです。

```java
//ドキュメントインスタンスを作成する
Document doc = new Document("Document.docx");

//TextWatermarkOptions の定義
TextWatermarkOptions options = new TextWatermarkOptions();
options.setFontFamily("Arial");
options.setFontSize(36f);
options.setColor(Color.BLACK);
options.setLayout(WatermarkLayout.HORIZONTAL);
options.setSemitransparent(false);

//透かしのテキストとオプションを設定する
doc.getWatermark().setText("Test", options);

//透かしを入れて文書を保存する
doc.save("DocumentWithWatermark.docx");
```

## 画像の透かしを追加する

テキストの透かしに加えて、画像の透かしをドキュメントに追加することもできます。画像の透かしを追加する方法は次のとおりです。

```java
//ドキュメントインスタンスを作成する
Document doc = new Document("Document.docx");

//透かし用の画像を読み込みます
byte[] imageBytes = Files.readAllBytes(Paths.get("watermark.png"));
Shape watermark = new Shape(doc, ShapeType.IMAGE);
watermark.getImageData().setImage(imageBytes);

//ウォーターマークのサイズと位置を設定する
watermark.setWidth(200.0);
watermark.setHeight(100.0);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.CENTER);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.CENTER);

//文書に透かしを追加する
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

//透かしを入れて文書を保存する
doc.save("DocumentWithImageWatermark.docx");
```

## 透かしのカスタマイズ

透かしの外観と位置を調整して、透かしをカスタマイズできます。テキストの透かしの場合、フォント、サイズ、色、レイアウトを変更できます。画像の透かしの場合は、前の例で示したように、そのサイズと位置を変更できます。

## ウォーターマークの削除

文書から透かしを削除するには、次のコードを使用できます。

```java
//ドキュメントインスタンスを作成する
Document doc = new Document("DocumentWithWatermark.docx");

//透かしを削除する
for (Shape shape : doc.getShapes())
{
    if (shape.getName().contains("Watermark"))
    {
        shape.remove();
    }
}

//透かしを入れずに文書を保存する
doc.save("DocumentWithoutWatermark.docx");
```


## 結論

このチュートリアルでは、Aspose.Words for Java を使用してドキュメントにウォーターマークを追加する方法を学習しました。テキストまたは画像の透かしを追加する必要がある場合でも、Aspose.Words はそれらを効率的にカスタマイズおよび管理するためのツールを提供します。不要になった透かしを削除することもできるので、文書をきれいでプロフェッショナルなものにすることができます。

## よくある質問

### テキストの透かしのフォントを変更するにはどうすればよいですか?

テキストの透かしのフォントを変更するには、`setFontFamily`のプロパティ`TextWatermarkOptions`。例えば：

```java
options.setFontFamily("Times New Roman");
```

### 1 つのドキュメントに複数の透かしを追加できますか?

はい、複数のウォーターマークを作成することで、ドキュメントに複数のウォーターマークを追加できます。`Shape`異なる設定を持つオブジェクトを作成し、ドキュメントに追加します。

### 透かしを回転させることは可能ですか?

はい、設定することで透かしを回転できます。`setRotation`のプロパティ`Shape`物体。正の値を指定するとウォーターマークが時計回りに回転し、負の値を指定すると反時計回りに回転します。

### ウォーターマークを半透明にするにはどうすればよいですか?

ウォーターマークを半透明にするには、`setSemitransparent`財産を`true`の中に`TextWatermarkOptions`.

### 文書の特定のセクションに透かしを追加できますか?

はい、セクションを反復処理して目的のセクションにウォーターマークを追加することで、ドキュメントの特定のセクションにウォーターマークを追加できます。