---
title: PDF Belgesinde Anahat Seçeneklerini Ayarlama
linktitle: PDF Belgesinde Anahat Seçeneklerini Ayarlama
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir PDF belgesinde taslak seçeneklerini ayarlamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/set-outline-options/
---

Bu makale, Aspose.Words for .NET ile meta dosya boyutuna yönelik anahat seçeneklerini ayarlama özelliğinin nasıl kullanılacağı hakkında adım adım bir kılavuz sağlar. Kodun her bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgedeki anahat seçeneklerini nasıl ayarlayacağınızı ve ilgili anahat seçenekleriyle bir PDF oluşturmayı anlayabileceksiniz.

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

## 3. Adım: PDF olarak kaydetme seçeneklerini plan seçenekleriyle yapılandırın

Oluşturulan PDF'deki anahat seçeneklerini ayarlamak için,`PdfSaveOptions` nesne. Başlık anahat düzeylerinin sayısını ayarlayabiliriz (`HeadingsOutlineLevels`) ve genişletilmiş anahat düzeylerinin sayısı (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## 4. Adım: Anahat seçenekleriyle belgeyi PDF olarak kaydedin

Son olarak daha önce yapılandırdığımız kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

Bu kadar ! Aspose.Words for .NET'i kullanarak bir belgedeki anahat seçeneklerini başarıyla ayarladınız ve karşılık gelen anahat seçenekleriyle bir PDF oluşturdunuz.

### Aspose.Words for .NET ile plan seçeneklerini meta dosya boyutuna ayarlamak için örnek kaynak kodu


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

Bu eğitimde Aspose.Words for .NET kullanarak bir PDF belgesinde anahat seçeneklerinin nasıl ayarlanacağını açıkladık. Açıklanan adımları kullanarak belgenizdeki başlık ve anahat düzeylerini kolayca belirleyebilir ve ilgili anahat seçenekleriyle bir PDF dosyası oluşturabilirsiniz. Aspose.Words for .NET'i kullanarak PDF belgelerinizdeki yapıyı ve gezinmeyi geliştirmek için anahat seçeneğinin avantajlarından yararlanın.

### Sıkça Sorulan Sorular

#### S: Bir PDF belgesindeki anahat seçeneği nedir?
C: Bir PDF belgesindeki anahat seçeneği, belge içeriğinin hiyerarşik yapısını ifade eder. Etkileşimli bir içindekiler tablosu oluşturmanıza olanak tanır ve belgede gezinmeyi kolaylaştırır. Anahat seçenekleri, ana hatta eklenecek başlık ve alt başlık düzeylerini ve oluşturulan taslakta görüntülenecek ayrıntı düzeyini belirler.

#### S: Aspose.Words for .NET'i kullanarak bir PDF belgesindeki anahat seçeneklerini nasıl ayarlayabilirim?
C: Aspose.Words for .NET kullanarak bir PDF belgesindeki taslak seçeneklerini ayarlamak için şu adımları izleyin:

 Belgelerinizin bulunduğu dizin yolunu değiştirerek ayarlayın.`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

 PDF'ye dönüştürmek istediğiniz belgeyi kullanarak yükleyin.`Document` sınıfını seçin ve belirtilen belgeler dizinindeki belgenin yolunu belirtin.

 Bir örneğini oluşturarak PDF olarak kaydetme seçeneklerini yapılandırın.`PdfSaveOptions` sınıf ve kullanımı`OutlineOptions` Anahat seçeneklerini ayarlama özelliği. Anahatta dahil edilecek başlık düzeylerinin sayısını aşağıdaki düğmeyi kullanarak belirleyebilirsiniz:`HeadingsOutlineLevels` özelliğini ve genişletilmiş anahat seviyelerinin sayısını kullanarak`ExpandedOutlineLevels` mülk.

 Belgeyi kullanarak PDF formatında kaydedin.`Save` yöntemi`Document` yolu ve kaydetme seçeneklerini belirten sınıf.

#### S: Bir PDF belgesindeki plan seçeneği nedir?
C: PDF belgesindeki anahat seçeneği, içeriğin hiyerarşik yapısını oluşturmanıza olanak tanır; bu da belgede gezinmeyi ve farklı bölümlere erişmeyi kolaylaştırır. Bu, kullanıcıların içindekiler veya anahattaki girişleri tıklatarak belgenin belirli bölümlerine hızlı bir şekilde atlamasına olanak tanır. Anahat seçeneği aynı zamanda genel belge yapısına genel bir bakış sağlayarak okuma deneyimini de geliştirir.
