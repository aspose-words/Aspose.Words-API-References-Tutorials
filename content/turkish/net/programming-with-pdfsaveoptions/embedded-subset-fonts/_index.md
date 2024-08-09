---
title: Alt Küme Yazı Tiplerini PDF Belgesine Göm
linktitle: Alt Küme Yazı Tiplerini PDF Belgesine Göm
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak yalnızca gerekli yazı tipi alt kümelerini yerleştirerek PDF dosya boyutunu küçültün. PDF'lerinizi verimli bir şekilde optimize etmek için adım adım kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---
## giriiş

Benzer içeriğe sahip olsalar bile bazı PDF dosyalarının diğerlerinden çok daha büyük olduğunu hiç fark ettiniz mi? Suçlu genellikle yazı tiplerindedir. Yazı tiplerini bir PDF'ye gömmek, her aygıtta aynı görünmesini sağlar ancak aynı zamanda dosya boyutunu da şişirebilir. Neyse ki Aspose.Words for .NET, yalnızca gerekli yazı tipi alt kümelerini gömmek için kullanışlı bir özellik sunarak PDF'lerinizi yalın ve verimli tutar. Bu eğitim size süreç boyunca adım adım rehberlik edecektir.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET: İndirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
- .NET Ortamı: Çalışan bir .NET geliştirme ortamına sahip olduğunuzdan emin olun.
- Temel C# Bilgisi: C# programlamaya aşinalık, takip etmenize yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Aspose.Words for .NET'i kullanmak için projenize gerekli ad alanlarını içe aktarmanız gerekir. Bunları C# dosyanızın en üstüne ekleyin:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## 1. Adım: Belgeyi Yükleyin

 Öncelikle PDF'e dönüştürmek istediğimiz Word belgesini yüklememiz gerekiyor. Bu, kullanılarak yapılır.`Document` Aspose.Words tarafından sağlanan sınıf.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Bu kod parçacığı şu adreste bulunan belgeyi yükler:`dataDir` . Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` belgenizin gerçek yolu ile.

## 2. Adım: PDF Kaydetme Seçeneklerini Yapılandırın

 Daha sonra, yapılandırıyoruz`PdfSaveOptions` yalnızca gerekli yazı tipi alt kümelerinin gömülmesini sağlamak için. Ayarlayarak`EmbedFullFonts` ile`false`Aspose.Words'e yalnızca belgede kullanılan glifleri yerleştirmesini söyleriz.

```csharp
// Çıktı PDF'si, belgedeki yazı tiplerinin alt kümelerini içerecektir.
// Yalnızca belgede kullanılan glifler PDF yazı tiplerine dahil edilir.
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

Bu küçük ama önemli adım, PDF dosya boyutunun önemli ölçüde azaltılmasına yardımcı olur.

## 3. Adım: Belgeyi PDF olarak kaydedin

 Son olarak belgeyi PDF olarak kaydediyoruz.`Save` yapılandırılmış yöntemi uygulayarak`PdfSaveOptions`.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbedSubsetFonts.pdf", saveOptions);
```

 Bu kod adında bir PDF dosyası oluşturacaktır.`WorkingWithPdfSaveOptions.EmbedSubsetFonts.pdf` belirtilen dizinde, yalnızca gerekli yazı tipi alt kümeleri gömülü olarak.

## Çözüm

Ve işte karşınızda! Bu basit adımları izleyerek, Aspose.Words for .NET'i kullanarak yalnızca gerekli yazı tipi alt kümelerini gömerek PDF dosyalarınızın boyutunu etkili bir şekilde azaltabilirsiniz. Bu yalnızca depolama alanından tasarruf etmekle kalmaz, aynı zamanda özellikle geniş yazı tiplerine sahip belgeler için daha hızlı yükleme süreleri ve daha iyi performans sağlar.

## SSS'ler

### Bir PDF'ye neden yalnızca yazı tipi alt kümelerini gömmeliyim?
Yalnızca gerekli yazı tipi alt kümelerini gömmek, belgenin görünümünden ve okunabilirliğinden ödün vermeden PDF dosya boyutunu önemli ölçüde azaltabilir.

### Gerekirse tam yazı tiplerini yerleştirmeye geri dönebilir miyim?
 Evet yapabilirsin. Basitçe ayarlayın`EmbedFullFonts`mülkiyet`true` içinde`PdfSaveOptions`.

### Aspose.Words for .NET diğer PDF optimizasyon özelliklerini destekliyor mu?
Kesinlikle! Aspose.Words for .NET, PDF'leri optimize etmek için görüntü sıkıştırma ve kullanılmayan nesnelerin kaldırılması da dahil olmak üzere çeşitli seçenekler sunar.

### Aspose.Words for .NET kullanılarak ne tür yazı tipleri alt kümeye gömülebilir?
Aspose.Words for .NET, belgede kullanılan tüm TrueType yazı tipleri için alt küme yerleştirmeyi destekler.

### PDF'ime hangi yazı tiplerinin gömülü olduğunu nasıl doğrulayabilirim?
PDF'yi Adobe Acrobat Reader'da açabilir ve gömülü yazı tiplerini görmek için Yazı Tipleri sekmesi altındaki özellikleri kontrol edebilirsiniz.
