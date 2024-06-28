---
title: PDF Belgesinde Özel Özellikleri Dışa Aktarma
linktitle: PDF Belgesinde Özel Özellikleri Dışa Aktarma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile belgeleri PDF'ye dönüştürürken özel özellikleri nasıl dışa aktaracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/custom-properties-export/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir belgenin özel özelliklerini bir PDF belgesine dışa aktarma adımlarında size yol göstereceğiz. Özel özellikleri dışa aktarmak, oluşturulan PDF belgesine ek bilgiler eklemenizi sağlar. Aşağıdaki adımları takip et:

## Adım 1: Belge Oluşturma ve Özel Özellikler Ekleme

Document sınıfının bir örneğini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2. Adım: Özel özellikler ekleyin
 Daha sonra istediğiniz özel özellikleri ekleyin. Örneğin, "Apose" değerine sahip bir "Şirket" özelliği eklemek için şunu kullanın:`Add` CustomDocumentProperties koleksiyonunun yöntemi:

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

## Adım 4: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` Dönüştürme seçeneklerini belirterek belgeyi PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Özel Özellikleri Dışa Aktarma için örnek kaynak kodu

Aspose.Words for .NET kullanarak özel özellikleri bir belgeden dışa aktarmak için gereken kaynak kodun tamamı burada:


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

Bu eğitimde Aspose.Words for .NET kullanarak özel özelliklerin bir belgeden PDF belgesine nasıl aktarılacağını açıkladık. Açıklanan adımları izleyerek, belgenin özel özelliklerini dışa aktararak oluşturulan PDF belgesine kolayca ek bilgiler ekleyebilirsiniz. Özel özellikleri dışa aktararak PDF belgelerinizi kişiselleştirmek ve zenginleştirmek için Aspose.Words for .NET'in özelliklerinden yararlanın.

### Sıkça Sorulan Sorular

#### S: Özel özellikleri bir PDF belgesine aktarmak nedir?
C: Özel özelliklerin bir PDF belgesine aktarılması, oluşturulan PDF belgesine ek bilgilerin eklenmesine olanak tanır. Özel özellikler; etiketler, anahtar kelimeler veya kimlik bilgileri gibi belgenize özel meta verilerdir. Bu özel özellikleri dışa aktararak, PDF belgesini görüntülerken bunları kullanıcıların kullanımına sunabilirsiniz.

#### S: Aspose.Words for .NET'i kullanarak bir belgenin özel özelliklerini bir PDF belgesine nasıl aktarabilirim?
C: Aspose.Words for .NET kullanarak bir belgenin özel özelliklerini PDF belgesine aktarmak için şu adımları izleyin:

 Bir örneğini oluşturun`Document` sınıf.

 İstenilen özel özellikleri kullanarak ekleyin`CustomDocumentProperties` Toplamak. Örneğin, şunu kullanın:`Add` "Apose" değerine sahip bir "Şirket" özelliği ekleme yöntemi.

 Bir örneğini oluşturun`PdfSaveOptions` sınıfını seçin ve özel özelliklerin nasıl dışa aktarılacağını belirtin.`CustomPropertiesExport` mülk.`PdfCustomPropertiesExport.Standard` değer, özel özellikleri varsayılan ayarlara göre dışa aktarır.

 Kullan`Save` yöntemi`Document` Dönüştürme seçeneklerini belirterek belgeyi PDF'ye dönüştürmek için sınıf.

#### S: Bir PDF belgesinin özel özelliklerine nasıl erişebilirim?
C: Bir PDF belgesinin özel özelliklerine erişmek için belge özelliklerini görüntülemeyi destekleyen uyumlu bir PDF okuyucu kullanabilirsiniz. Adobe Acrobat Reader gibi en yaygın PDF okuyucuları, bir PDF belgesinin meta verilerine ve özelliklerine erişim sağlar. Bu seçenekleri genellikle "Dosya" menüsünde veya belgeye sağ tıklayıp "Özellikler"i seçerek bulabilirsiniz.