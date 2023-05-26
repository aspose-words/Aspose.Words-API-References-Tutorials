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
