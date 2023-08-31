---
title: Tüm Css Kurallarını Tek Dosyaya Yazın
linktitle: Tüm Css Kurallarını Tek Dosyaya Yazın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile tüm CSS kurallarını tek bir dosyaya yazarak bir Word belgesini sabit HTML'ye nasıl dönüştüreceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Bir C# uygulamasında bir Word belgesini sabit HTML'ye dönüştürürken, daha iyi organizasyon ve taşınabilirlik için tüm CSS kurallarını tek bir dosyada birleştirmek isteyebilirsiniz. .NET için Aspose.Words kütüphanesiyle, HtmlFixedSaveOptions kaydetme seçeneklerini kullanarak bu işlevselliği kolayca belirleyebilirsiniz. Bu adım adım kılavuzda, HtmlFixedSaveOptions kaydetme seçeneklerini kullanarak tüm CSS kurallarını tek bir dosyaya yazarak bir Word belgesini sabit HTML'ye dönüştürmek için Aspose.Words for .NET C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Aspose.Words kütüphanesini anlama

Koda dalmadan önce .NET için Aspose.Words kütüphanesini anlamak önemlidir. Aspose.Words, Word belgelerini .NET dahil farklı platformlarda oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kütüphanedir. Metin ekleme, biçimlendirmeyi değiştirme, bölüm ekleme ve çok daha fazlası gibi belgeleri değiştirmek için birçok özellik sunar.

## Word belgesini yükleme

İlk adım, sabit HTML'ye dönüştürmek istediğiniz Word belgesini yüklemektir. Belgeyi kaynak dosyadan yüklemek için Document sınıfını kullanın. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

Bu örnekte, belgeler dizininde bulunan "Document.docx" belgesini yüklüyoruz.

## Yedekleme seçeneklerini yapılandırma

Bir sonraki adım, sabit HTML'ye dönüştürmek için kaydetme seçeneklerini yapılandırmaktır. Tüm CSS kurallarını tek bir dosyaya yazmak için HtmlFixedSaveOptions sınıfını kullanın ve SaveFontFaceCssSeparately özelliğini false olarak ayarlayın. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Tüm CSS kurallarını tek dosyaya yazmak için yeni bir HtmlFixedSaveOptions nesnesi oluşturup SaveFontFaceCssSeparately özelliğini false olarak ayarlıyoruz.

## Sabit HTML belge dönüşümü

Artık kaydetme seçeneklerini yapılandırdığımıza göre belgeyi sabit HTML'ye dönüştürmeye devam edebiliriz. Kaydetme seçeneklerini belirterek dönüştürülen belgeyi sabit HTML biçiminde kaydetmek için Document sınıfının Kaydet yöntemini kullanın. İşte bir örnek :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

Bu örnekte, dönüştürülen belgeyi belirtilen kaydetme seçeneklerini kullanarak "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" olarak kaydediyoruz.

### Aspose.Words for .NET kullanılarak "Tüm CSS kurallarını tek dosyaya yaz" özelliğine sahip HtmlFixedSaveOptions için örnek kaynak kodu

```csharp
// Belge dizininize erişim yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word belgesini yükleyin
Document doc = new Document(dataDir + "Document.docx");

// "Tüm CSS kurallarını tek dosyaya yaz" özelliğiyle yedekleme seçeneklerini yapılandırın
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Belgeyi sabit HTML'ye dönüştür
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Çözüm

Bu kılavuzda, .NET için Aspose.Words kütüphanesi ile HtmlFixedSaveOptions kullanarak tüm CSS kurallarını tek bir dosyaya yazarak bir Word belgesini sabit HTML'ye nasıl dönüştürebileceğinizi ele aldık. Verilen adımları takip ederek ve verilen C# kaynak kodunu kullanarak bu işlevselliği C# uygulamanıza kolayca uygulayabilirsiniz. Tüm CSS kurallarını tek bir dosyaya yazmak, belge dönüştürme sırasında oluşturulan HTML kodunu düzenlemeyi ve yönetmeyi kolaylaştırır.