---
title: PDF Belgesinde Son Yazdırılan Özelliği Güncelle
linktitle: PDF Belgesinde Son Yazdırılan Özelliği Güncelle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile PDF'ye dönüştürürken "Son Basılan" özelliğini güncellemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Bu makale, Aspose.Words for .NET ile PDF Belgesi güncelleme özelliğinde "Son Yazdırma" özelliğinin nasıl kullanılacağı hakkında adım adım bir kılavuz sağlar. Kodun her bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, PDF'ye dönüştürürken "Son yazdırılan" özelliğini güncelleme seçeneğinin nasıl yapılandırılacağını anlayabileceksiniz.

Başlamadan önce projenize Aspose.Words for .NET kütüphanesini kurup yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için belgelerinizin bulunduğu dizinin yolunu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` Belgeler dizininizin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin

Daha sonra işlemek istediğimiz belgeyi yüklememiz gerekiyor. Bu örnekte belgenin "Rendering.docx" olarak adlandırıldığını ve belirtilen belgeler dizininde bulunduğunu varsayıyoruz.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: Güncellenmiş "Son Yazdırılan" Özelliğiyle PDF Olarak Kaydetme Seçeneklerini Yapılandırma

 PDF'ye dönüştürürken "Son Basılan" özelliğinin güncellenmesini etkinleştirmek için,`PdfSaveOptions` nesneyi ayarlayın ve`UpdateLastPrintedProperty`mülkiyet`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## 4. Adım: "Son yazdırılan" özelliğinin güncellenmesiyle belgeyi PDF olarak kaydedin

Son olarak daha önce yapılandırdığımız kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedebiliriz.

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

Bu eğitimde Aspose.Words for .NET kullanarak bir PDF belgesindeki "Son Basılan" özelliğinin nasıl güncelleneceğini anlattık. Verilen adımları izleyerek, bir belgeyi PDF'ye dönüştürürken "Son Yazdırılan" özelliğini güncelleme seçeneğini kolayca yapılandırabilirsiniz. Belge kullanımını ve ilgili bilgileri takip etmek için bu özelliği kullanın.

### Sıkça Sorulan Sorular

#### S: Bir PDF belgesindeki "Son Yazdırılan" özelliği nedir?
C: Bir PDF belgesindeki "Son Yazdırılan" özelliği, belgenin en son yazdırıldığı tarih ve saati ifade eder. Bu özellik, belge kullanımı ve yönetimi hakkındaki bilgilerin izlenmesi için yararlı olabilir.

#### S: Bir PDF belgesindeki "Son Basılan" özelliğini Aspose.Words for .NET ile nasıl güncelleyebilirim?
C: Bir PDF belgesindeki "Son Basılan" özelliğini Aspose.Words for .NET ile güncellemek için şu adımları izleyin:

 Bir örneğini oluşturun`Document` Word belgesinin yolunu belirten sınıf.

 Bir örneğini oluşturun`PdfSaveOptions` sınıfı seçin ve ayarlayın`UpdateLastPrintedProperty`mülkiyet`true` "Son Basılan" özelliğinin güncellenmesini etkinleştirmek için.

 Kullan`Save` yöntemi`Document`Kaydetme seçeneklerini belirterek belgeyi PDF formatında kaydetmek için sınıf.

#### S: Oluşturulan PDF belgesinde "Son Yazdırılan" özelliğinin güncellenip güncellenmediğini nasıl kontrol edebilirim?
C: PDF dosyasını Adobe Acrobat Reader gibi uyumlu bir PDF görüntüleyiciyle açıp belge bilgilerini görüntüleyerek, oluşturulan PDF belgesinde "Son Yazdırılan" özelliğinin güncellenip güncellenmediğini kontrol edebilirsiniz. Son yazdırmanın tarihi ve saati, PDF belgesinin oluşturulduğu tarih ve saate karşılık gelmelidir.
