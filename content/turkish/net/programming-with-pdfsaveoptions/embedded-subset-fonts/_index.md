---
title: Alt Küme Yazı Tiplerini PDF Belgesine Göm
linktitle: Alt Küme Yazı Tiplerini PDF Belgesine Göm
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak yazı tipi alt kümelerini bir PDF belgesine gömmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Bu makale, Aspose.Words for .NET ile yazı tipi alt kümesi gömme özelliğinin nasıl kullanılacağı hakkında adım adım bir kılavuz sağlar. Kodun her bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, yazı tipi alt kümelerini bir belgeye nasıl yerleştireceğinizi ve yalnızca belgede kullanılan glifleri içeren bir PDF oluşturmayı anlayabileceksiniz.

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

## 3. Adım: PDF olarak kaydetme seçeneklerini yapılandırın

 Yalnızca belgede kullanılan yazı tiplerinin alt kümelerini içeren bir PDF oluşturmak için,`PdfSaveOptions` ile nesne`EmbedFullFonts` özellik şu şekilde ayarlandı:`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## 4. Adım: Belgeyi yazı tipi alt kümeleriyle PDF olarak kaydedin

 Son olarak yazı tipi alt kümelerini kullanarak belgeyi PDF olarak kaydedebiliriz. Çıktı dosyasının adını ve`saveOptions` önceki adımda yapılandırdığımız nesne.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Bu kadar ! Aspose.Words for .NET ile bir belgeye yazı tipi alt kümelerini başarıyla gömdünüz ve yalnızca belgede kullanılan glifleri içeren bir PDF oluşturdunuz.

### Aspose.Words for .NET ile yazı tipi alt kümelerini gömmek için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Çıktı PDF'si, belgedeki yazı tiplerinin alt kümelerini içerecektir.
	// Yalnızca belgede kullanılan glifler PDF yazı tiplerine dahil edilir.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak yazı tipi alt kümelerini bir PDF belgesine nasıl yerleştireceğimizi öğrendik. Yazı tipi alt kümelerinin gömülmesi, yalnızca gerçekte kullanılan karakterleri kullanarak belgenin görünümünü korurken PDF dosyasının boyutunun küçültülmesine yardımcı olur. Bu, PDF'yi görüntülerken ve yazdırırken daha iyi uyumluluk ve performans sağlar. Gömülü yazı tipi alt kümeleriyle PDF belgelerinizin oluşturulmasını optimize etmek için Aspose.Words for .NET'in özelliklerini daha fazla keşfetmekten çekinmeyin.

### Sıkça Sorulan Sorular

#### S: Yazı tipi alt kümelerini PDF belgesine gömmek nedir?
C: Yazı tipi alt kümelerini bir PDF belgesine gömmek, tüm yazı tiplerini tam olarak dahil etmek yerine yalnızca belgede kullanılan glifleri dahil etme işlemidir. Bu, yalnızca belgede gerçekten kullanılan karakterleri görüntülemek için gereken yazı tipi verilerini dahil ederek PDF dosyasının boyutunu azaltır.

#### S: Fontların tamamını gömmek ile yazı tiplerinin alt kümelerini gömmek arasındaki fark nedir?
C: Tam yazı tipi gömme, belgede kullanılan tüm yazı tiplerinin PDF dosyasına dahil edilmesi anlamına gelir; bu, belgenin tam olarak tasarlandığı gibi görüntülenmesini sağlar, ancak PDF dosyasının boyutunu artırabilir. Buna karşılık, gömme yazı tipi alt kümeleri yalnızca belgede kullanılan glifleri içerir, böylece PDF dosyasının boyutu küçülür, ancak daha sonra ek karakterler eklenirse belgenin görünümünü tam olarak kopyalama yeteneği sınırlanır.

#### S: Aspose.Words for .NET kullanarak yazı tipi alt kümelerini bir PDF belgesine nasıl gömebilirim?
C: Aspose.Words for .NET kullanarak yazı tipi alt kümelerini bir PDF belgesine gömmek için şu adımları izleyin:

 Belge dizini yolunu değiştirerek ayarlayın`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

 İşlemek istediğiniz belgeyi kullanarak yükleyin.`Document` sınıf ve belge yolu.

 Bir örneğini oluşturarak PDF kaydetme seçeneklerini yapılandırın.`PdfSaveOptions` sınıf ve ayarlama`EmbedFullFonts` mülkiyet`false`Bu, yalnızca belgede kullanılan yazı tipi alt kümelerinin PDF dosyasına dahil edilmesini sağlar.

 Belgeyi, yazı tipi alt kümeleri gömülü olarak PDF formatında kaydedin.`Save` yöntemi`Document` çıktı dosyasının adını ve daha önce yapılandırılan kaydetme seçeneklerini belirten nesne.

#### S: Yazı tipi alt kümelerini bir PDF belgesine yerleştirmenin faydaları nelerdir?
C: Yazı tipi alt kümelerini bir PDF belgesine yerleştirmenin faydaları şunlardır:

Küçültülmüş PDF dosya boyutu: Yalnızca belgede kullanılan gliflerin eklenmesiyle, tam yazı tiplerinin gömülmesine kıyasla PDF dosya boyutu küçültülür.

Belgenin görünümünün korunması: PDF dosyasında bulunan yazı tipi alt kümeleri, yalnızca gerçekte kullanılan karakterleri kullanarak belgenin görünümünü yeniden oluşturmayı mümkün kılar.

Lisans kısıtlamalarına uygunluk: Lisans kısıtlamaları nedeniyle yasal olarak tam yazı tiplerinin eklenemediği durumlarda yazı tiplerinin alt kümelerinin gömülmesi tercih edilebilir.