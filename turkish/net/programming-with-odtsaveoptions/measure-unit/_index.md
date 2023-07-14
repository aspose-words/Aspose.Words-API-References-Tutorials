---
title: Ölçü birimi
linktitle: Ölçü birimi
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesini ODT'ye dönüştürürken ölçü birimini nasıl belirteceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-odtsaveoptions/measure-unit/
---

Bir C# uygulamasında bir Word belgesini OpenDocument Text (ODT) biçimine dönüştürdüğünüzde, ölçülebilir biçimlendirme ve içerik özellikleri için kullanılan ölçü birimini belirtmek isteyebilirsiniz. .NET için Aspose.Words kitaplığıyla, OdtSaveOptions kaydetme seçeneklerini kullanarak bu işlevselliği kolayca belirleyebilirsiniz. Bu adım adım kılavuzda, OdtSaveOptions kullanarak ölçü birimini belirterek bir Word belgesini ODT'ye dönüştürmek için Aspose.Words for .NET C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, .NET dahil olmak üzere farklı platformlarda Word belgeleri oluşturmak, düzenlemek, dönüştürmek ve korumak için güçlü bir kitaplıktır. Belgeleri işlemek için metin ekleme, biçimlendirmeyi değiştirme, bölümler ekleme ve çok daha fazlası gibi birçok özellik sunar.

## Word belgesini yükleme

İlk adım, ODT'ye dönüştürmek istediğiniz Word belgesini yüklemektir. Belgeyi kaynak dosyadan yüklemek için Document sınıfını kullanın. İşte bir örnek :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

Bu örnekte, belgeler dizininde bulunan "Document.docx" belgesini yüklüyoruz.

## Yedekleme seçeneklerini yapılandırma

Bir sonraki adım, ODT'ye dönüştürmek için yedekleme seçeneklerini yapılandırmaktır. OdtSaveOptions sınıfını kullanın ve MeasureUnit özelliğini istenen değere ayarlayın. Örneğin, ölçü birimi olarak inç kullanmak istiyorsanız, MeasureUnit öğesini OdtSaveMeasureUnit.Inches olarak ayarlayın. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

Yeni bir OdtSaveOptions nesnesi oluşturuyoruz ve MeasureUnit özelliğini istenen değere ayarlıyoruz, bizim durumumuzda ölçüm birimi olarak inç kullanmak için OdtSaveMeasureUnit.Inches.

## Belgeyi ODT'ye dönüştür

Artık kaydetme seçeneklerini yapılandırdığımıza göre, belgeyi ODT'ye dönüştürmeye devam edebiliriz. Kaydetme seçeneklerini belirterek dönüştürülen belgeyi ODT formatında kaydetmek için Document sınıfının Save yöntemini kullanın. İşte bir örnek :

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

// "Ölçü birimi" özelliği ile yedekleme seçeneklerinin yapılandırılması
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Belgeyi ODT'ye dönüştürün
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Çözüm

Bu kılavuzda, Aspose.Words for .NET kitaplığı ile OdtSaveOptions kaydetme seçeneklerini kullanarak bir Word belgesini ölçü birimini belirterek ODT'ye nasıl dönüştüreceğinizi açıkladık. Sağlanan adımları izleyerek ve sağlanan C# kaynak kodunu kullanarak bu işlevi C# uygulamanıza kolayca uygulayabilirsiniz. ODT'ye dönüştürürken ölçü birimini belirtmek, ortaya çıkan belgenin biçimlendirmesini ve boyutlarını özel ihtiyaçlarınıza göre kontrol etmenizi sağlar.