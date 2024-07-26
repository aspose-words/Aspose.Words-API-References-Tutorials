---
title: Aspose.Words for Java'da Üstbilgi ve Altbilgileri Kullanma
linktitle: Üstbilgileri ve Altbilgileri Kullanma
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'da üstbilgi ve altbilgilerin nasıl kullanılacağını adım adım öğrenin. Zahmetsizce profesyonel belgeler oluşturun.
type: docs
weight: 16
url: /tr/java/using-document-elements/using-headers-and-footers/
---

Bu kapsamlı kılavuzda Aspose.Words for Java'da üstbilgiler ve altbilgilerle çalışma sürecinde size yol göstereceğiz. Üstbilgiler ve altbilgiler belge formatlamanın temel öğeleridir ve Aspose.Words bunları ihtiyaçlarınıza göre oluşturup özelleştirmeniz için güçlü araçlar sağlar.

Şimdi bu adımların her birine ayrıntılı olarak bakalım.

## 1. Aspose.Words'e Giriş

Aspose.Words, Word belgelerini programlı olarak oluşturmanıza, değiştirmenize ve işlemenize olanak tanıyan güçlü bir Java API'sidir. Üstbilgiler ve altbilgiler de dahil olmak üzere belge biçimlendirmesi için kapsamlı özellikler sağlar.

## 2. Java Ortamınızı Kurma

 Aspose.Words'ü kullanmaya başlamadan önce Java geliştirme ortamınızın doğru şekilde kurulduğundan emin olun. Gerekli kurulum talimatlarını Aspose.Words dokümantasyon sayfasında bulabilirsiniz:[Aspose.Words Java Belgeleri](https://reference.aspose.com/words/java/).

## 3. Yeni Bir Belge Oluşturma

Üstbilgiler ve altbilgilerle çalışmak için Aspose.Words'ü kullanarak yeni bir belge oluşturmanız gerekir. Aşağıdaki kod bunun nasıl yapılacağını gösterir:

```java
// Yeni bir belge oluşturmak için Java kodu
string dataDir = "Your Document Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 4. Sayfa Yapısını Anlamak

 Sayfa düzeni, belgenizin düzenini kontrol etmek için çok önemlidir. Üstbilgiler ve altbilgilerle ilgili çeşitli özellikleri aşağıdakileri kullanarak belirtebilirsiniz:`PageSetup` sınıf. Örneğin:

```java
// Sayfa özelliklerini ayarlama
Section currentSection = builder.getCurrentSection();
PageSetup pageSetup = currentSection.getPageSetup();
pageSetup.setDifferentFirstPageHeaderFooter(true);
pageSetup.setHeaderDistance(20.0);
```

## 5. Farklı İlk Sayfa Üstbilgisi/Altbilgisi

Aspose.Words, belgenizin ilk sayfası için farklı üstbilgi ve altbilgilere sahip olmanızı sağlar. Kullanmak`pageSetup.setDifferentFirstPageHeaderFooter(true);` Bu özelliği etkinleştirmek için.

## 6. Başlıklarla Çalışmak

### 6.1. Başlıklara Metin Eklemek

 kullanarak başlıklara metin ekleyebilirsiniz.`DocumentBuilder`. İşte bir örnek:

```java
// İlk sayfa başlığına metin ekleme
builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.getFont().setName("Arial");
builder.getFont().setBold(true);
builder.getFont().setSize(14.0);
builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

### 6.2. Başlıklara Resim Ekleme

 Başlıklara resim eklemek için şunu kullanabilirsiniz:`insertImage` yöntem. İşte bir örnek:

```java
// Başlığa resim ekleme
builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
    RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
```

### 6.3. Başlık Stillerini Özelleştirme

Yukarıdaki örneklerde gösterildiği gibi yazı tipi, hizalama ve daha fazlası gibi çeşitli özellikleri ayarlayarak başlık stillerini özelleştirebilirsiniz.

## 7. Alt Bilgilerle Çalışmak

### 7.1. Altbilgilere Metin Ekleme

 Başlıklara benzer şekilde altbilgilere de metin ekleyebilirsiniz.`DocumentBuilder`. İşte bir örnek:

