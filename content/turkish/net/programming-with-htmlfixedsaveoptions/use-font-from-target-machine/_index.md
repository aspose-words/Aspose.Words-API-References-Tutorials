---
title: Hedef Makinedeki Yazı Tipini Kullan
linktitle: Hedef Makinedeki Yazı Tipini Kullan
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile hedef makinenin yazı tiplerini kullanarak bir Word belgesini sabit HTML'ye nasıl dönüştüreceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

Bir C# uygulamasında bir Word belgesini sabit HTML'ye dönüştürürken, oluşturulan HTML'nin belgenin orijinal görünümünü ve stilini koruduğundan emin olmak için hedef makinenin yazı tiplerini kullanmak isteyebilirsiniz. .NET için Aspose.Words kütüphanesiyle, HtmlFixedSaveOptions kaydetme seçeneklerini kullanarak bu işlevselliği kolayca belirleyebilirsiniz. Bu adım adım kılavuzda, HtmlFixedSaveOptions'ı kullanarak hedef makinenin yazı tiplerini kullanarak bir Word belgesini sabit HTML'ye dönüştürmek için Aspose.Words for .NET'in C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Aspose.Words kütüphanesini anlama

Koda dalmadan önce .NET için Aspose.Words kütüphanesini anlamak önemlidir. Aspose.Words, Word belgelerini .NET dahil farklı platformlarda oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kütüphanedir. Metin ekleme, biçimlendirmeyi değiştirme, bölüm ekleme ve çok daha fazlası gibi belgeleri değiştirmek için birçok özellik sunar.

## Word belgesini yükleme

İlk adım, sabit HTML'ye dönüştürmek istediğiniz Word belgesini yüklemektir. Belgeyi kaynak dosyadan yüklemek için Document sınıfını kullanın. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

Bu örnekte, belgeler dizininde bulunan "Alternatif font.docx içeren madde işaretleri" belgesini yüklüyoruz.

## Yedekleme seçeneklerini yapılandırma

Bir sonraki adım, sabit HTML'ye dönüştürmek için kaydetme seçeneklerini yapılandırmaktır. Aspose.Words'e hedef makinedeki yazı tiplerini kullanmasını bildirmek için HtmlFixedSaveOptions sınıfını kullanın ve UseTargetMachineFonts özelliğini true olarak ayarlayın. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

Yeni bir HtmlFixedSaveOptions nesnesi oluşturup, dönüştürme sırasında hedef makinenin yazı tiplerini kullanmak için UseTargetMachineFonts özelliğini true olarak ayarlıyoruz.

## Sabit HTML belge dönüşümü

Artık kaydetme seçeneklerini yapılandırdığımıza göre belgeyi sabit HTML'ye dönüştürmeye devam edebiliriz. Kaydetme seçeneklerini belirterek dönüştürülen belgeyi sabit HTML biçiminde kaydetmek için Document sınıfının Kaydet yöntemini kullanın. İşte bir örnek :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

Bu örnekte, dönüştürülen belgeyi belirtilen kaydetme seçeneklerini kullanarak "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" olarak kaydediyoruz.

### Aspose.Words for .NET kullanan "Hedef makinedeki yazı tiplerini kullan" özelliğine sahip HtmlFixedSaveOptions için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word belgesini yükleyin
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

//"Hedef makinedeki yazı tiplerini kullan" özelliğiyle yedekleme seçeneklerini yapılandırın
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Belgeyi sabit HTML'ye dönüştür
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Çözüm

Bu kılavuzda, .NET için Aspose.Words kütüphanesi ile hedef makinenin yazı tiplerini kullanarak bir Word belgesinin sabit HTML'ye nasıl dönüştürüleceğini açıkladık. Verilen adımları takip ederek ve verilen C# kaynak kodunu kullanarak bu işlevselliği C# uygulamanıza kolayca uygulayabilirsiniz. Hedef makinenin yazı tipleriyle sabit HTML'ye dönüştürme, belgenin HTML biçiminde aslına uygun ve tutarlı şekilde oluşturulmasını garanti eder.
