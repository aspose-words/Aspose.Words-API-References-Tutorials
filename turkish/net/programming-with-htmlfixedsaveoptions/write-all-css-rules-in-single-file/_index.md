---
title: Tüm Css Kurallarını Tek Dosyaya Yazın
linktitle: Tüm Css Kurallarını Tek Dosyaya Yazın
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile tüm CSS kurallarını tek bir dosyaya yazarak bir Word belgesini sabit HTML'ye nasıl dönüştüreceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Bir C# uygulamasında bir Word belgesini sabit HTML'ye dönüştürürken, daha iyi organizasyon ve taşınabilirlik için tüm CSS kurallarını tek bir dosyada birleştirmek isteyebilirsiniz. .NET için Aspose.Words kitaplığıyla, HtmlFixedSaveOptions kaydetme seçeneklerini kullanarak bu işlevselliği kolayca belirleyebilirsiniz. Bu adım adım kılavuzda, HtmlFixedSaveOptions kaydetme seçeneklerini kullanarak tüm CSS kurallarını tek bir dosyaya yazarak bir Word belgesini sabit HTML'ye dönüştürmek için Aspose.Words for .NET C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, .NET dahil olmak üzere farklı platformlarda Word belgeleri oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kitaplıktır. Belgeleri işlemek için metin ekleme, biçimlendirmeyi değiştirme, bölümler ekleme ve çok daha fazlası gibi birçok özellik sunar.

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

Yeni bir HtmlFixedSaveOptions nesnesi oluşturuyoruz ve tüm CSS kurallarını tek bir dosyaya yazmak için SaveFontFaceCssSeparately özelliğini false olarak ayarlıyoruz.

## Sabit HTML belgesi dönüştürme

Artık kaydetme seçeneklerini yapılandırdığımıza göre, belgeyi sabit HTML'ye dönüştürmeye devam edebiliriz. Kaydetme seçeneklerini belirterek dönüştürülen belgeyi sabit HTML biçiminde kaydetmek için Document sınıfının Save yöntemini kullanın. İşte bir örnek :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

Bu örnekte, dönüştürülen belgeyi belirtilen kaydetme seçeneklerini kullanarak "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" olarak kaydediyoruz.

### Aspose.Words for .NET kullanan "Tüm CSS kurallarını tek bir dosyaya yaz" özelliğine sahip HtmlFixedSaveOptions için örnek kaynak kodu

```csharp
// Belge dizininize erişim yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word belgesini yükleyin
Document doc = new Document(dataDir + "Document.docx");

// "Tüm CSS kurallarını tek bir dosyaya yaz" özelliği ile yedekleme seçeneklerini yapılandırın
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Belgeyi sabit HTML'ye dönüştürün
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Çözüm

Bu kılavuzda, Aspose.Words for .NET kitaplığı ile HtmlFixedSaveOptions kullanarak tüm CSS kurallarını tek bir dosyaya yazarak bir Word belgesini sabit HTML'ye dönüştürmeyi ele aldık. Sağlanan adımları izleyerek ve sağlanan C# kaynak kodunu kullanarak bu işlevi C# uygulamanıza kolayca uygulayabilirsiniz. Tüm CSS kurallarını tek bir dosyaya yazmak, belge dönüştürme sırasında oluşturulan HTML kodunu düzenlemeyi ve yönetmeyi kolaylaştırır.