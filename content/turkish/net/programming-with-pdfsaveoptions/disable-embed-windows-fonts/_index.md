---
title: Gömülü Yazı Tiplerini Devre Dışı Bırakarak PDF Boyutunu Azaltın
linktitle: Gömülü Yazı Tiplerini Devre Dışı Bırakarak PDF Boyutunu Azaltın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile belgeleri PDF'ye dönüştürürken Windows yazı tipi yerleştirmeyi devre dışı bırakarak PDF boyutunu nasıl küçülteceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

Bu eğitimde, Aspose.Words for .NET ile bir PDF belgesine Windows yazı tipi yerleştirmeyi devre dışı bırakarak PDF boyutunu küçültme adımlarında size yol göstereceğiz. Yazı tipi yerleştirmeyi devre dışı bırakarak oluşturulan PDF dosyasının boyutunu azaltabilirsiniz. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme

PDF'ye dönüştürmek istediğiniz belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Belgenizin doğru yolunu belirttiğinizden emin olun.

## 2. Adım: PDF kaydetme seçeneklerini ayarlayın

PdfSaveOptions sınıfının bir örneğini oluşturun ve yazı tiplerinin nasıl gömüleceğini belirtin:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Bu seçenek, Windows yazı tiplerinin oluşturulan PDF dosyasına entegrasyonunu devre dışı bırakmanıza olanak tanır.

## 3. Adım: Belgeyi PDF'ye Dönüştürün

 Kullan`Save` Dönüştürme seçeneklerini belirterek belgeyi PDF'ye dönüştürme yöntemi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Dönüştürülen PDF'yi kaydetmek için doğru yolu belirttiğinizden emin olun.

### Aspose.Words for .NET Kullanarak Windows Yazı Tiplerini Gömmeyi Devre Dışı Bırakma için örnek kaynak kodu

Aspose.Words for .NET ile Windows yazı tiplerini PDF belgesine yerleştirmeyi devre dışı bırakmak için tam kaynak kodunu burada bulabilirsiniz:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Çıktı PDF'si standart Windows yazı tipleri eklenmeden kaydedilecektir.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Bu adımları izleyerek Aspose.Words for .NET ile Windows yazı tiplerinin PDF belgesine yerleştirilmesini kolayca devre dışı bırakabilirsiniz.


## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak Windows yazı tiplerini yerleştirmeyi devre dışı bırakarak bir PDF dosyasının boyutunu nasıl azaltacağımızı öğrendik. Yazı tipi yerleştirmeyi devre dışı bırakarak, oluşturulan PDF dosyasının boyutunu küçültebilir, böylece dosyaların saklanmasını, paylaşılmasını ve aktarılmasını kolaylaştırabilirsiniz. Ancak Windows yazı tipi yerleştirmeyi devre dışı bırakmanın son PDF belgesinde görünüm ve biçimlendirme değişikliklerine neden olabileceğini unutmamak önemlidir. Bu özelliği kullanırken bu sonuçları dikkate aldığınızdan emin olun. PDF dosyalarınızın oluşturulmasını optimize etmek için Aspose.Words for .NET'in diğer özelliklerini keşfetmekten çekinmeyin.

### Sıkça Sorulan Sorular

#### S: PDF belgesine Windows yazı tipi yerleştirmeyi devre dışı bırakmak nedir ve neden önemlidir?
C: Bir PDF belgesine Windows yazı tipi yerleştirmeyi devre dışı bırakmak, Windows yazı tiplerinin oluşturulan PDF dosyasına dahil edilmesini engelleme işlemidir. Bu, gömülü Windows yazı tipi verilerini kaldırarak PDF dosyasının boyutunu azaltır. Bu, PDF dosyalarının boyutunun küçültülmesi açısından önemli olabilir; bu da onların daha hızlı saklanmasını, paylaşılmasını ve aktarılmasını kolaylaştırabilir.

#### S: Aspose.Words for .NET kullanarak bir PDF belgesine Windows yazı tipi yerleştirmeyi nasıl devre dışı bırakabilirim?
C: Aspose.Words for .NET kullanarak Windows yazı tiplerini PDF belgesine yerleştirmeyi devre dışı bırakmak için şu adımları izleyin:

 PDF'ye dönüştürmek istediğiniz belgeyi kullanarak yükleyin.`Document` sınıf ve belge yolu.

 Bir örneğini oluşturun`PdfSaveOptions`sınıfı seçin ve ayarlayın`FontEmbeddingMode` mülkiyet`PdfFontEmbeddingMode.EmbedNone`. Bu, Windows yazı tiplerinin oluşturulan PDF dosyasına yerleştirilmesini devre dışı bırakır.

 Kullan`Save` yöntemi`Document` Daha önce yapılandırılan dönüştürme seçeneklerini belirterek belgeyi PDF'ye dönüştürmek için nesneyi seçin.

#### S: Bir PDF belgesine Windows yazı tipi yerleştirmeyi devre dışı bırakmanın faydaları nelerdir?
C: Bir PDF belgesine Windows yazı tipi yerleştirmeyi devre dışı bırakmanın faydaları şunlardır:

Küçültülmüş PDF dosyası boyutu: Windows yazı tipi yerleştirmeyi devre dışı bıraktığınızda, gömülü Windows yazı tipi verileri kaldırılır ve oluşturulan PDF dosyasının boyutu küçültülür.

Daha kolay depolama: Daha küçük PDF dosyalarının saklanması, kaydedilmesi ve aktarılması daha kolaydır.

Daha hızlı paylaşım ve aktarım: Daha küçük PDF dosyaları daha hızlı paylaşılıp aktarılabilir, böylece zamandan ve kaynaklardan tasarruf sağlanır.

#### S: Bir PDF belgesine Windows yazı tipi yerleştirmeyi devre dışı bırakmanın sonuçları nelerdir?
C: Windows yazı tiplerinin PDF belgesine yerleştirilmesinin devre dışı bırakılması aşağıdaki gibi sonuçlara yol açabilir:

Görünüm ve biçim kaybı: Belgede belirtilen Windows yazı tipleri, PDF'nin açıldığı sistemde mevcut değilse, yedek yazı tipleri kullanılacaktır, bu da hatalı görünüm ve biçimlendirmeye neden olabilir. şekli beklenenden farklı.

Okunabilirlik sorunları: Kullanılan yedek yazı tipleri orijinal yazı tipleri kadar okunabilir değilse, bu durum PDF belgesindeki metnin okunabilirliğini etkileyebilir.