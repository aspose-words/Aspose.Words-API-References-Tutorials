---
title: Gömülü Arial ve Times Roman Yazı Tiplerini Atlayarak PDF Boyutunu Optimize Edin
linktitle: Gömülü Arial ve Times Roman Yazı Tiplerini Atlayarak PDF Boyutunu Optimize Edin
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Arial ve Times Roman yazı tiplerini gömmeden optimize edilmiş PDF oluşturmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Bu makale, Aspose.Words for .NET ile gömülü Arial ve Times Roman yazı tiplerini meta dosya boyutuna atlayarak PDF boyutunu optimize etme özelliğinin nasıl kullanılacağı hakkında adım adım bir kılavuz sağlar. Kodun her bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgede yazı tipi gömme modu seçeneğini nasıl yapılandıracağınızı ve Arial ve Times Roman yazı tiplerini gömmeden PDF oluşturmayı anlayabileceksiniz.

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

## 3. Adım: Yazı tipi yerleştirmeyle PDF olarak kaydetme seçeneklerini yapılandırın

 Arial ve Times Roman yazı tiplerini oluşturulan PDF'ye yerleştirmeyi atlamak için,`PdfSaveOptions` nesneyi ayarlayın ve`FontEmbeddingMode` mülkiyet`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## 4. Adım: Belgeyi gömülü yazı tipleri olmadan PDF olarak kaydedin

Son olarak daha önce yapılandırdığımız kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Bu kadar ! Aspose.Words for .NET'i kullanarak Arial ve Times Roman yazı tiplerini gömmeden başarıyla PDF oluşturdunuz.

### Aspose.Words for .NET ile meta dosya boyutunda gömülü Arial ve Times Roman yazı tiplerini atlamak için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak Arial ve Times Roman yazı tiplerinin PDF belgesine yerleştirilmesinin nasıl devre dışı bırakılacağını açıkladık. Belirtilen adımları izleyerek, bu belirli yazı tiplerini gömmeden bir PDF dosyası oluşturabilirsiniz; bu, dosya boyutunun küçültülmesine ve farklı platformlar arasında daha iyi belge uyumluluğu sağlanmasına yardımcı olabilir. Bu özelliği kullanırken yazı tipi yerleştirmeyi devre dışı bırakmanın sonuçlarını dikkate aldığınızdan emin olun. PDF dosyalarınızın oluşturulmasını optimize etmek için Aspose.Words for .NET'in diğer özelliklerini keşfetmekten çekinmeyin.

### Sıkça Sorulan Sorular

#### S: Arial ve Times Roman yazı tipinin PDF belgesine yerleştirilmesini devre dışı bırakmak nedir ve neden önemlidir?
C: Arial ve Times Roman yazı tiplerinin PDF belgesine yerleştirilmesinin devre dışı bırakılması, bu yazı tiplerinin oluşturulan PDF dosyasına dahil edilmemesi işlemidir. Bu, PDF okuyucu sistemlerinde halihazırda yaygın olarak bulunan yazı tiplerini dahil etmekten kaçınarak PDF dosyasının boyutunu azaltmak açısından önemli olabilir. Ayrıca, PDF belgesinin farklı cihazlar ve platformlar arasında daha iyi uyumluluğunun ve tutarlı görünümünün sağlanmasına da yardımcı olabilir.

#### S: Aspose.Words for .NET'i Arial ve Times Roman yazı tiplerini PDF belgesine gömmeyecek şekilde nasıl yapılandırabilirim?
C: Aspose.Words for .NET'i Arial ve Times Roman yazı tiplerini PDF belgesine yerleştirmeyecek şekilde yapılandırmak için şu adımları izleyin:

 Belgelerinizin bulunduğu dizin yolunu değiştirerek ayarlayın.`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

 İşlemek istediğiniz belgeyi kullanarak yükleyin.`Document` sınıf ve belirtilen belge yolu.

 Bir örneğini oluşturun`PdfSaveOptions` sınıfı seçin ve ayarlayın`FontEmbeddingMode` mülkiyet`PdfFontEmbeddingMode.EmbedAll`. Bu, Arial ve Times Roman dışındaki tüm yazı tiplerini oluşturulan PDF dosyasına gömecektir.

 Kullan`Save` yöntemi`Document` Daha önce yapılandırılan kaydetme seçeneklerini belirterek belgeyi PDF formatında kaydetmek için nesneyi seçin.

#### S: Bir PDF belgesine Arial ve Times Roman yazı tipi yerleştirmeyi devre dışı bırakmanın faydaları nelerdir?
C: Bir PDF belgesine Arial ve Times Roman yazı tipi yerleştirmeyi devre dışı bırakmanın faydaları şunlardır:

PDF dosya boyutunun küçültülmesi: Arial ve Times Roman gibi yaygın olarak bulunan yazı tiplerinin yerleştirilmesinden kaçınılarak, PDF dosya boyutu küçültülebilir, böylece dosyaların saklanması, paylaşılması ve aktarılması daha kolay hale gelir.

Daha iyi uyumluluk: PDF okuyucu sistemlerinde yaygın olarak bulunan yazı tiplerini kullanarak, belgenin farklı cihaz ve platformlarda daha iyi uyumluluğunu ve görünümünü sağlarsınız.

#### S: Arial ve Times Roman yazı tiplerinin bir PDF belgesine yerleştirilmesini devre dışı bırakmanın sonuçları nelerdir?
C: Arial ve Times Roman yazı tiplerinin PDF belgesine yerleştirilmesinin devre dışı bırakılmasının sonuçları aşağıdaki gibidir:

Farklı görünüm: PDF'nin açıldığı sistemde Arial ve Times Roman yazı tipleri bulunmuyorsa yedek yazı tipleri kullanılacaktır, bu da istenilenden farklı bir görünüme neden olabilir.

Okunabilirlik sorunları: Kullanılan yedek yazı tipleri, orijinal yazı tipleri kadar okunabilir olmayabilir ve bu da belgenin okunabilirliğini etkileyebilir.