```java
// Birincil altbilgiye metin ekleme
builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
// Gerektiğinde metin ve alanlar ekleyin
```

### 7.2. Altbilgilere Görüntü Ekleme

 Altbilgilere resim eklemek için şunu kullanın:`insertImage` yöntem, tıpkı başlıklarda olduğu gibi.

### 7.3. Alt Bilgi Stillerini Özelleştirme

 Altbilgi stillerini kullanarak özelleştirin`DocumentBuilder`başlıkları özelleştirmeye benzer.

## 8. Sayfa Numaralandırma

 Gibi alanları kullanarak üstbilgilerinize ve altbilgilerinize sayfa numaraları ekleyebilirsiniz.`PAGE`Ve`NUMPAGES`. Bu alanlar siz sayfa ekledikçe veya çıkardıkça otomatik olarak güncellenir.

## 9. Alt Bilgilerdeki Telif Hakkı Bilgileri

Belgenizin alt bilgisine telif hakkı bilgisi eklemek için, kod parçacığında gösterildiği gibi biri sola, diğeri sağa hizalanan iki hücreli bir tablo kullanabilirsiniz.

## 10. Çoklu Bölümlerle Çalışmak

Aspose.Words bir belgede birden fazla bölümle çalışmanıza olanak tanır. Her bölüm için farklı sayfa düzenleri ve üstbilgi/altbilgiler ayarlayabilirsiniz.

## 11. Peyzaj Yönü

Gerekirse belirli bölümlerin yönünü yatay moda değiştirebilirsiniz.

## 12. Önceki Bölümlerden Üstbilgi/Altbilgi Kopyalama

Önceki bölümlerdeki üstbilgileri ve altbilgileri kopyalamak, karmaşık belgeler oluştururken zaman kazandırabilir.

## 13. Belgenizi Kaydetmek

Belgenizi oluşturup özelleştirdikten sonra, onu kullanarak kaydetmeyi unutmayın.`doc.save()` yöntem.

