---
title: DrawingML Metin Efektini Kontrol Edin
linktitle: DrawingML Metin Efektini Kontrol Edin
second_title: Aspose.Words for .NET API Referansı
description: Bu eğitimde, Aspose.Words for .NET ile bir Word belgesindeki DrawingML metin efektlerini nasıl kontrol edeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/check-drawingml-text-effect/
---

Bu eğitimde, Aspose.Words Library for .NET kullanarak bir Word belgesinde DrawingML metin efektlerini nasıl kontrol edeceğinizi anlatacağız. DrawingML metin efektlerini kontrol etmek, metnin bir kısmına belirli bir efektin uygulanıp uygulanmadığını belirlemenizi sağlar. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı
- DrawingML metin efektleri içeren bir Word belgesi

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, dizin yolunu Word belgenizin konumuna ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin ve metin efektlerini kontrol edin
Ardından, Word belgesini yükleyeceğiz ve belge gövdesinin ilk paragrafındaki çalıştırmalar (karakter dizileri) koleksiyonuna erişeceğiz. Ardından, ilk çalıştırmanın yazı tipine herhangi bir belirli DrawingML metin efektinin uygulanıp uygulanmadığını kontrol edeceğiz.

```csharp
//belgeyi yükle
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// DrawingML metin efektlerini kontrol edin
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Aspose.Words for .NET kullanarak Check DMLText Effect için örnek kaynak kodu 

```csharp

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Bir çalıştırmada birkaç Dml metin efekti uygulanmış olabilir.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Çözüm
Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinde DrawingML metin efektlerinin nasıl kontrol edileceğini gördük. DrawingML metin efektlerini kontrol etmek, metnin belirli efektleri uygulanmış kısımlarını tanımlamanıza olanak tanır. Word belgelerinizdeki metin efektlerini işlemek ve analiz etmek için bu özelliği kullanmaktan çekinmeyin.

### SSS

#### S: Aspose.Words kullanarak bir Word belgesindeki DrawingML metin efektlerine nasıl erişebilirim?

Y: Aspose.Words ile, sağlanan API'yi kullanarak bir Word belgesindeki DrawingML metin efektlerine erişebilirsiniz. Metin öğelerine göz atabilir ve metin efektlerinin renk, boyut vb. belirli özelliklerini kontrol edebilirsiniz.

#### S: Word belgelerinde yaygın olarak ne tür DrawingML metin efektleri kullanılır?

A: Word belgelerinde yaygın olarak kullanılan DrawingML metin efektleri türleri arasında gölgeler, yansımalar, parlamalar, degradeler vb. bulunur. Bu efektler, metnin görünümünü ve biçimlendirmesini iyileştirmek için uygulanabilir.

#### S: Bir Word belgesindeki DrawingML metin efektinin rengini nasıl kontrol edebilirim?

A: Bir Word belgesindeki DrawingML metin efektinin rengini kontrol etmek için Aspose.Words tarafından metin efektinin renk özelliklerine erişmek için sağlanan yöntemleri kullanabilirsiniz. Bu şekilde, belirli metin efekti için kullanılan rengi elde edebilirsiniz.

#### S: Birden çok bölüm içeren Word belgelerinde metin efektlerini kontrol etmek mümkün mü?

C: Evet, Aspose.Words, birden fazla bölüm içeren Word belgelerinde metin efektlerinin kontrol edilmesini sağlar. Belgenin her bölümünde gezinebilir ve her bölüm için ayrı ayrı metin efektlerine erişebilirsiniz.

#### S: Bir Word belgesinde DrawingML metin efektinin opaklığını nasıl kontrol edebilirim?

C: Bir Word belgesindeki DrawingML metin efektinin opaklığını kontrol etmek için, metin efektinin opaklık özelliklerine erişmek için Aspose.Words tarafından sağlanan yöntemleri kullanabilirsiniz. Bu, belirli metin efektine uygulanan opaklık değerini elde etmenizi sağlayacaktır.