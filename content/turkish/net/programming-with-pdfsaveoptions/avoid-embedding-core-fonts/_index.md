---
title: Çekirdek Yazı Tiplerini Gömmeyerek PDF Dosyasının Boyutunu Küçültün
linktitle: Çekirdek Yazı Tiplerini Gömmeyerek PDF Dosyasının Boyutunu Küçültün
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile Word belgelerini PDF'ye dönüştürürken Temel Yazı Tiplerini Gömmeyerek PDF Dosyasının Boyutunu Nasıl Küçülteceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

Bu eğitimde, temel yazı tiplerini Aspose.Words for .NET ile gömmeyerek PDF dosya boyutunu nasıl küçülteceğiniz konusunda size yol göstereceğiz. Bu özellik, bir Word belgesi dönüştürülürken Arial, Times New Roman vb. gibi temel yazı tiplerinin PDF'ye gömülmesi gerekip gerekmediğini kontrol etmenizi sağlar. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme

PDF'ye dönüştürmek istediğiniz Word belgesini yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Word belgenizin doğru yolunu belirttiğinizden emin olun.

## 2. Adım: PDF Dönüştürme Seçeneklerini Ayarlayın

PdfSaveOptions sınıfının bir örneğini oluşturun ve temel yazı tipi katıştırmadan kaçınmayı etkinleştirin:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Bu seçenek, temel yazı tiplerinin PDF'ye gömülüp gömülmeyeceğini kontrol eder.

## 3. Adım: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` dönüştürme seçeneklerini belirterek Word belgesini PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Temel Yazı Tiplerini Gömmekten Kaçının için örnek kaynak kodu

Aspose.Words for .NET ile temel yazı tipi gömülmesini önlemek için özelliği kullanmak için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Çıktı PDF'si, Arial, Times New Roman vb. temel yazı tipleriyle gömülmeyecektir.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Bu adımları izleyerek, bir Word belgesini Aspose.Words for .NET ile dönüştürürken temel yazı tiplerinin PDF'ye gömülmesi gerekip gerekmediğini kolayca kontrol edebilirsiniz.


## Çözüm

Bu eğitimde, temel yazı tiplerini Aspose.Words for .NET ile gömmeyerek bir PDF dosyasının boyutunu nasıl küçültebileceğimizi açıkladık. Bu özellik, bir Word belgesi dönüştürülürken temel yazı tiplerinin PDF'ye gömülüp gömülmeyeceğini kontrol etmenizi sağlar. Ana hatları verilen adımları izleyerek, temel yazı tiplerinin gömülmesini veya gömülmemesini kolayca kontrol edebilirsiniz; bu, PDF dosya boyutunun küçültülmesine yardımcı olabilir ve daha iyi uyumluluk ve belgenin farklı aygıt ve platformlarda tutarlı görünmesini sağlar. Temel yazı tiplerini gömmemenin sonuçlarını göz önünde bulundurmayı ve belgenin beklendiği gibi işlenmesini sağlamak için denemeler yapmayı unutmayın.

### Sıkça Sorulan Sorular

#### S: Temel yazı tiplerini bir PDF dosyasına gömmeme seçeneği nedir ve bu neden önemlidir?
C: Temel yazı tiplerini bir PDF dosyasına gömme seçeneği, bir Word belgesi dönüştürülürken Arial, Times New Roman vb. temel yazı tiplerinin PDF'ye gömülmesi gerekip gerekmediğini kontrol eder. Bu, PDF okuyucu sistemlerinde yaygın olarak bulunan yazı tiplerini dahil etmekten kaçınarak PDF dosyasının boyutunu azaltmak için önemli olabilir. Ayrıca, PDF belgesinin farklı aygıtlar ve platformlar arasında daha iyi uyumluluğunun ve tutarlı görünümünün sağlanmasına da yardımcı olabilir.

#### S: Aspose.Words for .NET'i bir PDF dosyasına temel yazı tiplerini gömmeyecek şekilde nasıl yapılandırabilirim?
C: Aspose.Words for .NET'i temel yazı tiplerini bir PDF dosyasına gömmeyecek şekilde yapılandırmak için şu adımları izleyin:

 Değiştirerek belgelerinizin bulunduğu dizin yolunu ayarlayın.`"YOUR DOCUMENTS DIRECTORY"` belgeler dizininizin gerçek yolu ile.

 kullanarak PDF'ye dönüştürmek istediğiniz Word belgesini yükleyin.`Document` sınıf ve belirtilen belge yolu.

 örneğini oluşturun`PdfSaveOptions`sınıflandırın ve ayarlayın`UseCoreFonts` mülkiyet`true`. Bu, temel yazı tiplerinin oluşturulan PDF dosyasına gömülmesini önleyecektir.

 Kullan`Save` yöntemi`Document` Daha önce yapılandırılan dönüştürme seçeneklerini belirterek belgeyi PDF biçiminde kaydetmek için nesne.

#### S: Temel yazı tiplerini bir PDF dosyasına gömmemenin faydaları nelerdir?
C: Temel yazı tiplerini bir PDF dosyasına gömmemenin faydaları şunlardır:

PDF dosya boyutunu küçültme: Arial, Times New Roman vb. gibi yaygın olarak bulunan yazı tiplerini gömmekten kaçınarak, PDF dosya boyutu küçültülerek dosyaların saklanması, paylaşılması ve aktarılması kolaylaşır.

Daha iyi uyumluluk: PDF okuyucu sistemlerinde yaygın olarak bulunan temel yazı tiplerini kullanarak, farklı cihaz ve platformlarda daha iyi uyumluluk ve belge görünümü sağlarsınız.

#### S: Temel yazı tiplerini bir PDF dosyasına gömmemenin sonuçları nelerdir?
C: Temel yazı tiplerini bir PDF dosyasına gömmemenin sonuçları aşağıdaki gibidir:

Farklı görünüm: Temel yazı tipleri PDF'nin açıldığı sistemde mevcut değilse, yedek yazı tipleri kullanılacaktır ve bu da amaçlanandan farklı bir görünüme neden olabilir.

Okunabilirlik sorunları: Kullanılan yedek yazı tipleri orijinal yazı tipleri kadar okunaklı olmayabilir ve bu da belgenin okunabilirliğini etkileyebilir.