---
title: Aspose.Words Java ile Gelişmiş HTML Belgelerini Kaydetme Seçenekleri
linktitle: HTML Belgelerini şununla kaydetme
second_title: Aspose.Words Java Belge İşleme API'si
description: Bu eğitimde Aspose.Words for Java ile çeşitli gelişmiş HTML belgesi kaydetme seçeneklerini ele aldık. Bu seçenekler yüksek kaliteli HTML oluşturmanıza olanak sağlar
type: docs
weight: 16
url: /tr/java/document-loading-and-saving/advance-html-documents-saving-options/
---

Bu eğitimde Aspose.Words for Java tarafından sağlanan gelişmiş HTML belgesi kaydetme seçeneklerini inceleyeceğiz. Aspose.Words, Word belgeleriyle çalışmak için güçlü bir Java API'sidir ve belge işleme ve dönüştürme için çok çeşitli özellikler sunar.

## 1. Giriş
Aspose.Words for Java, Word belgeleriyle programlı olarak çalışmanıza olanak tanır. Bu eğitimde, Word belgelerinin HTML'ye nasıl dönüştürüleceğini kontrol etmenizi sağlayan gelişmiş HTML belgesi kaydetme seçeneklerine odaklanacağız.

## 2. Gidiş-Dönüş Bilgilerini Dışa Aktarın
`exportRoundtripInformation` yöntemi, gidiş dönüş bilgilerini korurken Word belgelerini HTML'ye aktarmanıza olanak tanır. Bu bilgi, belgeye özgü ayrıntıları kaybetmeden HTML'yi tekrar Word biçimine dönüştürmek istediğinizde yararlı olabilir.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Yazı Tiplerini Base64 Olarak Dışa Aktarın
 İle`exportFontsAsBase64` yöntemiyle, belgede kullanılan yazı tiplerini HTML'de Base64 kodlu veriler olarak dışa aktarabilirsiniz. Bu, HTML gösteriminin orijinal Word belgesiyle aynı yazı tipi stillerini korumasını sağlar.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Kaynakları Dışa Aktarın
`exportResources` yöntemi, CSS stil sayfasının türünü belirtmenize ve yazı tipi kaynaklarını dışa aktarmanıza olanak tanır. Ayrıca HTML'deki kaynaklar için bir kaynak klasörü ve takma ad da ayarlayabilirsiniz.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Meta Dosyalarını EMF veya WMF'ye Dönüştürün
`convertMetafilesToEmfOrWmf`yöntemi, belgedeki meta dosyalarını EMF veya WMF biçimine dönüştürmenize olanak tanıyarak HTML'de uyumluluk ve düzgün görüntü oluşturma sağlar.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Kısa olması açısından kod pasajı gösterilmemiştir.
}
```

## 6. Meta Dosyalarını SVG'ye Dönüştürün
 Kullan`convertMetafilesToSvg` Meta dosyalarını SVG formatına dönüştürme yöntemi. Bu format, HTML belgelerinde vektör grafiklerini görüntülemek için idealdir.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Kısa olması açısından kod pasajı gösterilmemiştir.
}
```

## 7. CSS Sınıfı Adı Öneki Ekle
 İle`addCssClassNamePrefix` yöntemini kullanarak, dışa aktarılan HTML'deki CSS sınıfı adlarına bir önek ekleyebilirsiniz. Bu, mevcut stillerle çakışmaları önlemeye yardımcı olur.

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
`exportCidUrlsForMhtmlResources` Belgeleri MHTML formatında kaydederken yöntem kullanılır. Kaynaklar için Content-ID URL'lerinin dışa aktarılmasına olanak tanır.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Kısa olması açısından kod pasajı gösterilmemiştir.
}
```

## 9. Yazı Tipi Adlarını Çözümleyin
`resolveFontNames` yöntemi, belgeleri HTML biçiminde kaydederken yazı tipi adlarının çözümlenmesine yardımcı olarak farklı platformlarda tutarlı görüntü oluşturmayı sağlar.

```java
@Test
public void resolveFontNames() throws Exception {
    // Kısa olması açısından kod pasajı gösterilmemiştir.
}
```

## 10. Metin Giriş Formu Alanını Metin Olarak Dışa Aktar
`exportTextInputFormFieldAsText` yöntem, form alanlarını HTML'de düz metin olarak dışa aktararak onları kolayca okunabilir ve düzenlenebilir hale getirir.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Kısa olması açısından kod pasajı gösterilmemiştir.
}
```

## 11. Sonuç
Bu eğitimde Aspose.Words for Java tarafından sağlanan gelişmiş HTML belgesi kaydetme seçeneklerini inceledik. Bu seçenekler size dönüştürme süreci üzerinde ayrıntılı kontrol sağlayarak orijinal Word belgelerine çok benzeyen HTML belgeleri oluşturmanıza olanak tanır.

## 12. SSS
Aspose.Words for Java ve HTML belge kaydetme seçenekleriyle çalışmaya ilişkin sık sorulan sorulardan bazıları şunlardır:

### S1: Aspose.Words for Java'yı kullanarak HTML'yi Word formatına nasıl dönüştürebilirim?
 HTML'yi tekrar Word formatına dönüştürmek için Aspose.Words API'sini kullanabilirsiniz.`load` HTML belgesini yükleme ve ardından Word formatında kaydetme yöntemini kullanın.

### S2: HTML'ye dışa aktarırken CSS stillerini özelleştirebilir miyim?
 Evet, HTML'de kullanılan stil sayfalarını değiştirerek veya CSS stillerini özelleştirebilirsiniz.`addCssClassNamePrefix` CSS sınıfı adlarına önek ekleme yöntemi.

### S3: Web gösterimi için HTML çıktısını optimize etmenin bir yolu var mı?
Evet, yazı tiplerini Base64 olarak dışa aktarma ve meta dosyaları SVG'ye dönüştürme gibi seçenekleri yapılandırarak HTML çıktısını web görüntüsü için optimize edebilirsiniz.

### S4: Karmaşık Word belgelerini HTML'ye dönüştürürken herhangi bir sınırlama var mı?
Aspose.Words for Java güçlü dönüştürme yetenekleri sağlarken, karmaşık düzenlere sahip karmaşık Word belgeleri, istenen HTML çıktısını elde etmek için ek son işlemler gerektirebilir.
