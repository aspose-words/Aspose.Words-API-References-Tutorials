---
title: Revizyon Al Kelime Türleri
linktitle: Revizyon Al Kelime Türleri
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesindeki sözcüklerin düzeltme türlerini alın.
type: docs
weight: 10
url: /tr/net/working-with-revisions/get-revision-types/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir Word belgesindeki kelime türlerinin revizyonlarını nasıl alacağınızı anlatacağız. Size tam kaynak kodunu sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi yükleme

İlk adım, revizyonları içeren belgeyi yüklemektir.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2. Adım: Paragraflar arasında geçiş yapın

Daha sonra, belgenin paragraflarını gözden geçireceğiz ve her paragrafla ilişkili kelime revizyonlarının türlerini kontrol edeceğiz.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Aspose.Words for .NET kullanarak Revizyon Türlerini Al için örnek kaynak kodu

Aspose.Words for .NET kullanan bir belgede revizyon türlerini almak için tam kaynak kodu burada:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki kelime revizyonlarının nasıl alınacağını öğrendik. Belgeyi yükleme, paragrafları gözden geçirme ve her paragrafla ilişkili kelime inceleme türlerini kontrol etme adımlarını izledik. Artık bu bilgiyi, Aspose.Words for .NET kullanarak kendi Word belgelerinizdeki kelime incelemelerini analiz etmek için uygulayabilirsiniz.

### Revizyon kelime türleri için SSS

#### S: Aspose.Words for .NET'te bir belge nasıl yüklenir?

 C: Şunu kullanın:`Document` bir dosyadan belge yüklemek için Aspose.Words for .NET sınıfı. Tam belge yolunu belirleyebilirsiniz.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### S: Aspose.Words for .NET'te bir belgedeki paragraflar arasında nasıl dolaşırım?

 C: Şunu kullanın:`Paragraphs` Paragrafların toplanması için belge bölümünün özelliği. Daha sonra her paragrafta döngü yapmak için bir döngü kullanabilirsiniz.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Her paragrafı burada işleyin
}
```

#### S: Aspose.Words for .NET'te bir paragrafın taşınmış (silinmiş) olup olmadığı nasıl kontrol edilir?

 C: Bir paragraf kullanın`IsMoveFromRevision` taşınmış (silinmiş) olup olmadığını kontrol etmek için özellik.

```csharp
if (paragraph. IsMove

FromRevision)
{
     // Paragraf taşındı (silindi)
}
```

#### S: Aspose.Words for .NET'te bir paragrafın taşınmış (eklenmiş) olup olmadığı nasıl kontrol edilir?

 C: Bir paragraf kullanın`IsMoveToRevision`taşınmış (eklenmiş) olup olmadığını kontrol etmek için özellik.

```csharp
if (paragraph.IsMoveToRevision)
{
     // Paragraf taşındı (eklendi)
}
```