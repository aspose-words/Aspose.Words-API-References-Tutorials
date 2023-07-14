---
title: Katıştırılmış Yazı Tiplerini Devre Dışı Bırakarak PDF Boyutunu Küçültün
linktitle: Katıştırılmış Yazı Tiplerini Devre Dışı Bırakarak PDF Boyutunu Küçültün
second_title: Aspose.Words Belge İşleme API'sı
description: Belgeleri Aspose.Words for .NET ile PDF'ye dönüştürürken Windows font gömmeyi devre dışı bırakarak PDF boyutunu nasıl küçülteceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

Bu eğitimde, Aspose.Words for .NET ile bir PDF belgesine Windows yazı tipi gömmeyi devre dışı bırakarak PDF boyutunu küçültme adımlarında size yol göstereceğiz. Yazı tipi yerleştirmeyi devre dışı bırakarak oluşturulan PDF dosyasının boyutunu azaltabilirsiniz. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme

PDF'ye dönüştürmek istediğiniz belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Belgenize giden doğru yolu belirttiğinizden emin olun.

## 2. Adım: PDF kaydetme seçeneklerini ayarlayın

PdfSaveOptions sınıfının bir örneğini oluşturun ve yazı tiplerinin nasıl gömüleceğini belirtin:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Bu seçenek, oluşturulan PDF dosyasında Windows yazı tiplerinin entegrasyonunu devre dışı bırakmanıza olanak tanır.

## 3. Adım: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` dönüştürme seçeneklerini belirterek belgeyi PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Windows Yazı Tiplerini Gömmeyi Devre Dışı Bırakmak için örnek kaynak kodu

Aspose.Words for .NET ile Windows yazı tiplerini bir PDF belgesine gömmeyi devre dışı bırakmak için tam kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Çıktı PDF'si, standart Windows yazı tiplerini gömmeden kaydedilecektir.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Bu adımları izleyerek, Windows yazı tiplerinin Aspose.Words for .NET ile bir PDF belgesine gömülmesini kolayca devre dışı bırakabilirsiniz.


## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak Windows yazı tiplerini gömmeyi devre dışı bırakarak bir PDF dosyasının boyutunu nasıl küçülteceğimizi öğrendik. Yazı tipi yerleştirmeyi devre dışı bırakarak, oluşturulan PDF dosyasının boyutunu küçülterek dosyaları depolamayı, paylaşmayı ve aktarmayı kolaylaştırabilirsiniz. Ancak, Windows yazı tipi gömmeyi devre dışı bırakmanın nihai PDF belgesinde görünüm ve biçimlendirme değişikliklerine neden olabileceğini unutmamak önemlidir. Bu özelliği kullanırken bu sonuçları göz önünde bulundurduğunuzdan emin olun. PDF dosyalarınızın üretimini optimize etmek için Aspose.Words for .NET'in diğer özelliklerini keşfetmekten çekinmeyin.

### Sıkça Sorulan Sorular

#### S: Bir PDF belgesine Windows yazı tipi yerleştirmeyi devre dışı bırakmak nedir ve neden önemlidir?
Y: Bir PDF belgesine Windows yazı tipi yerleştirmeyi devre dışı bırakmak, Windows yazı tiplerinin oluşturulan PDF dosyasına dahil edilmesini önleme işlemidir. Bu, gömülü Windows yazı tipi verilerini kaldırarak PDF dosyasının boyutunu azaltır. Bu, PDF dosyalarının boyutunu küçültmek için önemli olabilir, bu da onların daha hızlı saklanmasını, paylaşılmasını ve aktarılmasını kolaylaştırabilir.

#### S: Aspose.Words for .NET kullanarak bir PDF belgesine Windows yazı tipi gömmeyi nasıl devre dışı bırakabilirim?
A: Aspose.Words for .NET kullanarak Windows yazı tiplerini bir PDF belgesine gömmeyi devre dışı bırakmak için şu adımları izleyin:

 kullanarak PDF'ye dönüştürmek istediğiniz belgeyi yükleyin.`Document` sınıf ve belge yolu.

 örneğini oluşturun`PdfSaveOptions`sınıflandırın ve ayarlayın`FontEmbeddingMode` mülkiyet`PdfFontEmbeddingMode.EmbedNone`. Bu, Windows yazı tiplerinin oluşturulan PDF dosyasına gömülmesini devre dışı bırakır.

 Kullan`Save` yöntemi`Document` Daha önce yapılandırılan dönüştürme seçeneklerini belirterek belgeyi PDF'ye dönüştürmek için nesne.

#### S: Bir PDF belgesine Windows yazı tipi katıştırmayı devre dışı bırakmanın faydaları nelerdir?
Y: Bir PDF belgesine Windows yazı tipi yerleştirmeyi devre dışı bırakmanın faydaları şunlardır:

Küçültülmüş PDF dosyası boyutu: Windows yazı tipi gömmeyi devre dışı bırakarak, gömülü Windows yazı tipi verileri kaldırılır ve oluşturulan PDF dosyasının boyutu küçülür.

Daha kolay depolama: Daha küçük PDF dosyalarının saklanması, kaydedilmesi ve aktarılması daha kolaydır.

Daha hızlı paylaşım ve aktarım: Daha küçük PDF dosyaları daha hızlı paylaşılabilir ve aktarılabilir, bu da zamandan ve kaynaklardan tasarruf sağlar.

#### S: Bir PDF belgesine Windows yazı tipi katıştırmayı devre dışı bırakmanın sonuçları nelerdir?
C: Windows yazı tiplerinin bir PDF belgesine gömülmesinin devre dışı bırakılması, aşağıdaki gibi sonuçlara yol açabilir:

Görünüm ve biçimlendirme kaybı: Belgede belirtilen Windows yazı tipleri PDF'nin açıldığı sistemde mevcut değilse, yedek yazı tipleri kullanılacak ve bu da hatalı bir görünüm ve biçimlendirmeye neden olabilir. şekil olarak beklenenden farklı.

Okunabilirlik sorunları: Kullanılan yedek yazı tipleri orijinal yazı tipleri kadar okunabilir değilse, PDF belgesindeki metnin okunabilirliğini etkileyebilir.