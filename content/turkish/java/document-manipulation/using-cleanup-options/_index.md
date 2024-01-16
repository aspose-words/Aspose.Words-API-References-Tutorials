---
title: Aspose.Words for Java'da Temizleme Seçeneklerini Kullanma
linktitle: Temizleme Seçeneklerini Kullanma
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java Temizleme Seçenekleri ile Belge Netliğini Artırın. Boş paragrafları, kullanılmayan bölgeleri ve daha fazlasını nasıl kaldıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/java/document-manipulation/using-cleanup-options/
---

## Aspose.Words for Java'da Temizleme Seçeneklerini Kullanmaya Giriş

Bu eğitimde, adres-mektup birleştirme işlemi sırasında belgeleri düzenlemek ve temizlemek için Aspose.Words for Java'daki temizleme seçeneklerinin nasıl kullanılacağını keşfedeceğiz. Temizleme seçenekleri, boş paragrafların, kullanılmayan bölgelerin ve daha fazlasının kaldırılması gibi belge temizlemenin çeşitli yönlerini kontrol etmenize olanak tanır.

## Önkoşullar

 Başlamadan önce Aspose.Words for Java kütüphanesinin projenize entegre olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/java/).

## Adım 1: Boş Paragrafları Kaldırma

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Birleştirme alanları ekle
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

// Temizleme seçeneklerini ayarlayın
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

// Noktalama işaretleriyle paragrafların temizlenmesini etkinleştirin
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

// Adres-mektup birleştirmeyi yürüt
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

// Belgeyi kaydet
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

Bu örnekte yeni bir belge oluşturuyoruz, birleştirme alanları ekliyoruz ve temizleme seçeneklerini boş paragrafları kaldıracak şekilde ayarlıyoruz. Ayrıca noktalama işaretli paragrafların kaldırılmasını da sağlıyoruz. Adres-mektup birleştirmeyi yürüttükten sonra belge, belirtilen temizleme uygulanarak kaydedilir.

## 2. Adım: Birleştirilmemiş Bölgeleri Kaldırma

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

// Kullanılmayan bölgeleri kaldırmak için temizleme seçeneklerini ayarlayın
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

// Bölgelerle adres-mektup birleştirmeyi yürütme
doc.getMailMerge().executeWithRegions(data);

// Belgeyi kaydet
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

Bu örnekte, birleştirme bölgeleri içeren mevcut bir belgeyi açıyoruz, temizleme seçeneklerini kullanılmayan bölgeleri kaldıracak şekilde ayarlıyoruz ve ardından adres-mektup birleştirmeyi boş verilerle yürütüyoruz. Bu işlem, kullanılmayan bölgeleri belgeden otomatik olarak kaldırır.

## 3. Adım: Boş Alanları Kaldırma

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Boş alanları kaldırmak için temizleme seçeneklerini ayarlayın
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

// Adres-mektup birleştirmeyi yürüt
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Belgeyi kaydet
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

Bu örnekte, birleştirme alanları içeren bir belge açıyoruz, temizleme seçeneklerini boş alanları kaldıracak şekilde ayarlıyoruz ve adres-mektup birleştirmeyi verilerle yürütüyoruz. Birleştirmeden sonra tüm boş alanlar belgeden kaldırılacaktır.

## Adım 4: Kullanılmayan Alanları Kaldırma

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Kullanılmayan alanları kaldırmak için temizleme seçeneklerini ayarlayın
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

// Adres-mektup birleştirmeyi yürüt
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Belgeyi kaydet
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

Bu örnekte, birleştirme alanları içeren bir belge açıyoruz, kullanılmayan alanları kaldırmak için temizleme seçeneklerini ayarlıyoruz ve adres-mektup birleştirmeyi verilerle yürütüyoruz. Birleştirme sonrasında kullanılmayan alanlar belgeden kaldırılacaktır.

## Adım 5: İçeren Alanları Kaldırma

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// İçeren alanları kaldırmak için temizleme seçeneklerini ayarlayın
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

// Adres-mektup birleştirmeyi yürüt
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Belgeyi kaydet
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

Bu örnekte, birleştirme alanlarına sahip bir belge açıyoruz, temizleme seçeneklerini içeren alanları kaldıracak şekilde ayarlıyoruz ve adres-mektup birleştirmeyi verilerle yürütüyoruz. Birleştirmeden sonra alanların kendileri belgeden kaldırılacaktır.

## Adım 6: Boş Tablo Satırlarını Kaldırma

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Boş tablo satırlarını kaldırmak için temizleme seçeneklerini ayarlayın
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

// Adres-mektup birleştirmeyi yürüt
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Belgeyi kaydet
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

