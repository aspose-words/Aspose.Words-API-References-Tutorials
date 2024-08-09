---
title: Belge Filigranı ve Sayfa Yapısı
linktitle: Belge Filigranı ve Sayfa Yapısı
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java ile filigranları nasıl uygulayacağınızı ve sayfa yapılandırmalarını nasıl ayarlayacağınızı öğrenin. Kaynak koduyla birlikte kapsamlı bir kılavuz.
type: docs
weight: 13
url: /tr/java/document-styling/document-watermarking-page-setup/
---
## giriiş

Belge işleme alanında Aspose.Words for Java, geliştiricilerin belge işlemenin her yönü üzerinde kontrol sahibi olmalarına olanak tanıyan güçlü bir araç olarak duruyor. Bu kapsamlı kılavuzda Aspose.Words for Java kullanarak belge filigranlama ve sayfa düzeninin inceliklerini inceleyeceğiz. İster deneyimli bir geliştirici olun ister Java belge işleme dünyasına yeni adım atın, bu adım adım kılavuz sizi ihtiyacınız olan bilgi ve kaynak koduyla donatacaktır.

## Belge Filigranı

### Filigran Ekleme

Belgelere filigran eklemek, içeriğinizi markalamak veya güvence altına almak için çok önemli olabilir. Aspose.Words for Java bu görevi basitleştirir. İşte nasıl:

```java
// Belgeyi yükleyin
Document doc = new Document("document.docx");

// Filigran oluşturma
Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.getTextPath().setText("Confidential");
watermark.setWidth(300);
watermark.setHeight(100);

// Filigranı konumlandırın
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.setWrapType(WrapType.NONE);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);

// Filigranı ekleyin
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// Belgeyi kaydet
doc.save("document_with_watermark.docx");
```

### Filigranları Özelleştirme

Yazı tipini, boyutunu, rengini ve dönüşünü ayarlayarak filigranları daha da özelleştirebilirsiniz. Bu esneklik, filigranınızın belgenizin stiliyle kusursuz bir şekilde eşleşmesini sağlar.

## Sayfa Yapısı

### Sayfa Boyutu ve Yönü

Sayfa düzeni belge biçimlendirmesinde çok önemlidir. Aspose.Words for Java, sayfa boyutu ve yönü üzerinde tam kontrol sunar:

```java
// Belgeyi yükleyin
Document doc = new Document("document.docx");

// Sayfa boyutunu A4 olarak ayarla
doc.getFirstSection().getPageSetup().setPageWidth(595.0);
doc.getFirstSection().getPageSetup().setPageHeight(842.0);

// Sayfa yönünü yatay olarak değiştirme
doc.getFirstSection().getPageSetup().setOrientation(Orientation.LANDSCAPE);

// Değiştirilen belgeyi kaydet
doc.save("formatted_document.docx");
```

### Kenar Boşlukları ve Sayfa Numaralandırma

Profesyonel belgeler için kenar boşlukları ve sayfa numaralandırma üzerinde hassas kontrol şarttır. Aspose.Words for Java ile bunu başarabilirsiniz:

```java
// Belgeyi yükleyin
Document doc = new Document("document.docx");

// Kenar boşluklarını ayarlayın
doc.getFirstSection().getPageSetup().setLeftMargin(72.0);
doc.getFirstSection().getPageSetup().setRightMargin(72.0);
doc.getFirstSection().getPageSetup().setTopMargin(72.0);
doc.getFirstSection().getPageSetup().setBottomMargin(72.0);

// Sayfa numaralandırmayı etkinleştir
doc.getFirstSection().getPageSetup().setDifferentFirstPageHeaderFooter(true);
HeaderFooter firstPageHeader = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.HEADER_FIRST);
firstPageHeader.appendParagraph("First Page Header");

// Biçimlendirilmiş belgeyi kaydedin
doc.save("formatted_document.docx");
```

## SSS

### Bir belgeden filigranı nasıl kaldırabilirim?

Bir belgeden filigranı kaldırmak için belgenin şekillerini yineleyebilir ve filigranı temsil eden şekilleri kaldırabilirsiniz. İşte bir kesit:

```java
Document doc = new Document("document_with_watermark.docx");

for (Shape shape : doc.getChildNodes(NodeType.SHAPE, true).<Shape>toArray()) {
    if (shape.getText().contains("Confidential")) {
        shape.remove();
    }
}

doc.save("document_without_watermark.docx");
```

### Tek bir belgeye birden fazla filigran ekleyebilir miyim?

Evet, ek Shape nesneleri oluşturup bunları gerektiği gibi konumlandırarak bir belgeye birden fazla filigran ekleyebilirsiniz.

### Yatay yönde sayfa boyutunu yasal olarak nasıl değiştiririm?

Sayfa boyutunu yatay yönde yasal olarak ayarlamak için sayfa genişliğini ve yüksekliğini aşağıdaki gibi değiştirin:

```java
doc.getFirstSection().getPageSetup().setPageWidth(842.0);
doc.getFirstSection().getPageSetup().setPageHeight(595.0);
```

### Filigranlar için varsayılan yazı tipi nedir?

Filigranlar için varsayılan yazı tipi, yazı tipi boyutu 36 olan Calibri'dir.

### Belirli bir sayfadan başlayarak sayfa numaralarını nasıl ekleyebilirim?

Bunu, belgenizdeki başlangıç sayfa numarasını aşağıdaki gibi ayarlayarak sağlayabilirsiniz:

```java
doc.getFirstSection().getPageSetup().setPageStartingNumber(5);
```

### Üstbilgi veya altbilgideki metni nasıl ortaya hizalarım?

Üstbilgi veya altbilgideki metni, üstbilgi veya altbilgi içindeki Paragraph nesnesindeki setAlignment yöntemini kullanarak ortalayarak hizalayabilirsiniz.

## Çözüm

Bu kapsamlı kılavuzda Aspose.Words for Java'yı kullanarak belge filigranlama ve sayfa düzeni sanatını inceledik. Sağlanan kaynak kod parçacıkları ve öngörülerle donanmış olarak artık belgelerinizi ustalıkla işlemek ve biçimlendirmek için gereken araçlara sahipsiniz. Aspose.Words for Java, tam spesifikasyonlarınıza göre uyarlanmış profesyonel, markalı belgeler oluşturmanıza olanak sağlar.

Belge manipülasyonunda ustalaşmak geliştiriciler için değerli bir beceridir ve Aspose.Words for Java bu yolculukta güvenilir arkadaşınızdır. Bugün çarpıcı belgeler oluşturmaya başlayın!