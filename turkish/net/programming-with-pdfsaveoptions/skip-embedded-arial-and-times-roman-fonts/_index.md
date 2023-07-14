---
title: Gömülü Arial ve Times Roman Yazı Tiplerini Atla ile PDF Boyutunu Optimize Edin
linktitle: Gömülü Arial ve Times Roman Yazı Tiplerini Atla ile PDF Boyutunu Optimize Edin
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile Arial ve Times Roman yazı tiplerini gömmeden optimize edilmiş PDF oluşturmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Bu makale, gömülü Arial ve Times Roman yazı tiplerini Aspose.Words for .NET ile meta dosya boyutuna atlayarak PDF boyutunu optimize etmek için bu özelliğin nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgede yazı tipi gömme modu seçeneğini nasıl yapılandıracağınızı ve Arial ve Times Roman yazı tiplerini gömmeden bir PDF oluşturmayı öğrenebileceksiniz.

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

## 3. Adım: Yazı tipi gömme ile PDF olarak kaydetme seçeneklerini yapılandırın

 Oluşturulan PDF'ye Arial ve Times Roman yazı tiplerini yerleştirmeyi atlamak için,`PdfSaveOptions` nesne ve ayarlayın`FontEmbeddingMode` mülkiyet`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## 4. Adım: Belgeyi katıştırılmış yazı tipleri olmadan PDF olarak kaydedin

Son olarak, daha önce yapılandırılmış kaydetme seçeneklerini kullanarak belgeyi PDF formatında kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Bu kadar ! Aspose.Words for .NET kullanarak Arial ve Times Roman yazı tiplerini gömmeden başarıyla bir PDF oluşturdunuz.

### Aspose.Words for .NET ile gömülü Arial ve Times Roman yazı tiplerini meta dosyası boyutunda atlamak için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak Arial ve Times Roman yazı tiplerinin bir PDF belgesine gömülmesinin nasıl devre dışı bırakılacağını açıkladık. Ana hatları verilen adımları izleyerek, dosya boyutunu küçültmeye ve farklı platformlarda daha iyi belge uyumluluğu sağlamaya yardımcı olabilecek bu belirli yazı tiplerini gömmeden bir PDF dosyası oluşturabilirsiniz. Bu özelliği kullanırken yazı tipi gömmeyi devre dışı bırakmanın sonuçlarını göz önünde bulundurduğunuzdan emin olun. PDF dosyalarınızın üretimini optimize etmek için Aspose.Words for .NET'in diğer özelliklerini keşfetmekten çekinmeyin.

### Sıkça Sorulan Sorular

#### S: Bir PDF belgesine Arial ve Times Roman yazı tipi yerleştirmeyi devre dışı bırakan nedir ve bu neden önemlidir?
C: Arial ve Times Roman yazı tiplerinin bir PDF belgesine gömülmesinin devre dışı bırakılması, bu yazı tiplerinin oluşturulan PDF dosyasına dahil edilmemesi işlemidir. Bu, PDF okuyucu sistemlerinde zaten yaygın olarak bulunan yazı tiplerini dahil etmekten kaçınarak PDF dosyasının boyutunu azaltmak için önemli olabilir. Ayrıca, PDF belgesinin farklı aygıtlar ve platformlar arasında daha iyi uyumluluğunun ve tutarlı görünümünün sağlanmasına da yardımcı olabilir.

#### S: Aspose.Words for .NET'i Arial ve Times Roman yazı tiplerini bir PDF belgesine gömmeyecek şekilde nasıl yapılandırabilirim?
C: Aspose.Words for .NET'i Arial ve Times Roman yazı tiplerini bir PDF belgesine gömmeyecek şekilde yapılandırmak için şu adımları izleyin:

 Değiştirerek belgelerinizin bulunduğu dizin yolunu ayarlayın.`"YOUR DOCUMENT DIRECTORY"` belgeler dizininizin gerçek yolu ile.

 kullanarak işlemek istediğiniz belgeyi yükleyin.`Document` sınıf ve belirtilen belge yolu.

 örneğini oluşturun`PdfSaveOptions`sınıflandırın ve ayarlayın`FontEmbeddingMode` mülkiyet`PdfFontEmbeddingMode.EmbedAll`. Bu, oluşturulan PDF dosyasına Arial ve Times Roman dışındaki tüm yazı tiplerini gömecektir.

 Kullan`Save` yöntemi`Document` Daha önce yapılandırılan kaydetme seçeneklerini belirterek belgeyi PDF biçiminde kaydetmek için nesne.

#### S: Bir PDF belgesine Arial ve Times Roman yazı tipi yerleştirmeyi devre dışı bırakmanın faydaları nelerdir?
Y: Bir PDF belgesine Arial ve Times Roman yazı tipi yerleştirmeyi devre dışı bırakmanın faydaları şunlardır:

PDF dosya boyutunu küçültme: Arial ve Times Roman gibi yaygın olarak bulunan yazı tiplerini gömmekten kaçınarak, PDF dosya boyutu küçültülerek dosyaların saklanması, paylaşılması ve aktarılması kolaylaşır.

Daha iyi uyumluluk: PDF okuyucu sistemlerinde yaygın olarak bulunan yazı tiplerini kullanarak, belgenin farklı aygıtlarda ve platformlarda daha iyi uyumluluğunu ve görünümünü sağlarsınız.

#### S: Bir PDF belgesine Arial ve Times Roman yazı tiplerinin yerleştirilmesini devre dışı bırakmanın sonuçları nelerdir?
C: Arial ve Times Roman yazı tiplerinin bir PDF belgesine gömülmesinin devre dışı bırakılmasının sonuçları aşağıdaki gibidir:

Farklı görünüm: PDF'nin açıldığı sistemde Arial ve Times Roman yazı tipleri yoksa, yedek yazı tipleri kullanılacak ve bu da amaçlanandan farklı bir görünüme neden olabilir.

Okunabilirlik sorunları: Kullanılan yedek yazı tipleri, kaynaktaki yazı tipleri kadar okunabilir olmayabilir ve bu da belgenin okunabilirliğini etkileyebilir.