## Kaynak Kodunu Tamamlayın
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Section currentSection = builder.getCurrentSection();
        PageSetup pageSetup = currentSection.getPageSetup();
        // İlk sayfanın üstbilgilerinin/altbilgilerinin diğer sayfalardan farklı olmasını isteyip istemediğimizi belirtin.
        // Ayrıca belirtmek için PageSetup.OddAndEvenPagesHeaderFooter özelliğini de kullanabilirsiniz.
        // tek ve çift sayfalar için farklı üstbilgiler/altbilgiler.
        pageSetup.setDifferentFirstPageHeaderFooter(true);
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
        builder.getFont().setName("Arial");
        builder.getFont().setBold(true);
        builder.getFont().setSize(14.0);
        builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY);
        // Üstbilginin üst/sol köşesine konumlandırılmış bir resim ekleyin.
        // Sayfanın üst/sol kenarlarına olan mesafe 10 noktaya ayarlanmıştır.
        builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
            RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.write("Aspose.Words Header/Footer Creation Primer.");
        builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
        // Satırdaki metnin bir bölümünü (sayfa numaralandırmayla) yapmak için iki hücreli bir tablo kullanıyoruz.
        // Sola hizalanacak ve metnin diğer kısmı (telif hakkıyla birlikte) sağa hizalanacak.
        builder.startTable();
        builder.getCellFormat().clearFormatting();
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        // Geçerli sayfa numarasını ve birçok sayfayı otomatik olarak hesaplamak için PAGE ve NUMPAGES alanlarını kullanır.
        builder.write("Page ");
        builder.insertField("PAGE", "");
        builder.write(" of ");
        builder.insertField("NUMPAGES", "");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.LEFT);
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        builder.write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.endRow();
        builder.endTable();
        builder.moveToDocumentEnd();
        // Birincil üstbilgilerin/altbilgilerin görüneceği ikinci bir sayfa oluşturmak için sayfa sonu yapın.
        builder.insertBreak(BreakType.PAGE_BREAK);
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        currentSection = builder.getCurrentSection();
        pageSetup = currentSection.getPageSetup();
        pageSetup.setOrientation(Orientation.LANDSCAPE);
        // Bu bölümün farklı bir ilk sayfa üstbilgisine/altbilgisine ihtiyacı yoktur, belgede yalnızca bir başlık sayfasına ihtiyacımız vardır.
        //ve bu sayfanın üstbilgisi/altbilgisi önceki bölümde zaten tanımlanmıştı.
        pageSetup.setDifferentFirstPageHeaderFooter(false);
        // Bu bölümde önceki bölümdeki üstbilgiler/altbilgiler görüntülenir
        // Bu sayfa genişliğini iptal etmek için varsayılan olarak currentSection.HeadersFooters.LinkToPrecious(false) öğesini çağırın
        // yeni bölüm için farklıdır ve bu nedenle altbilgi tablosu için farklı hücre genişlikleri ayarlamamız gerekir.
        currentSection.getHeadersFooters().linkToPrevious(false);
        // Bu bölüm için zaten var olan üstbilgi/altbilgi setini kullanmak istiyorsak.
        // Ancak bazı küçük değişikliklerle üstbilgileri/altbilgileri kopyalamak uygun olabilir
        // önceki bölümden ve gerekli değişiklikleri istediğimiz yere uygulayın.
        copyHeadersFootersFromPreviousSection(currentSection);
        HeaderFooter primaryFooter = currentSection.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
        Row row = primaryFooter.getTables().get(0).getFirstRow();
        row.getFirstCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        row.getLastCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        doc.save("Your Directory Path" + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```	
copyHeadersFootersFromPreciousSection yönteminin kaynak kodu
```java
    /// <özet>
    /// Önceki bölümdeki üstbilgileri/altbilgileri belirtilen bölüme kopyalar ve kopyalar.
    /// </özet>
    private void copyHeadersFootersFromPreviousSection(Section section)
    {
        Section previousSection = (Section)section.getPreviousSibling();
        if (previousSection == null)
            return;
        section.getHeadersFooters().clear();
        for (HeaderFooter headerFooter : (Iterable<HeaderFooter>) previousSection.getHeadersFooters())
            section.getHeadersFooters().add(headerFooter.deepClone(true));
	}
```

## Çözüm

Bu eğitimde Aspose.Words for Java'da üstbilgi ve altbilgilerle çalışmanın temellerini ele aldık. Üstbilgi ve altbilgilerin nasıl oluşturulacağını, özelleştirileceğini ve stillendirileceğinin yanı sıra diğer önemli belge biçimlendirme tekniklerini de öğrendiniz.

 Daha fazla ayrıntı ve gelişmiş özellikler için bkz.[Aspose.Words Java Belgeleri](https://reference.aspose.com/words/java/).

## SSS

### 1. Belgemin altbilgisine sayfa numaralarını nasıl ekleyebilirim?
 Sayfa numaralarını ekleyerek ekleyebilirsiniz.`PAGE` Aspose.Words kullanarak altbilgi alanına girin.

### 2. Aspose.Words Java geliştirme ortamlarıyla uyumlu mu?
Evet, Aspose.Words Java geliştirme desteği sağlar. Gerekli kurulumun yapıldığından emin olun.

### 3. Üstbilgi ve altbilgilerin yazı tipini ve stilini özelleştirebilir miyim?
Üstbilgilerinizi ve altbilgilerinizi görsel olarak çekici hale getirmek için kesinlikle yazı tiplerini, hizalamayı ve diğer stilleri özelleştirebilirsiniz.

### 4. Tek ve çift sayfalar için farklı başlıklara sahip olmak mümkün müdür?
 Evet, kullanabilirsin`PageSetup.OddAndEvenPagesHeaderFooter` Tek ve çift sayfalar için farklı başlıklar belirtmek için.

### 5. Aspose.Words for Java'yı kullanmaya nasıl başlayabilirim?
 Başlamak için şu adresi ziyaret edin:[Aspose.Words Java Belgeleri](https://reference.aspose.com/words/java/) API'nin kullanımına ilişkin kapsamlı rehberlik için.