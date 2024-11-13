---
title: Aspose.Words Java ile Gelişmiş HTML Belgeleri Kaydetme Seçenekleri
linktitle: HTML Belgelerini Kaydetme
second_title: Aspose.Words Java Belge İşleme API'si
description: Bu eğitimde, Java için Aspose.Words ile çeşitli gelişmiş HTML belge kaydetme seçeneklerini ele aldık. Bu seçenekler, yüksek kaliteli HTML oluşturmanıza olanak tanır
type: docs
weight: 16
url: /tr/java/document-loading-and-saving/advance-html-documents-saving-options/
---

Bu eğitimde, Aspose.Words for Java tarafından sağlanan gelişmiş HTML belge kaydetme seçeneklerini inceleyeceğiz. Aspose.Words, Word belgeleriyle çalışmak için güçlü bir Java API'sidir ve belge düzenleme ve dönüştürme için çok çeşitli özellikler sunar.

## 1. Giriş
Java için Aspose.Words, Word belgeleriyle programatik olarak çalışmanıza olanak tanır. Bu eğitimde, Word belgelerinin HTML'ye nasıl dönüştürüleceğini kontrol etmenizi sağlayan gelişmiş HTML belge kaydetme seçeneklerine odaklanacağız.

## 2. Gidiş-Dönüş Bilgilerini Dışa Aktar
The`exportRoundtripInformation` yöntem, gidiş-dönüş bilgilerini koruyarak Word belgelerini HTML'ye aktarmanıza olanak tanır. Bu bilgiler, belgeye özgü hiçbir ayrıntıyı kaybetmeden HTML'yi Word biçimine geri dönüştürmek istediğinizde yararlı olabilir.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Yazı Tiplerini Base64 Olarak Dışa Aktar
 İle`exportFontsAsBase64` yöntemiyle, belgede kullanılan yazı tiplerini HTML'de Base64 kodlu veri olarak dışa aktarabilirsiniz. Bu, HTML gösteriminin orijinal Word belgesiyle aynı yazı tipi stillerini korumasını sağlar.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Kaynakları İhracat Etmek
The`exportResources` yöntemi, CSS stil sayfasının türünü belirtmenize ve yazı tipi kaynaklarını dışa aktarmanıza olanak tanır. Ayrıca HTML'de kaynaklar için bir kaynak klasörü ve bir takma ad da ayarlayabilirsiniz.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/kaynaklar");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Meta Dosyalarını EMF veya WMF'ye Dönüştürün
The`convertMetafilesToEmfOrWmf`Bu yöntem, belgedeki meta dosyalarını EMF veya WMF biçimine dönüştürmenize olanak tanır ve HTML'de uyumluluğu ve düzgün işlemeyi garanti eder.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Kısalık amacıyla kod parçacığı gösterilmiyor.
}
```

## 6. Meta Dosyalarını SVG'ye Dönüştürün
 Kullanın`convertMetafilesToSvg` meta dosyalarını SVG formatına dönüştürme yöntemi. Bu format, HTML belgelerinde vektör grafiklerini görüntülemek için idealdir.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Kısalık amacıyla kod parçacığı gösterilmiyor.
}
```

## 7. CSS Sınıf Adı Önekini Ekleyin
 İle`addCssClassNamePrefix` yöntemi, dışa aktarılan HTML'deki CSS sınıf adlarına bir önek ekleyebilirsiniz. Bu, mevcut stillerle çakışmaları önlemeye yardımcı olur.

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. MHTML Kaynakları için CID URL'lerini dışa aktarın
The`exportCidUrlsForMhtmlResources` yöntem, belgeleri MHTML biçiminde kaydederken kullanılır. Kaynaklar için İçerik Kimliği URL'lerinin dışa aktarılmasına izin verir.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Kısalık amacıyla kod parçacığı gösterilmiyor.
}
```

## 9. Yazı Tipi Adlarını Çöz
The`resolveFontNames` Bu yöntem, belgeleri HTML formatında kaydederken yazı tipi adlarının çözümlenmesine yardımcı olur ve farklı platformlarda tutarlı bir görüntüleme sağlar.

```java
@Test
public void resolveFontNames() throws Exception {
    // Kısalık amacıyla kod parçacığı gösterilmiyor.
}
```

## 10. Metin Giriş Formu Alanını Metin Olarak Dışa Aktar
The`exportTextInputFormFieldAsText` method form alanlarını HTML'de düz metin olarak dışa aktarır, böylece kolayca okunabilir ve düzenlenebilir hale gelir.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Kısalık amacıyla kod parçacığı gösterilmiyor.
}
```

## 11. Sonuç
Bu eğitimde, Aspose.Words for Java tarafından sağlanan gelişmiş HTML belge kaydetme seçeneklerini inceledik. Bu seçenekler, dönüştürme süreci üzerinde ayrıntılı kontrol sağlayarak orijinal Word belgelerine oldukça benzeyen HTML belgeleri oluşturmanıza olanak tanır.

## 12. SSS
Aspose.Words for Java ve HTML belge kaydetme seçenekleriyle ilgili sık sorulan sorulardan bazıları şunlardır:

### S1: Aspose.Words for Java kullanarak HTML'yi Word formatına nasıl geri dönüştürebilirim?
 HTML'yi Word biçimine geri dönüştürmek için Aspose.Words API'lerini kullanabilirsiniz`load` HTML belgesini yükleme ve ardından Word formatında kaydetme yöntemi.

### S2: HTML'e aktarırken CSS stillerini özelleştirebilir miyim?
 Evet, HTML'de kullanılan stil sayfalarını değiştirerek veya CSS stillerini özelleştirebilirsiniz.`addCssClassNamePrefix` CSS sınıf adlarına önek ekleme yöntemi.

### S3: HTML çıktısını web gösterimi için optimize etmenin bir yolu var mı?
Evet, fontları Base64 olarak dışa aktarma ve meta dosyalarını SVG'ye dönüştürme gibi seçenekleri yapılandırarak HTML çıktısını web gösterimi için optimize edebilirsiniz.

### S4: Karmaşık Word belgelerini HTML'ye dönüştürürken herhangi bir sınırlama var mı?
Aspose.Words for Java güçlü dönüştürme yetenekleri sağlasa da, karmaşık düzenlere sahip karmaşık Word belgelerinin istenen HTML çıktısını elde etmek için ek son işleme tabi tutulması gerekebilir.
