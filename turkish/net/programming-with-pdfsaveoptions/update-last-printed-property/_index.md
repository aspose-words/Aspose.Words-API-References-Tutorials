---
title: PDF Belgesinde Son Basılan Özelliği Güncelle
linktitle: PDF Belgesinde Son Basılan Özelliği Güncelle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile PDF'ye dönüştürürken "Son Basılan" özelliğini güncellemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Bu makale, Aspose.Words for .NET ile PDF Belgesi güncelleme özelliğinde "Son Baskı" özelliğinin nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, PDF'ye dönüştürürken "Son yazdırılan" özelliğini güncelleme seçeneğini nasıl yapılandıracağınızı anlayabileceksiniz.

Başlamadan önce, projenizde Aspose.Words for .NET kitaplığını kurduğunuzdan ve yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için, belgelerinizin bulunduğu dizine giden yolu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler dizininize giden gerçek yolla.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Ardından, işlemek istediğimiz belgeyi yüklememiz gerekiyor. Bu örnekte, belgenin "Rendering.docx" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: Güncellenmiş "Son Yazdırılan" Özelliğiyle PDF Olarak Kaydetme Seçeneklerini Yapılandırın

 PDF'ye dönüştürürken "Son Basılan" özelliğinin güncellenmesini etkinleştirmek için,`PdfSaveOptions` nesne ve ayarlayın`UpdateLastPrintedProperty` mülkiyet`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## 4. Adım: "Son yazdırılan" özelliğinin güncellenmesiyle belgeyi PDF olarak kaydedin

Son olarak, daha önce yapılandırılmış kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

Bu kadar ! Aspose.Words for .NET kullanarak bir belgeyi PDF'ye dönüştürürken "Son Basılan" özelliğinin güncellenmesini başarıyla etkinleştirdiniz.

### Aspose.Words for .NET ile "Son Basılan" Özelliği Güncellemek için Örnek Kaynak Kodu


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak bir PDF belgesindeki "Son Basılan" özelliğinin nasıl güncelleneceğini açıkladık. Verilen adımları izleyerek, bir belgeyi PDF'ye dönüştürürken "Son Basılan" özelliğini güncelleme seçeneğini kolayca yapılandırabilirsiniz. Belge kullanımını ve ilgili bilgileri takip etmek için bu özelliği kullanın.

### Sıkça Sorulan Sorular

#### S: Bir PDF belgesindeki "Son Basılan" özelliği nedir?
Y: Bir PDF belgesindeki "Son Basılan" özelliği, belgenin en son yazdırıldığı tarih ve saati ifade eder. Bu özellik, belge kullanımı ve yönetimi hakkındaki bilgileri izlemek için yararlı olabilir.

#### S: Aspose.Words for .NET ile bir PDF belgesindeki "Son Basılan" özelliğini nasıl güncelleyebilirim?
C: Bir PDF belgesindeki "Son Basılan" özelliğini Aspose.Words for .NET ile güncellemek için şu adımları izleyin:

 örneğini oluşturun`Document` Word belgesine giden yolu belirten sınıf.

 örneğini oluşturun`PdfSaveOptions` sınıflandırın ve ayarlayın`UpdateLastPrintedProperty` mülkiyet`true` "Son Basılan" özelliğinin güncellenmesini sağlamak için.

 Kullan`Save` yöntemi`Document`kaydetme seçeneklerini belirterek belgeyi PDF biçiminde kaydetmek için sınıf.

#### S: Oluşturulan PDF belgesinde "Son Basılan" özelliğinin güncellenip güncellenmediğini nasıl kontrol edebilirim?
Y: Oluşturulan PDF belgesinde "Son Basılan" özelliğinin güncellenip güncellenmediğini, PDF dosyasını Adobe Acrobat Reader gibi uyumlu bir PDF görüntüleyici ile açıp belge bilgilerini görüntüleyerek kontrol edebilirsiniz. Son baskının tarih ve saati, PDF belgesinin oluşturulduğu tarih ve saate karşılık gelmelidir.
