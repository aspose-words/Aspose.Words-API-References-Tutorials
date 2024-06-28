---
title: Aspose.Words for Java'da Belgelerde Filigran Kullanma
linktitle: Belgelerde Filigran Kullanma
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'da belgelere nasıl filigran ekleyeceğinizi öğrenin. Profesyonel görünümlü belgeler için metin ve resim filigranlarını özelleştirin.
type: docs
weight: 15
url: /tr/java/document-conversion-and-export/using-watermarks-to-documents/
---

## Aspose.Words for Java'da Belgelere Filigran Eklemeye Giriş

Bu eğitimde Aspose.Words for Java API'sini kullanarak belgelere nasıl filigran ekleneceğini inceleyeceğiz. Filigranlar, belgeleri durumlarını, gizliliklerini veya diğer ilgili bilgileri belirtmek üzere metin veya grafiklerle etiketlemenin yararlı bir yoludur. Bu kılavuzda hem metin hem de resim filigranlarını ele alacağız.

## Aspose.Words for Java'yı kurma

Belgelere filigran eklemeye başlamadan önce Aspose.Words for Java'yı kurmamız gerekiyor. Başlamak için şu adımları izleyin:

1.  Aspose.Words for Java'yı şu adresten indirin:[Burada](https://releases.aspose.com/words/java/).
2. Aspose.Words for Java kütüphanesini Java projenize ekleyin.
3. Gerekli sınıfları Java kodunuza aktarın.

Artık kitaplığı kurduğumuza göre filigran eklemeye devam edebiliriz.

## Metin Filigranı Ekleme

Belgelerinize metin bilgisi eklemek istediğinizde metin filigranları yaygın bir seçimdir. Aspose.Words for Java'yı kullanarak nasıl metin filigranı ekleyebileceğiniz aşağıda açıklanmıştır:

```java
//Belge örneği oluşturma
Document doc = new Document("Document.docx");

// Metin Filigranı Seçeneklerini Tanımla
TextWatermarkOptions options = new TextWatermarkOptions();
options.setFontFamily("Arial");
options.setFontSize(36f);
options.setColor(Color.BLACK);
options.setLayout(WatermarkLayout.HORIZONTAL);
options.setSemitransparent(false);

// Filigran metnini ve seçeneklerini ayarlama
doc.getWatermark().setText("Test", options);

// Belgeyi filigranla kaydedin
doc.save("DocumentWithWatermark.docx");
```

## Resim Filigranları Ekleme

Belgelerinize metin filigranlarının yanı sıra resim filigranları da ekleyebilirsiniz. Resim filigranını nasıl ekleyeceğiniz aşağıda açıklanmıştır:

```java
//Belge örneği oluşturma
Document doc = new Document("Document.docx");

// Filigran için resmi yükleyin
byte[] imageBytes = Files.readAllBytes(Paths.get("watermark.png"));
Shape watermark = new Shape(doc, ShapeType.IMAGE);
watermark.getImageData().setImage(imageBytes);

// Filigran boyutunu ve konumunu ayarlayın
watermark.setWidth(200.0);
watermark.setHeight(100.0);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.CENTER);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.CENTER);

// Filigranı belgeye ekleme
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// Belgeyi filigranla kaydedin
doc.save("DocumentWithImageWatermark.docx");
```

## Filigranları Özelleştirme

Görünümlerini ve konumlarını ayarlayarak filigranları özelleştirebilirsiniz. Metin filigranlarında yazı tipini, boyutunu, rengini ve düzenini değiştirebilirsiniz. Görüntü filigranlarının boyutunu ve konumunu önceki örneklerde gösterildiği gibi değiştirebilirsiniz.

## Filigranları Kaldırma

Filigranları bir belgeden kaldırmak için aşağıdaki kodu kullanabilirsiniz:

```java
//Belge örneği oluşturma
Document doc = new Document("DocumentWithWatermark.docx");

// Filigranı kaldır
for (Shape shape : doc.getShapes())
{
    if (shape.getName().contains("Watermark"))
    {
        shape.remove();
    }
}

// Belgeyi filigran olmadan kaydedin
doc.save("DocumentWithoutWatermark.docx");
```


## Çözüm

Bu eğitimde Aspose.Words for Java kullanarak belgelere nasıl filigran ekleneceğini öğrendik. İster metin ister resim filigranı eklemeniz gerekiyorsa Aspose.Words, bunları verimli bir şekilde özelleştirmeniz ve yönetmeniz için gerekli araçları sağlar. Ayrıca artık ihtiyaç duyulmadığında filigranları kaldırarak belgelerinizin temiz ve profesyonel olmasını sağlayabilirsiniz.

## SSS'ler

### Bir metin filigranının yazı tipini nasıl değiştirebilirim?

 Bir metin filigranının yazı tipini değiştirmek için`setFontFamily` içindeki mülk`TextWatermarkOptions`. Örneğin:

```java
options.setFontFamily("Times New Roman");
```

### Tek bir belgeye birden fazla filigran ekleyebilir miyim?

 Evet, birden fazla filigran oluşturarak bir belgeye birden fazla filigran ekleyebilirsiniz.`Shape` farklı ayarlara sahip nesneler ve bunları belgeye ekleme.

### Filigranı döndürmek mümkün mü?

 Evet, filigranı ayarlayarak döndürebilirsiniz.`setRotation` içindeki mülk`Shape` nesne. Pozitif değerler filigranı saat yönünde döndürür, negatif değerler ise saat yönünün tersine döndürür.

### Bir filigranı nasıl yarı şeffaf hale getirebilirim?

 Bir filigranı yarı şeffaf yapmak için`setSemitransparent`mülkiyet`true` içinde`TextWatermarkOptions`.

### Bir belgenin belirli bölümlerine filigran ekleyebilir miyim?

Evet, bölümleri yineleyerek ve filigranı istediğiniz bölümlere ekleyerek belgenin belirli bölümlerine filigran ekleyebilirsiniz.