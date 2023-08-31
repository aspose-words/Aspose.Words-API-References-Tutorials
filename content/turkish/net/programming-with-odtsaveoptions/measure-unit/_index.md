---
title: Ölçü birimi
linktitle: Ölçü birimi
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesini ODT'ye dönüştürürken ölçü birimini nasıl belirleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-odtsaveoptions/measure-unit/
---

Bir Word belgesini C# uygulamasında OpenDocument Metni (ODT) biçimine dönüştürdüğünüzde ölçülebilir biçimlendirme ve içerik özellikleri için kullanılan ölçü birimini belirtmek isteyebilirsiniz. .NET için Aspose.Words kütüphanesiyle, OdtSaveOptions kaydetme seçeneklerini kullanarak bu işlevselliği kolayca belirleyebilirsiniz. Bu adım adım kılavuzda, OdtSaveOptions'ı kullanarak ölçü birimini belirterek bir Word belgesini ODT'ye dönüştürmek için Aspose.Words for .NET C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Aspose.Words kütüphanesini anlama

Koda dalmadan önce .NET için Aspose.Words kütüphanesini anlamak önemlidir. Aspose.Words, Word belgelerini .NET dahil farklı platformlarda oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kütüphanedir. Metin ekleme, biçimlendirmeyi değiştirme, bölüm ekleme ve çok daha fazlası gibi belgeleri değiştirmek için birçok özellik sunar.

## Word belgesini yükleme

İlk adım, ODT'ye dönüştürmek istediğiniz Word belgesini yüklemektir. Belgeyi kaynak dosyadan yüklemek için Document sınıfını kullanın. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

Bu örnekte, belgeler dizininde bulunan "Document.docx" belgesini yüklüyoruz.

## Yedekleme seçeneklerini yapılandırma

Bir sonraki adım, ODT'ye dönüştürmeye yönelik yedekleme seçeneklerini yapılandırmaktır. OdtSaveOptions sınıfını kullanın ve MeasureUnit özelliğini istediğiniz değere ayarlayın. Örneğin, ölçü birimi olarak inç kullanmak istiyorsanız MeasureUnit'i OdtSaveMeasureUnit.Inches olarak ayarlayın. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

Yeni bir OdtSaveOptions nesnesi oluşturuyoruz ve MeasureUnit özelliğini istenen değere ayarlıyoruz, bizim durumumuzda OdtSaveMeasureUnit.Inches ölçü birimi olarak inç kullanacak.

## Belgeyi ODT'ye dönüştür

Artık kaydetme seçeneklerini yapılandırdığımıza göre belgeyi ODT'ye dönüştürmeye devam edebiliriz. Kaydetme seçeneklerini belirterek dönüştürülen belgeyi ODT biçiminde kaydetmek için Document sınıfının Kaydet yöntemini kullanın. İşte bir örnek :

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

Bu örnekte, dönüştürülen belgeyi belirtilen kaydetme seçeneklerini kullanarak "WorkingWithOdtSaveOptions.MeasureUnit.odt" olarak kaydediyoruz.

### Aspose.Words for .NET kullanan "Ölçü birimi" işlevine sahip OdtSaveOptions için örnek kaynak kodu



```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word belgesini yükleyin
Document doc = new Document(dataDir + "Document.docx");

// Yedekleme seçeneklerinin "Ölçü birimi" özelliği ile yapılandırılması
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Belgeyi ODT'ye dönüştürün
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Çözüm

Bu kılavuzda, .NET için Aspose.Words kütüphanesindeki OdtSaveOptions kaydetme seçeneklerini kullanarak ölçü birimini belirterek bir Word belgesinin ODT'ye nasıl dönüştürüleceğini açıkladık. Verilen adımları takip ederek ve verilen C# kaynak kodunu kullanarak bu işlevselliği C# uygulamanıza kolayca uygulayabilirsiniz. ODT'ye dönüştürürken ölçü birimini belirtmek, ortaya çıkan belgenin formatını ve boyutlarını özel ihtiyaçlarınıza göre kontrol etmenize olanak tanır.