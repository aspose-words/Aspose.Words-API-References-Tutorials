---
title: Bir PDF Belgesinde Özel Özellikleri Dışa Aktarma
linktitle: Bir PDF Belgesinde Özel Özellikleri Dışa Aktarma
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile belgeleri PDF'ye dönüştürürken özel özellikleri nasıl dışa aktaracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/custom-properties-export/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir belgenin özel özelliklerini bir PDF belgesine dışa aktarma adımlarında size yol göstereceğiz. Özel özelliklerin dışa aktarılması, oluşturulan PDF belgesine ek bilgiler eklemenizi sağlar. Aşağıdaki adımları takip et:

## 1. Adım: Belge Oluşturma ve Özel Özellikler Ekleme

Document sınıfının bir örneğini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2. Adım: Özel özellikler ekleyin
 Ardından, istenen özel özellikleri ekleyin. Örneğin, "Aspose" değerine sahip bir "Şirket" özelliği eklemek için`Add` CustomDocumentProperties koleksiyonunun yöntemi:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Gerektiği kadar çok sayıda özel özellik ekleyebilirsiniz.

## 3. Adım: PDF dışa aktarma seçeneklerini ayarlayın

PdfSaveOptions sınıfının bir örneğini oluşturun ve özel özelliklerin nasıl dışa aktarılacağını belirtin:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Bu seçenek, PDF'ye dönüştürürken özel özelliklerin dışa aktarılmasını kontrol eder.

## 4. Adım: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` dönüştürme seçeneklerini belirterek belgeyi PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Custom Properties Export için örnek kaynak kodu

Aspose.Words for .NET kullanan bir belgeden özel özellikleri dışa aktarmak için eksiksiz kaynak kodu burada:


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Bu adımları izleyerek, Aspose.Words for .NET ile PDF'ye dönüştürürken bir belgenin özel özelliklerini kolayca dışa aktarabilirsiniz.


## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir belgeden özel özelliklerin bir PDF belgesine nasıl aktarılacağını açıkladık. Açıklanan adımları izleyerek, belgenin özel özelliklerini dışa aktararak oluşturulan PDF belgesine kolayca ek bilgiler ekleyebilirsiniz. Özel özellikleri dışa aktararak PDF belgelerinizi kişiselleştirmek ve zenginleştirmek için Aspose.Words for .NET'in özelliklerinden yararlanın.

### Sıkça Sorulan Sorular

#### S: Özel özellikleri bir PDF belgesine dışa aktarmak nedir?
C: Özel özelliklerin bir PDF belgesine dışa aktarılması, oluşturulan PDF belgesine ek bilgilerin dahil edilmesini sağlar. Özel özellikler, etiketler, anahtar sözcükler veya kimlik bilgileri gibi belgenize özgü meta verilerdir. Bu özel özellikleri dışa aktararak, PDF belgesini görüntülerken kullanıcıların kullanımına sunabilirsiniz.

#### S: Aspose.Words for .NET kullanarak bir belgenin özel özelliklerini bir PDF belgesine nasıl aktarabilirim?
Y: Aspose.Words for .NET kullanarak bir belgenin özel özelliklerini bir PDF belgesine dışa aktarmak için şu adımları izleyin:

 örneğini oluşturun`Document` sınıf.

 kullanarak istenen özel özellikleri ekleyin.`CustomDocumentProperties` Toplamak. Örneğin,`Add` "Aspose" değerine sahip bir "Şirket" özelliği ekleme yöntemi.

 örneğini oluşturun`PdfSaveOptions` kullanarak özel özelliklerin nasıl dışa aktarılacağını belirtin.`CustomPropertiesExport` mülk. bu`PdfCustomPropertiesExport.Standard` value, özel özellikleri varsayılan ayarlara göre dışa aktarır.

 Kullan`Save` yöntemi`Document` dönüştürme seçeneklerini belirterek belgeyi PDF'ye dönüştürmek için sınıf.

#### S: Bir PDF belgesinin özel özelliklerine nasıl erişebilirim?
Y: Bir PDF belgesinin özel özelliklerine erişmek için belge özelliklerini görüntülemeyi destekleyen uyumlu bir PDF okuyucu kullanabilirsiniz. Adobe Acrobat Reader gibi en yaygın PDF okuyucuları, bir PDF belgesinin meta verilerine ve özelliklerine erişim sağlar. Bu seçenekleri genellikle "Dosya" menüsünde veya belgeye sağ tıklayıp "Özellikler"i seçerek bulabilirsiniz.