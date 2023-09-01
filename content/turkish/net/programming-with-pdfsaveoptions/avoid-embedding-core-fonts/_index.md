---
title: Temel Yazı Tiplerini Gömmeyerek PDF Dosya Boyutunu Azaltın
linktitle: Temel Yazı Tiplerini Gömmeyerek PDF Dosya Boyutunu Azaltın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgelerini PDF'ye dönüştürürken Temel Yazı Tiplerini Gömmeyerek PDF Dosya Boyutunu Nasıl Küçülteceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

Bu eğitimde, temel yazı tiplerini Aspose.Words for .NET'e gömmeyerek PDF dosya boyutunu nasıl azaltabileceğinizi adım adım anlatacağız. Bu özellik, bir Word belgesini dönüştürürken Arial, Times New Roman vb. gibi temel yazı tiplerinin PDF'ye gömülmesi gerekip gerekmediğini kontrol etmenize olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme

PDF'ye dönüştürmek istediğiniz Word belgesini yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Word belgenizin doğru yolunu belirttiğinizden emin olun.

## Adım 2: PDF Dönüştürme Seçeneklerini Ayarlayın

PdfSaveOptions sınıfının bir örneğini oluşturun ve temel yazı tipi yerleştirmeyi önlemeyi etkinleştirin:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Bu seçenek, temel yazı tiplerinin PDF'ye gömülüp gömülmeyeceğini kontrol eder.

## 3. Adım: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` Dönüştürme seçeneklerini belirterek Word belgesini PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET Kullanarak Çekirdek Fontları Gömmekten Kaçının için örnek kaynak kodu

Aspose.Words for .NET'e çekirdek yazı tipi yerleştirmeyi önleme özelliğini kullanmak için tam kaynak kodunu burada bulabilirsiniz:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Çıktı PDF'sine Arial, Times New Roman vb. gibi temel yazı tipleri eklenmez.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Bu adımları izleyerek, Aspose.Words for .NET ile bir Word belgesini dönüştürürken temel yazı tiplerinin PDF'ye gömülüp gömülmeyeceğini kolayca kontrol edebilirsiniz.


## Çözüm

Bu eğitimde, Aspose.Words for .NET'e temel yazı tiplerini gömmeyerek bir PDF dosyasının boyutunun nasıl azaltılacağını açıkladık. Bu özellik, bir Word belgesini dönüştürürken temel yazı tiplerinin PDF'ye gömülüp gömülmeyeceğini kontrol etmenizi sağlar. Özetlenen adımları izleyerek, temel yazı tiplerinin gömülmesini veya gömülmemesini kolayca kontrol edebilirsiniz; bu, PDF dosya boyutunun küçültülmesine yardımcı olabilir ve belgenin farklı cihazlar ve platformlarda daha iyi uyumluluk ve tutarlı bir görünüm sağlamasına yardımcı olabilir. Temel yazı tiplerini yerleştirmemenin sonuçlarını göz önünde bulundurmayı ve belgenin beklendiği gibi görüntülendiğinden emin olmak için denemeler yapmayı unutmayın.

### Sıkça Sorulan Sorular

#### S: Temel yazı tiplerini PDF dosyasına gömmeme seçeneği nedir ve bu neden önemlidir?
C: Bir PDF dosyasına temel yazı tiplerini gömmeme seçeneği, bir Word belgesini dönüştürürken Arial, Times New Roman vb. gibi temel yazı tiplerinin PDF'ye gömülmesi gerekip gerekmediğini kontrol eder. Bu, PDF okuyucu sistemlerinde yaygın olarak bulunan yazı tiplerini dahil etmekten kaçınarak PDF dosyasının boyutunu azaltmak açısından önemli olabilir. Ayrıca, PDF belgesinin farklı cihazlar ve platformlar arasında daha iyi uyumluluğunun ve tutarlı görünümünün sağlanmasına da yardımcı olabilir.

#### S: Aspose.Words for .NET'i temel yazı tiplerini bir PDF dosyasına gömmeyecek şekilde nasıl yapılandırabilirim?
C: Aspose.Words for .NET'i temel yazı tiplerini bir PDF dosyasına yerleştirmeyecek şekilde yapılandırmak için şu adımları izleyin:

 Belgelerinizin bulunduğu dizin yolunu değiştirerek ayarlayın.`"YOUR DOCUMENTS DIRECTORY"` belge dizininizin gerçek yolu ile.

 PDF'ye dönüştürmek istediğiniz Word belgesini kullanarak yükleyin.`Document` sınıf ve belirtilen belge yolu.

 Bir örneğini oluşturun`PdfSaveOptions` sınıfı seçin ve ayarlayın`UseCoreFonts` mülkiyet`true`. Bu, temel yazı tiplerinin oluşturulan PDF dosyasına gömülmesini önleyecektir.

 Kullan`Save` yöntemi`Document` Daha önce yapılandırılan dönüştürme seçeneklerini belirterek belgeyi PDF formatında kaydetmek için nesneyi seçin.

#### S: Temel yazı tiplerini bir PDF dosyasına yerleştirmemenin faydaları nelerdir?
C: Temel yazı tiplerini PDF dosyasına yerleştirmemenin faydaları şunlardır:

PDF dosya boyutunun küçültülmesi: Arial, Times New Roman vb. gibi yaygın olarak bulunan yazı tiplerinin yerleştirilmesinden kaçınılarak, PDF dosya boyutu küçültülebilir, böylece dosyaların saklanması, paylaşılması ve aktarılması daha kolay hale gelir.

Daha iyi uyumluluk: PDF okuyucu sistemlerinde yaygın olarak bulunan temel yazı tiplerini kullanarak, farklı cihaz ve platformlarda daha iyi uyumluluk ve belge görünümü sağlarsınız.

#### S: Temel yazı tiplerini bir PDF dosyasına yerleştirmemenin sonuçları nelerdir?
C: Temel yazı tiplerini bir PDF dosyasına yerleştirmemenin sonuçları aşağıdaki gibidir:

Farklı görünüm: PDF'nin açıldığı sistemde temel yazı tipleri mevcut değilse, yedek yazı tipleri kullanılacaktır, bu da amaçlanandan farklı bir görünüme neden olabilir.

Okunabilirlik sorunları: Kullanılan yedek yazı tipleri, orijinal yazı tipleri kadar okunabilir olmayabilir ve bu da belgenin okunabilirliğini etkileyebilir.