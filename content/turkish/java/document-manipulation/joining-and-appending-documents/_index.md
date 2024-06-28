---
title: Aspose.Words for Java'da Belgeleri Birleştirme ve Ekleme
linktitle: Belgelerin Birleştirilmesi ve Eklenmesi
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'yı kullanarak belgeleri kolayca birleştirmeyi ve eklemeyi öğrenin. Biçimlendirmeyi koruyun, üstbilgi altbilgilerini yönetin ve daha fazlasını yapın.
type: docs
weight: 30
url: /tr/java/document-manipulation/joining-and-appending-documents/
---

## Aspose.Words for Java'da Belgeleri Birleştirme ve Eklemeye Giriş

Bu eğitimde Aspose.Words for Java kütüphanesini kullanarak belgeleri nasıl birleştirip ekleyeceğimizi keşfedeceğiz. Biçimlendirmeyi ve yapıyı korurken birden çok belgeyi sorunsuz bir şekilde nasıl birleştireceğinizi öğreneceksiniz.

## Önkoşullar

Başlamadan önce Java projenizde Aspose.Words for Java API'sinin kurulu olduğundan emin olun.

## Belge Birleştirme Seçenekleri

### Basit Ekle

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### İçe Aktarma Formatı Seçenekleri ile Ekle

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### Boş Belgeye Ekle

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Sayfa Numarası Dönüşümleriyle Ekle

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); // NUMPAGES alanı dönüştür
dstDoc.updatePageLayout(); // Doğru numaralandırma için sayfa düzenini güncelleyin
```

## Farklı Sayfa Düzenlerini Yönetme

Farklı sayfa düzenlerine sahip belgeleri eklerken:

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
// Sayfa yapısı ayarlarının hedef belgeyle eşleştiğinden emin olun
```

## Farklı Stillerdeki Belgeleri Birleştirme

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## Akıllı Stil Davranışı

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## DocumentBuilder ile Belge Ekleme

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Kaynak Numaralandırmasının Tutulması

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Metin Kutularını Kullanma

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Üstbilgileri ve Altbilgileri Yönetme

### Üstbilgileri ve Altbilgileri Bağlama

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Üstbilgilerin ve Altbilgilerin Bağlantısını Kaldırma

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Çözüm

Aspose.Words for Java, ister biçimlendirmeyi korumanız, farklı sayfa düzenlerini yönetmeniz veya üstbilgileri ve altbilgileri yönetmeniz olsun, belgeleri birleştirmek ve eklemek için esnek ve güçlü araçlar sağlar. Özel belge işleme ihtiyaçlarınızı karşılamak için bu teknikleri deneyin.

## SSS'ler

### Farklı stillerdeki belgeleri sorunsuz bir şekilde nasıl birleştirebilirim?

 Farklı stillerdeki belgeleri birleştirmek için şunu kullanın:`ImportFormatMode.USE_DESTINATION_STYLES` eklerken.

### Belgeleri eklerken sayfa numaralandırmasını koruyabilir miyim?

 Evet, sayfa numaralandırmasını aşağıdaki komutu kullanarak koruyabilirsiniz:`convertNumPageFieldsToPageRef` yöntemi ve sayfa düzeninin güncellenmesi.

### Akıllı Stil Davranışı Nedir?

 Akıllı Stil Davranışı, belgeleri eklerken tutarlı stillerin korunmasına yardımcı olur. Şununla kullan:`ImportFormatOptions` daha iyi sonuçlar için.

### Belgeleri eklerken metin kutularını nasıl kullanabilirim?

Ayarlamak`importFormatOptions.setIgnoreTextBoxes(false)` ekleme sırasında metin kutularını dahil etmek için.

### Belgeler arasında üstbilgileri ve altbilgileri bağlamak/bağlantısını kaldırmak istersem ne olur?

 Üstbilgileri ve altbilgileri şu şekilde bağlayabilirsiniz:`linkToPrevious(true)` veya bunların bağlantısını kaldırın`linkToPrevious(false)` ihyaç olduğu gibi.