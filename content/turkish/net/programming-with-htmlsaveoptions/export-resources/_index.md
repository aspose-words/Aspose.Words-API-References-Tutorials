---
title: Kaynakları Dışa Aktar
linktitle: Kaynakları Dışa Aktar
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerini HTML olarak kaydederken CSS ve yazı tipleri gibi kaynakları nasıl dışa aktaracağınızı öğrenin. Adım adım kılavuzumuzu takip edin.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/export-resources/
---
## giriiş

Merhaba teknoloji meraklısı dostlarım! Word belgelerini HTML'ye dönüştürme ihtiyacı duyduysanız doğru yerdesiniz. Bugün Aspose.Words for .NET'in muhteşem dünyasına dalıyoruz. Bu güçlü kitaplık, Word belgeleriyle programlı olarak çalışmayı kolaylaştırır. Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesini HTML olarak kaydederken yazı tipleri ve CSS gibi kaynakları dışa aktarma adımlarını anlatacağız. Eğlenceli ve bilgilendirici bir yolculuk için kemerlerinizi bağlayın!

## Önkoşullar

Koda dalmadan önce, başlamak için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım. İşte hızlı bir kontrol listesi:

1.  Visual Studio: Makinenizde Visual Studio'nun kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Visual Studio web sitesi](https://visualstudio.microsoft.com/).
2.  Aspose.Words for .NET: Aspose.Words for .NET kitaplığına ihtiyacınız olacak. Henüz almadıysanız, şu adresten ücretsiz deneme sürümünü edinin:[Sürümleri Aspose](https://releases.aspose.com/words/net/) veya adresinden satın alın[Aspose Mağaza](https://purchase.aspose.com/buy).
3. Temel C# Bilgisi: Temel C# anlayışı, kod örneklerini takip etmenize yardımcı olacaktır.

Bunların hepsini anladın mı? Harika! Gerekli ad alanlarını içe aktarmaya geçelim.

## Ad Alanlarını İçe Aktar

Aspose.Words for .NET'i kullanmak için projenize ilgili ad alanlarını eklemeniz gerekir. İşte bunu nasıl yapacağınız:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Bu ad alanları, eğitimimizde kullanacağımız Aspose.Words sınıflarına ve yöntemlerine erişim için çok önemlidir.

Bir Word belgesini HTML olarak kaydederken kaynakları dışa aktarma sürecini inceleyelim. Takip edilmesi kolay olsun diye adım adım ilerleyeceğiz.

## 1. Adım: Belge Dizininizi Kurun

Öncelikle belgeler dizininizin yolunu belirtmeniz gerekir. Burası Word belgenizin bulunduğu ve HTML dosyasının kaydedileceği yerdir.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` Dizininizin gerçek yolu ile.

## Adım 2: Word Belgesini Yükleyin

 Daha sonra HTML'ye dönüştürmek istediğiniz Word belgesini yükleyelim. Bu eğitim için adlı bir belge kullanacağız.`Rendering.docx`.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Bu kod satırı belgeyi belirtilen dizinden yükler.

## 3. Adım: HTML Kaydetme Seçeneklerini Yapılandırın

CSS ve yazı tipleri gibi kaynakları dışa aktarmak için`HtmlSaveOptions`. Bu adım, HTML çıktınızın iyi yapılandırılmış olmasını ve gerekli kaynakları içermesini sağlamak için çok önemlidir.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ResourceFolder = dataDir + "Resources",
    ResourceFolderAlias = "http://example.com/resources"
};
```

Her seçeneğin ne işe yaradığını inceleyelim:
- `CssStyleSheetType = CssStyleSheetType.External`: Bu seçenek, CSS stillerinin harici bir stil sayfasına kaydedilmesi gerektiğini belirtir.
- `ExportFontResources = true`: Bu, yazı tipi kaynaklarının dışa aktarılmasını sağlar.
- `ResourceFolder = dataDir + "Resources"`: Kaynakların (yazı tipleri ve CSS dosyaları gibi) kaydedileceği yerel klasörü belirtir.
- `ResourceFolderAlias = "http://example.com/resources"`: Kaynak klasörü için HTML dosyasında kullanılacak bir takma ad ayarlar.

## Adım 4: Belgeyi HTML olarak kaydedin

Kaydetme seçenekleri yapılandırıldığında son adım, belgeyi bir HTML dosyası olarak kaydetmektir. İşte bunu nasıl yapacağınız:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Bu kod satırı, belgeyi dışa aktarılan kaynaklarla birlikte HTML biçiminde kaydeder.

## Çözüm

İşte buyur! Aspose.Words for .NET kullanarak bir Word belgesini HTML olarak kaydederken kaynakları başarıyla dışa aktardınız. Bu güçlü kitaplık sayesinde Word belgelerinin programlı olarak işlenmesi çocuk oyuncağı haline gelir. İster bir web uygulaması üzerinde çalışıyor olun, ister yalnızca çevrimdışı kullanım için belgeleri dönüştürmeniz gerekiyor olsun, Aspose.Words size yardımcı olacaktır.

## SSS'ler

### Görselleri yazı tipleri ve CSS ile birlikte dışa aktarabilir miyim?
 Evet yapabilirsin! Aspose.Words for .NET görüntülerin dışa aktarılmasını da destekler. Sadece yapılandırdığınızdan emin olun.`HtmlSaveOptions` buna göre.

### Harici bir stil sayfası kullanmak yerine CSS'yi yerleştirmenin bir yolu var mı?
 Kesinlikle. Ayarlayabilirsiniz`CssStyleSheetType` ile`CssStyleSheetType.Embedded` gömülü stilleri tercih ediyorsanız.

### Çıktı HTML dosyasının adını nasıl özelleştirebilirim?
 İstediğiniz herhangi bir dosya adını belirtebilirsiniz.`doc.Save` yöntem. Örneğin,`doc.Save(dataDir + "CustomFileName.html", saveOptions);`.

### Aspose.Words HTML dışında diğer formatları da destekliyor mu?
 Evet, PDF, DOCX, TXT ve daha fazlasını içeren çeşitli formatları destekler. Kontrol et[dokümantasyon](https://reference.aspose.com/words/net/) tam liste için.

### Daha fazla desteği ve kaynağı nereden alabilirim?
Daha fazla yardım için şu adresi ziyaret edin:[Aspose.Words Destek Forumu](https://forum.aspose.com/c/words/8) . Ayrıca ayrıntılı belgeleri ve örnekleri de şu adreste bulabilirsiniz:[Web sitesi](https://reference.aspose.com/words/net/).