---
title: 1Bpp Dizine Alınmış Biçim
linktitle: 1Bpp Dizine Alınmış Biçim
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesini 1Bpp dizinli görüntüye nasıl dönüştüreceğinizi öğrenin. Kolay dönüşüm için adım adım kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
## giriiş

Bir Word belgesini yalnızca birkaç satır kodla siyah beyaz resim olarak nasıl kaydedeceğinizi hiç merak ettiniz mi? Şanslısın! Bugün, Aspose.Words for .NET'i kullanarak belgelerinizi 1Bpp dizinli görüntülere dönüştürmenize olanak tanıyan küçük ve güzel bir numaraya dalıyoruz. Bu format, belirli dijital arşivleme ve yazdırma türleri için veya yerden tasarruf etmeniz gerektiğinde mükemmeldir. Bunu pasta kadar kolaylaştırmak için her adımı parçalara ayıracağız. Başlamaya hazır mısınız? Hadi dalalım!

## Önkoşullar

Ellerimizi kirletmeden önce, elimizde olması gereken birkaç şey var:

-  Aspose.Words for .NET: Kütüphanenin kurulu olduğundan emin olun. Yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
- .NET Geliştirme Ortamı: Visual Studio iyi bir seçenektir ancak kendinizi rahat hissettiğiniz herhangi bir ortamı kullanabilirsiniz.
- Temel C# Bilgisi: Endişelenmeyin, konuyu basit tutacağız, ancak C#'a biraz aşina olmak yardımcı olacaktır.
- Bir Word Belgesi: Dönüştürülmeye hazır örnek bir Word belgesine sahip olun.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktarmamız gerekiyor. Bu, Aspose.Words'ten ihtiyacımız olan sınıflara ve yöntemlere erişmemizi sağladığı için çok önemlidir.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1. Adım: Belge Dizininizi Kurun

Belge dizininizin yolunu belirtmeniz gerekecektir. Burası Word belgenizin saklandığı ve dönüştürülen görüntünün kaydedileceği yerdir.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Word Belgesini Yükleyin

 Şimdi Word belgesini Aspose.Words'e yükleyelim`Document` nesne. Bu nesne Word dosyanızı temsil eder ve onu değiştirmenize olanak tanır.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: Görüntü Kaydetme Seçeneklerini Yapılandırın

 Daha sonra, ayarlamamız gerekiyor`ImageSaveOptions`Sihrin gerçekleştiği yer burasıdır. Görüntüyü 1Bpp indeksli renk moduyla PNG formatında kaydedecek şekilde yapılandıracağız.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1),
    ImageColorMode = ImageColorMode.BlackAndWhite,
    PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

- SaveFormat.Png: Bu, belgeyi PNG görüntüsü olarak kaydetmek istediğimizi belirtir.
- PageSet(1): Bu sadece ilk sayfayı dönüştürdüğümüzü gösterir.
- ImageColorMode.BlackAndWhite: Bu, görüntüyü siyah beyaza ayarlar.
- ImagePixelFormat.Format1bppIndexed: Bu, görüntü formatını 1Bpp indeksli olarak ayarlar.

## Adım 4: Belgeyi Görüntü Olarak Kaydetme

 Son olarak belgeyi kullanarak resim olarak kaydediyoruz.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak Word belgenizi yalnızca birkaç satır kodla 1Bpp indeksli bir görüntüye dönüştürdünüz. Bu yöntem, belgelerinizden yüksek kontrastlı, yerden tasarruf sağlayan görüntüler oluşturmak için inanılmaz derecede kullanışlıdır. Artık bunu projelerinize ve iş akışlarınıza kolayca entegre edebilirsiniz. Mutlu kodlama!

## SSS'ler

### 1Bpp indeksli görsel nedir?
1Bpp (Piksel Başına 1 Bit) indekslenmiş görüntü, her pikselin 0 veya 1 gibi tek bir bit ile temsil edildiği siyah beyaz bir görüntü formatıdır. Bu format, alan açısından oldukça verimlidir.

### Bir Word belgesinin birden fazla sayfasını aynı anda dönüştürebilir miyim?
 Evet yapabilirsin. Değiştir`PageSet` içindeki mülk`ImageSaveOptions` birden fazla sayfayı veya belgenin tamamını eklemek için.

### Aspose.Words for .NET'i kullanmak için lisansa ihtiyacım var mı?
 Evet, Aspose.Words for .NET tam işlevsellik için lisans gerektirir. Alabilirsin[geçici lisans burada](https://purchase.aspose.com/temporary-license/).

### Word belgemi başka hangi görüntü formatlarına dönüştürebilirim?
 Aspose.Words, JPEG, BMP ve TIFF dahil olmak üzere çeşitli görüntü formatlarını destekler. Basitçe değiştirin`SaveFormat` içinde`ImageSaveOptions`.

### Aspose.Words for .NET hakkında daha fazla belgeyi nerede bulabilirim?
 Ayrıntılı belgeleri şu adreste bulabilirsiniz:[Aspose.Words for .NET dokümantasyon sayfası](https://reference.aspose.com/words/net/).
