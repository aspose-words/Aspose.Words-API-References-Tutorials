---
title: Alt Küme Yazı Tiplerini PDF Belgesine Göm
linktitle: Alt Küme Yazı Tiplerini PDF Belgesine Göm
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak yazı tipi alt kümelerini bir PDF belgesine gömmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Bu makale, yazı tipi alt kümesi gömme özelliğinin Aspose.Words for .NET ile nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, yazı tiplerinin alt kümelerini bir belgeye nasıl gömeceğinizi ve yalnızca belgede kullanılan glifleri içeren bir PDF oluşturmayı öğrenebileceksiniz.

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

## 3. Adım: PDF olarak kaydetme seçeneklerini yapılandırın

 Yalnızca belgede kullanılan yazı tiplerinin alt kümelerini içeren bir PDF oluşturmak için,`PdfSaveOptions` ile nesne`EmbedFullFonts` özellik ayarlandı`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## 4. Adım: Belgeyi yazı tipi alt kümeleriyle PDF olarak kaydedin

 Son olarak, yazı tipi alt kümelerini kullanarak belgeyi PDF olarak kaydedebiliriz. Çıktı dosyası adını ve`saveOptions` önceki adımda yapılandırdığımız nesne.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Bu kadar ! Yazı tiplerinin alt kümelerini bir belgeye başarıyla gömdünüz ve Aspose.Words for .NET ile yalnızca belgede kullanılan glifleri içeren bir PDF oluşturdunuz.

### Aspose.Words for .NET ile yazı tipi alt kümelerini gömmek için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Çıktı PDF'si, belgedeki yazı tiplerinin alt kümelerini içerecektir.
	// PDF yazı tiplerine yalnızca belgede kullanılan glifler dahildir.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak yazı tipi altkümelerini bir PDF belgesine nasıl gömeceğimizi öğrendik. Yazı tiplerinin alt kümelerini gömmek, yalnızca gerçekte kullanılan karakterleri kullanarak belgenin görünümünü korurken PDF dosyasının boyutunun küçültülmesine yardımcı olur. Bu, PDF'yi görüntülerken ve yazdırırken daha iyi uyumluluk ve performans sağlar. Aspose.Words for .NET'in özelliklerini, gömülü yazı tipi altkümeleri ile PDF belgelerinizin üretimini optimize etmek için daha fazla keşfetmekten çekinmeyin.

### Sıkça Sorulan Sorular

#### S: Yazı tipi alt kümelerini bir PDF belgesine gömmek nedir?
Y: Bir PDF belgesine yazı tipi alt kümelerini gömmek, tüm yazı tiplerini dahil etmek yerine yalnızca belgede kullanılan glifleri dahil etme işlemidir. Bu, yalnızca belgede fiilen kullanılan karakterleri görüntülemek için gerekli olan yazı tipi verilerini dahil ederek PDF dosyasının boyutunu azaltır.

#### S: Tam yazı tiplerini gömme ile yazı tiplerinin alt kümelerini gömme arasındaki fark nedir?
C: Tam yazı tipi gömme, belgede kullanılan tüm yazı tiplerinin PDF dosyasına dahil edilmesi anlamına gelir; bu, belgenin tam olarak tasarlandığı gibi görüntülenmesini sağlar, ancak PDF dosyasının boyutunu artırabilir. Buna karşılık, gömme yazı tipi alt kümeleri yalnızca belgede kullanılan glifleri içerir, bu nedenle PDF dosyasının boyutu küçülür, ancak daha sonra ek karakterler eklenirse belgenin görünümünü tam olarak çoğaltma yeteneği sınırlanır.

#### S: Aspose.Words for .NET kullanarak yazı tipi altkümelerini bir PDF belgesine nasıl gömebilirim?
C: Aspose.Words for .NET kullanarak bir PDF belgesine yazı tipi alt kümelerini gömmek için şu adımları izleyin:

 Değiştirerek belge dizini yolunu ayarlayın`"YOUR DOCUMENT DIRECTORY"` belgeler dizininizin gerçek yolu ile.

 kullanarak işlemek istediğiniz belgeyi yükleyin.`Document` sınıf ve belge yolu.

 örneğini oluşturarak PDF kaydetme seçeneklerini yapılandırın.`PdfSaveOptions` sınıf ve ayar`EmbedFullFonts` mülkiyet`false`Bu, yalnızca belgede kullanılan yazı tipi alt kümelerinin PDF dosyasına dahil edilmesini sağlar.

 kullanarak gömülmüş yazı tipi altkümeleri ile belgeyi PDF formatında kaydedin.`Save` yöntemi`Document` çıktı dosyasının adını ve daha önce yapılandırılan kaydetme seçeneklerini belirterek.

#### S: Yazı tipi alt kümelerini bir PDF belgesine gömmenin faydaları nelerdir?
C: Yazı tipi alt kümelerini bir PDF belgesine gömmenin faydaları şunlardır:

Küçültülmüş PDF dosya boyutu: Yalnızca belgede kullanılan glifleri dahil ederek, PDF dosya boyutu, tam yazı tiplerinin gömülmesine kıyasla küçültülür.

Belgenin görünümünün korunması: PDF dosyasında yer alan yazı tiplerinin alt kümeleri, yalnızca gerçekten kullanılan karakterleri kullanarak belgenin görünümünü yeniden oluşturmayı mümkün kılar.

Lisans kısıtlamalarıyla uyumluluk: Lisanslama kısıtlamaları nedeniyle tam yazı tiplerinin yasal olarak gömülemediği durumlarda, yazı tiplerinin alt kümelerinin gömülmesi tercih edilebilir.