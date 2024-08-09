---
title: Görüntüleri Alt Örnekleme ile PDF Belge Boyutunu Azaltın
linktitle: Görüntüleri Alt Örnekleme ile PDF Belge Boyutunu Azaltın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak görüntüleri altörnekleyerek PDF belge boyutunu küçültün. Daha hızlı yükleme ve indirme süreleri için PDF'lerinizi optimize edin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/downsampling-images/
---
## giriiş

PDF'ler, belge paylaşımından e-Kitap oluşturmaya kadar her şey için kullanılan dijital dünyanın temelini oluşturur. Ancak boyutları, özellikle görsel açısından zengin içerikle uğraşırken bazen engel teşkil edebilir. Burada altörnekleme görüntüleri devreye giriyor. PDF'deki görsellerin çözünürlüğünü azaltarak kaliteden çok fazla ödün vermeden dosya boyutunu önemli ölçüde azaltabilirsiniz. Bu eğitimde Aspose.Words for .NET kullanarak bunu başarmak için gereken adımları inceleyeceğiz.

## Önkoşullar

Koda geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Words for .NET: Aspose.Words kütüphanesinin kurulu olduğundan emin olun. Değilse indirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio gibi herhangi bir .NET geliştirme ortamı.
3. Temel C# Bilgisi: C# programlamanın temellerini anlamak faydalı olacaktır.
4.  Örnek Belge: Bir Word belgesi (örn.`Rendering.docx`) PDF'ye dönüştürülecek resimlerle birlikte.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktarmanız gerekir. Bunları kod dosyanızın en üstüne ekleyin:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Şimdi süreci yönetilebilir adımlara ayıralım.

## 1. Adım: Belgeyi Yükleyin

İlk adım Word belgenizi yüklemektir. Belge dizininizin yolunu belirttiğiniz yer burasıdır.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Bu adımda, Word belgesini belirtilen dizinden yüklüyoruz. Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"`belgenizin bulunduğu gerçek yolla.

## Adım 2: Alt Örnekleme Seçeneklerini Yapılandırma

Daha sonra altörnekleme seçeneklerini yapılandırmamız gerekiyor. Bu, görüntüler için çözünürlüğün ve çözünürlük eşiğinin ayarlanmasını içerir.

```csharp
// Altörnekleme için minimum bir eşik ayarlayabiliriz.
// Bu değer, giriş belgesindeki ikinci görüntünün altörneklenmesini önleyecektir.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 Burada yeni bir örnek oluşturuyoruz`PdfSaveOptions` ve ayarlanması`Resolution` 36 DPI'ya ve`ResolutionThreshold` 128 DPI'ya kadar. Bu, çözünürlüğü 128 DPI'dan yüksek olan herhangi bir görüntünün 36 DPI'ya alt örnekleneceği anlamına gelir.

## 3. Adım: Belgeyi PDF olarak kaydedin

Son olarak, yapılandırılan seçeneklerle belgeyi PDF olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Bu son adımda, belgeyi belirtilen alt örnekleme seçenekleriyle aynı dizine PDF olarak kaydediyoruz.

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak görüntüleri altörnekleyerek PDF'nizin boyutunu başarıyla küçülttünüz. Bu yalnızca PDF'lerinizi daha kolay yönetilebilir hale getirmekle kalmaz, aynı zamanda daha hızlı yükleme, indirme ve daha sorunsuz görüntüleme deneyimlerine de yardımcı olur.

## SSS'ler

### Alt örnekleme nedir?
Altörnekleme, görüntülerin çözünürlüğünü azaltma işlemidir ve bu, bu görüntüleri içeren belgelerin dosya boyutunun azaltılmasına yardımcı olur.

### Altörnekleme görüntülerin kalitesini etkiler mi?
Evet, altörnekleme görüntü kalitesini düşürür. Ancak etki, çözünürlük azalmasının derecesine bağlıdır. Bu, dosya boyutu ile görüntü kalitesi arasındaki bir dengedir.

### Hangi görüntülerin alt örnekleneceğini seçebilir miyim?
 Evet, ayarlayarak`ResolutionThreshold`ile hangi görüntülerin orijinal çözünürlüklerine göre altörnekleneceğini kontrol edebilirsiniz.

### Altörnekleme için ideal çözünürlük nedir?
İdeal çözünürlük özel ihtiyaçlarınıza bağlıdır. Genellikle web görselleri için 72 DPI kullanılırken, baskı kalitesi için daha yüksek çözünürlükler kullanılır.

### Aspose.Words for .NET ücretsiz mi?
 Aspose.Words for .NET ticari bir üründür ancak ücretsiz deneme sürümünü indirebilirsiniz[Burada](https://releases.aspose.com/) veya başvuruda bulunun[geçici lisans](https://purchase.aspose.com/temporary-license/).