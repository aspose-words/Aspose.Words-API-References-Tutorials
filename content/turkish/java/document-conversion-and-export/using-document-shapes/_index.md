---
title: Aspose.Words for Java'da Belge Şekillerini Kullanma
linktitle: Belge Şekillerini Kullanma
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'da Belge Şekillerinin Gücünün Kilidini Açın. Adım Adım Örneklerle Görsel Açıdan İlgi Çekici Belgeler Oluşturmayı Öğrenin.
type: docs
weight: 14
url: /tr/java/document-conversion-and-export/using-document-shapes/
---

## Aspose.Words for Java'da Belge Şekillerini Kullanmaya Giriş

Bu kapsamlı kılavuzda Aspose.Words for Java'daki belge şekillerinin dünyasına gireceğiz. Şekiller, görsel olarak çekici ve etkileşimli belgeler oluşturmada önemli unsurlardır. Açıklamalar, düğmeler, resimler veya filigranlar eklemeniz gerekip gerekmediğini Aspose.Words for Java, bunu verimli bir şekilde yapmanız için gereken araçları sağlar. Bu şekillerin nasıl kullanılacağını adım adım kaynak kod örnekleriyle inceleyelim.

## Belge Şekillerine Başlarken

 Koda geçmeden önce ortamımızı ayarlayalım. Aspose.Words for Java'nın projenize entegre olduğundan emin olun. Henüz yapmadıysanız Aspose web sitesinden indirebilirsiniz.[Aspose.Words for Java'yı indirin](https://releases.aspose.com/words/java/)

## Belgelere Şekil Ekleme

### GroupShape Ekleme

 A`GroupShape` birden çok şekli birlikte gruplamanıza olanak tanır. İşte nasıl oluşturup ekleyebileceğiniz`GroupShape`:

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

### Metin Kutusu Şekli Ekleme

 Metin kutusu şekli eklemek için şunu kullanabilirsiniz:`insertShape` aşağıdaki örnekte gösterildiği gibi yöntem:

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

## Şekil Özelliklerini Değiştirme

### En Boy Oranını Yönetme

Bir şeklin en boy oranının kilitli olup olmadığını kontrol edebilirsiniz. Bir şeklin en boy oranının kilidini nasıl açacağınız aşağıda açıklanmıştır:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertImage(getImagesDir() + "Transparent background logo.png");
shape.setAspectRatioLocked(false);

doc.save("Your Directory Path" + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Tablo Hücresine Şekil Yerleştirme

Bir tablo hücresinin içine bir şekil yerleştirmeniz gerekiyorsa bunu aşağıdaki kodla yapabilirsiniz:

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
watermark.isLayoutInCell(true); // Şekli bir hücreye yerleştirilecekse tablo hücresinin dışında görüntüleyin.
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

## SmartArt Şekilleriyle Çalışmak

### SmartArt Şekillerini Algılama

Aşağıdaki kodu kullanarak bir belgedeki SmartArt şekillerini tespit edebilirsiniz:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
List<Shape> shapes = IterableUtils.toList(doc.getChildNodes(NodeType.SHAPE, true));
int count = (int) shapes.stream().filter(s -> s.hasSmartArt()).count();
System.out.println("The document has " + count + " shapes with SmartArt.");
```

### SmartArt Çizimlerini Güncelleme

Bir belgedeki SmartArt çizimlerini güncellemek için aşağıdaki kodu kullanın:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true)) {
    if (shape.hasSmartArt())
        shape.updateSmartArtDrawing();
}
```

## Çözüm

Bu kılavuzda Aspose.Words for Java'daki belge şekilleri dünyasını keşfettik. Belgelerinize çeşitli şekiller eklemeyi, özelliklerini değiştirmeyi ve SmartArt şekilleriyle çalışmayı öğrendiniz. Bu bilgiyle görsel olarak çekici ve etkileşimli belgeleri kolaylıkla oluşturabilirsiniz.

## SSS'ler

### Aspose.Words for Java nedir?

Aspose.Words for Java, geliştiricilerin Word belgelerini programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan bir Java kitaplığıdır. Çeşitli formatlardaki belgelerle çalışmak için çok çeşitli özellikler ve araçlar sağlar.

### Aspose.Words for Java'yı nasıl indirebilirim?

 Aspose.Words for Java'yı Aspose web sitesinden şu bağlantıyı takip ederek indirebilirsiniz:[Aspose.Words for Java'yı indirin](https://releases.aspose.com/words/java/)

### Belge şekillerini kullanmanın faydaları nelerdir?

Belge şekilleri, belgelerinize görsel öğeler ve etkileşim ekleyerek onları daha ilgi çekici ve bilgilendirici hale getirir. Şekillerle belirtme çizgileri, düğmeler, resimler, filigranlar ve daha fazlasını oluşturarak genel kullanıcı deneyimini geliştirebilirsiniz.

### Şekillerin görünümünü özelleştirebilir miyim?

Evet, boyutları, konumu, dönüşü ve dolgu rengi gibi özelliklerini ayarlayarak şekillerin görünümünü özelleştirebilirsiniz. Aspose.Words for Java şekil özelleştirmesi için kapsamlı seçenekler sunar.

### Aspose.Words for Java, SmartArt ile uyumlu mu?

Evet, Aspose.Words for Java, SmartArt şekillerini destekleyerek belgelerinizdeki karmaşık diyagramlar ve grafiklerle çalışmanıza olanak tanır.