Bu örnekte, tablo ve birleştirme alanları içeren bir belge açıyoruz, boş tablo satırlarını kaldırmak için temizleme seçeneklerini ayarlıyoruz ve verilerle adres-mektup birleştirmeyi yürütüyoruz. Birleştirmeden sonra tüm boş tablo satırları belgeden kaldırılacaktır.

## Çözüm

Bu eğitimde, adres-mektup birleştirme işlemi sırasında belgeleri düzenlemek ve temizlemek için Aspose.Words for Java'daki temizleme seçeneklerini nasıl kullanacağınızı öğrendiniz. Bu seçenekler, belge temizleme üzerinde ayrıntılı kontrol sağlayarak, kolaylıkla gösterişli ve özelleştirilmiş belgeler oluşturmanıza olanak tanır.

## SSS'ler

### Aspose.Words for Java'daki temizleme seçenekleri nelerdir?

Aspose.Words for Java'daki temizleme seçenekleri, adres-mektup birleştirme işlemi sırasında belge temizlemenin çeşitli yönlerini kontrol etmenize olanak tanıyan ayarlardır. Boş paragraflar, kullanılmayan bölgeler ve daha fazlası gibi gereksiz öğeleri kaldırmanıza olanak tanıyarak nihai belgenizin iyi yapılandırılmış ve gösterişli olmasını sağlarlar.

### Belgemdeki boş paragrafları nasıl kaldırabilirim?

 Aspose.Words for Java'yı kullanarak belgenizdeki boş paragrafları kaldırmak için,`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS` doğru seçeneği. Bu, içeriği olmayan paragrafları otomatik olarak ortadan kaldırarak daha temiz bir belge elde edilmesini sağlar.

###  Amacı nedir?`REMOVE_UNUSED_REGIONS` cleanup option?

`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS` seçeneği, adres-mektup birleştirme işlemi sırasında bir belgede karşılık gelen verileri olmayan bölgeleri kaldırmak için kullanılır. Kullanılmayan yer tutuculardan kurtularak belgenizi düzenli tutmanıza yardımcı olur.

### Aspose.Words for Java kullanarak boş tablo satırlarını bir belgeden kaldırabilir miyim?

 Evet, boş tablo satırlarını belgeden kaldırabilirsiniz.`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`temizleme seçeneğini true olarak ayarlayın. Bu, veri içermeyen tüm tablo satırlarını otomatik olarak silerek belgenizde iyi yapılandırılmış bir tablo oluşmasını sağlar.

###  Ayarladığımda ne olur?`REMOVE_CONTAINING_FIELDS` option?

 ayarlamak`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS` seçeneği, adres-mektup birleştirme işlemi sırasında, içerdiği paragraf da dahil olmak üzere birleştirme alanının tamamını belgeden kaldıracaktır. Bu, birleştirme alanlarını ve bunlarla ilişkili metinleri ortadan kaldırmak istediğinizde kullanışlıdır.

### Kullanılmayan birleştirme alanlarını belgemden nasıl kaldırabilirim?

 Kullanılmayan birleştirme alanlarını bir belgeden kaldırmak için`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS` doğru seçeneği. Bu, adres-mektup birleştirme sırasında doldurulmayan birleştirme alanlarını otomatik olarak ortadan kaldıracak ve daha temiz bir belge elde edilmesini sağlayacaktır.

###  Arasındaki fark nedir`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

`REMOVE_EMPTY_FIELDS` seçeneği, veri içermeyen veya adres-mektup birleştirme işlemi sırasında boş olan birleştirme alanlarını kaldırır. Öte yandan,`REMOVE_UNUSED_FIELDS`seçeneği, birleştirme sırasında verilerle doldurulmayan birleştirme alanlarını kaldırır. Aralarındaki seçim, içeriği olmayan alanları mı, yoksa belirli birleştirme işleminde kullanılmayan alanları mı kaldırmak istediğinize bağlıdır.

### Noktalama işaretli paragrafların kaldırılmasını nasıl etkinleştirebilirim?

 Noktalama işaretli paragrafların kaldırılmasını etkinleştirmek için`cleanupParagraphsWithPunctuationMarks` seçeneğini true olarak ayarlayın ve temizleme için dikkate alınacak noktalama işaretlerini belirtin. Bu, yalnızca noktalama işaretlerinden oluşan gereksiz paragrafları kaldırarak daha iyileştirilmiş bir belge oluşturmanıza olanak tanır.

### Aspose.Words for Java'daki temizleme seçeneklerini özelleştirebilir miyim?

Evet, temizleme seçeneklerini özel ihtiyaçlarınıza göre özelleştirebilirsiniz. Hangi temizleme seçeneklerinin uygulanacağını seçebilir ve bunları belge temizleme gereksinimlerinize göre yapılandırarak nihai belgenizin istediğiniz standartları karşılamasını sağlayabilirsiniz.