---
title: Bir PDF Belgesinde Anahat Seçeneklerini Ayarlama
linktitle: Bir PDF Belgesinde Anahat Seçeneklerini Ayarlama
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir PDF belgesinde anahat seçeneklerini ayarlamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/set-outline-options/
---

Bu makale, Aspose.Words for .NET ile anahat seçeneklerini meta dosyası boyutuna ayarla özelliğinin nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgede anahat seçeneklerini nasıl ayarlayacağınızı ve karşılık gelen anahat seçenekleriyle bir PDF oluşturmayı öğrenebileceksiniz.

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

## 3. Adım: Plan seçenekleriyle PDF olarak kaydetme seçeneklerini yapılandırın

 Oluşturulan PDF'de anahat seçeneklerini ayarlamak için,`PdfSaveOptions` nesne. Başlık anahat düzeylerinin sayısını ayarlayabiliriz (`HeadingsOutlineLevels`) ve genişletilmiş anahat düzeylerinin sayısı (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## 4. Adım: Anahat seçenekleriyle belgeyi PDF olarak kaydedin

Son olarak, daha önce yapılandırılmış kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

Bu kadar ! Aspose.Words for .NET'i kullanarak bir belgede anahat seçeneklerini başarıyla belirlediniz ve karşılık gelen anahat seçenekleriyle bir PDF oluşturdunuz.

### Aspose.Words for .NET ile plan seçeneklerini meta dosyası boyutuna ayarlamak için örnek kaynak kodu


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak bir PDF belgesinde anahat seçeneklerinin nasıl ayarlanacağını açıkladık. Açıklanan adımları kullanarak, belgenizdeki başlık ve anahat düzeylerini kolayca belirleyebilir ve karşılık gelen anahat seçenekleriyle bir PDF dosyası oluşturabilirsiniz. Aspose.Words for .NET kullanarak PDF belgelerinizdeki yapıyı ve gezinmeyi iyileştirmek için anahat seçeneğinin avantajlarından yararlanın.

### Sıkça Sorulan Sorular

#### S: Bir PDF belgesindeki anahat seçeneği nedir?
Y: Bir PDF belgesindeki anahat seçeneği, belge içeriğinin hiyerarşik yapısını ifade eder. Etkileşimli bir içindekiler tablosu oluşturmanıza olanak tanır ve belgede gezinmeyi kolaylaştırır. Anahat seçenekleri, ana hatta dahil edilecek başlık ve alt başlık düzeylerini ve oluşturulan anahatta görüntülenecek ayrıntı düzeyini belirler.

#### S: Aspose.Words for .NET kullanarak bir PDF belgesinde anahat seçeneklerini nasıl ayarlayabilirim?
C: Aspose.Words for .NET kullanarak bir PDF belgesinde ana hat seçeneklerini ayarlamak için şu adımları izleyin:

 Değiştirerek belgelerinizin bulunduğu dizin yolunu ayarlayın.`"YOUR DOCUMENT DIRECTORY"` belgeler dizininizin gerçek yolu ile.

 kullanarak PDF'ye dönüştürmek istediğiniz belgeyi yükleyin.`Document` class ve belirtilen belgeler dizinindeki belgenin yolunu belirtin.

 örneğini oluşturarak PDF olarak kaydetme seçeneklerini yapılandırın.`PdfSaveOptions` sınıf ve kullanarak`OutlineOptions` anahat seçeneklerini ayarlamak için özelliği. Anahatta dahil edilecek başlık düzeylerinin sayısını belirtebilirsiniz.`HeadingsOutlineLevels` özelliği ve genişletilmiş anahat düzeylerinin sayısı`ExpandedOutlineLevels` mülk.

 kullanarak belgeyi PDF formatında kaydedin.`Save` yöntemi`Document`yolu ve kaydetme seçeneklerini belirten sınıf.

#### S: Bir PDF belgesinde plan seçeneği nedir?
C: Bir PDF belgesindeki anahat seçeneği, belgede gezinmeyi ve farklı bölümlere erişmeyi kolaylaştıran, içeriğin hiyerarşik bir yapısını oluşturmanıza olanak tanır. Bu, kullanıcıların içindekiler tablosundaki veya ana hatlardaki girişleri tıklatarak belgenin belirli bölümlerine hızlı bir şekilde atlamalarına olanak tanır. Anahat seçeneği, genel belge yapısına genel bir bakış sunarak okuma deneyimini de geliştirir.
