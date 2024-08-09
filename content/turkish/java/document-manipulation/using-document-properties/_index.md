---
title: Aspose.Words for Java'da Belge Özelliklerini Kullanma
linktitle: Belge Özelliklerini Kullanma
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java ile belge yönetimini optimize edin. Bu kapsamlı eğitimde belge özellikleriyle çalışmayı, özel meta veriler eklemeyi ve daha fazlasını öğrenin.
type: docs
weight: 32
url: /tr/java/document-manipulation/using-document-properties/
---

## Belge Özelliklerine Giriş

Belge özellikleri herhangi bir belgenin hayati bir parçasıdır. Belgenin kendisi hakkında başlığı, yazarı, konusu, anahtar sözcükleri ve daha fazlası gibi ek bilgiler sağlarlar. Aspose.Words for Java'da hem yerleşik hem de özel belge özelliklerini değiştirebilirsiniz.

## Belge Özelliklerini Numaralandırma

### Yerleşik Özellikler

Yerleşik belge özelliklerini almak ve bunlarla çalışmak için aşağıdaki kod parçacığını kullanabilirsiniz:

```java
@Test
public void enumerateProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    System.out.println(MessageFormat.format("1. Document name: {0}", doc.getOriginalFileName()));
    System.out.println("2. Built-in Properties");
    for (DocumentProperty prop : doc.getBuiltInDocumentProperties())
        System.out.println(MessageFormat.format("{0} : {1}", prop.getName(), prop.getValue()));
}
```

Bu kod, belgenin adını ve "Başlık", "Yazar" ve "Anahtar Kelimeler" gibi özellikler de dahil olmak üzere yerleşik özelliklerini görüntüler.

### Özel Özellikler

Özel belge özellikleriyle çalışmak için aşağıdaki kod parçacığını kullanabilirsiniz:

```java
@Test
public void addCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    CustomDocumentProperties customDocumentProperties = doc.getCustomDocumentProperties();

    if (customDocumentProperties.get("Authorized") != null) return;

    customDocumentProperties.add("Authorized", true);
    customDocumentProperties.add("Authorized By", "John Smith");
    customDocumentProperties.add("Authorized Date", new Date());
    customDocumentProperties.add("Authorized Revision", doc.getBuiltInDocumentProperties().getRevisionNumber());
    customDocumentProperties.add("Authorized Amount", 123.45);
}
```

Bu kod parçacığı, bir boolean değeri, bir dize, bir tarih, bir revizyon numarası ve bir sayısal değer dahil olmak üzere özel belge özelliklerinin nasıl ekleneceğini gösterir.

## Belge Özelliklerini Kaldırma

Belirli belge özelliklerini kaldırmak için aşağıdaki kodu kullanabilirsiniz:

```java
@Test
public void removeCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    doc.getCustomDocumentProperties().remove("Authorized Date");
}
```

Bu kod, "Yetkili Tarih" özel özelliğini belgeden kaldırır.

## İçeriğe Bağlantıyı Yapılandırma

Bazı durumlarda belgenizin içinde bağlantılar oluşturmak isteyebilirsiniz. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```java
@Test
public void configuringLinkToContent() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.startBookmark("MyBookmark");
    builder.writeln("Text inside a bookmark.");
    builder.endBookmark("MyBookmark");

    CustomDocumentProperties customProperties = doc.getCustomDocumentProperties();

    // İçerik özelliğine bağlı ekleyin.
    DocumentProperty customProperty = customProperties.addLinkToContent("Bookmark", "MyBookmark");
    customProperty = customProperties.get("Bookmark");
    boolean isLinkedToContent = customProperty.isLinkToContent();
    String linkSource = customProperty.getLinkSource();
    String customPropertyValue = customProperty.getValue().toString();
}
```

Bu kod parçacığı, belgenizde nasıl yer işareti oluşturulacağını ve bu yer işaretine bağlantı veren özel bir belge özelliğinin nasıl ekleneceğini gösterir.

## Ölçü Birimleri Arasında Dönüştürme

Aspose.Words for Java'da ölçü birimlerini kolaylıkla dönüştürebilirsiniz. İşte bunun nasıl yapılacağına dair bir örnek:

```java
@Test
public void convertBetweenMeasurementUnits() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    PageSetup pageSetup = builder.getPageSetup();

    // Kenar boşluklarını inç cinsinden ayarlayın.
    pageSetup.setTopMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setBottomMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setLeftMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setRightMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setHeaderDistance(ConvertUtil.inchToPoint(0.2));
    pageSetup.setFooterDistance(ConvertUtil.inchToPoint(0.2));
}
```

Bu kod parçacığı, çeşitli kenar boşluklarını ve mesafeleri noktalara dönüştürerek inç cinsinden ayarlar.

## Kontrol Karakterlerini Kullanma

Kontrol karakterleri metinle uğraşırken yararlı olabilir. Metninizdeki bir kontrol karakterini nasıl değiştireceğiniz aşağıda açıklanmıştır:

```java
@Test
public void useControlCharacters()
{
    final String TEXT = "test\r";

    // "\r" kontrol karakterini "\r\n" ile değiştirin.
    String replace = TEXT.replace(ControlChar.CR, ControlChar.CR_LF);
}
```

Bu örnekte satırbaşını değiştiriyoruz (`\r`) satır başı ve ardından satır besleme (`\r\n`).

## Çözüm

Belge özellikleri, Aspose.Words for Java'da belgelerinizi etkili bir şekilde yönetmede ve organize etmede önemli bir rol oynar. Yerleşik özelliklerle, özel özelliklerle veya kontrol karakterleriyle çalışmak olsun, belge yönetimi yeteneklerinizi geliştirmek için emrinizde bir dizi araç vardır.

## SSS'ler

### Yerleşik belge özelliklerine nasıl erişebilirim?

 Aspose.Words for Java'daki yerleşik belge özelliklerine erişmek için`getBuiltInDocumentProperties` konusundaki yöntem`Document` nesne. Bu yöntem, yineleyebileceğiniz yerleşik özelliklerin bir koleksiyonunu döndürür.

### Bir belgeye özel belge özellikleri ekleyebilir miyim?

 Evet, kullanarak bir belgeye özel belge özellikleri ekleyebilirsiniz.`CustomDocumentProperties` koleksiyon. Dizeler, boolean'lar, tarihler ve sayısal değerler dahil olmak üzere çeşitli veri türleriyle özel özellikler tanımlayabilirsiniz.

### Belirli bir özel belge özelliğini nasıl kaldırabilirim?

 Belirli bir özel belge özelliğini kaldırmak için`remove` konusundaki yöntem`CustomDocumentProperties`koleksiyonu, kaldırmak istediğiniz özelliğin adını parametre olarak iletin.

### Bir belge içindeki içeriğe bağlantı vermenin amacı nedir?

Bir belge içindeki içeriğe bağlantı vermek, belgenin belirli bölümlerine dinamik referanslar oluşturmanıza olanak tanır. Bu, etkileşimli belgeler oluşturmak veya bölümler arasında çapraz referanslar oluşturmak için yararlı olabilir.

### Aspose.Words for Java'da farklı ölçü birimleri arasında nasıl dönüşüm yapabilirim?

 Aspose.Words for Java'da farklı ölçü birimleri arasında dönüşüm yapabilirsiniz.`ConvertUtil` sınıf. İnç gibi birimleri noktaya, noktaları santimetreye ve daha fazlasına dönüştürme yöntemleri sağlar.