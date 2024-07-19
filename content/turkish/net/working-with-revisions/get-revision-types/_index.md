---
title: Kelime Türlerinin Revizyonunu Alın
linktitle: Kelime Türlerinin Revizyonunu Alın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgesindeki kelimelerin revizyon türlerini alın.
type: docs
weight: 10
url: /tr/net/working-with-revisions/get-revision-types/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir Word belgesindeki kelime revizyonlarının türlerini nasıl alacağınızı anlatacağız. Size kaynak kodunun tamamını sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi yükleme

İlk adım, revizyonları içeren belgeyi yüklemektir.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Adım 2: Paragraflarda ilerleyin

Daha sonra belgenin paragraflarını inceleyeceğiz ve her paragrafla ilişkili kelime revizyon türlerini kontrol edeceğiz.

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

### Aspose.Words for .NET kullanarak Revizyon Tiplerini Al için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir belgede revizyon türlerini almak için tam kaynak kodu:

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

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki kelime revizyon türlerinin nasıl alınacağını öğrendik. Belgeyi yüklemek, paragrafları gözden geçirmek ve her paragrafla ilişkili kelime incelemesi türlerini kontrol etmek için gerekli adımları izledik. Artık bu bilgiyi Aspose.Words for .NET kullanarak kendi Word belgelerinizdeki kelime incelemelerini analiz etmek için uygulayabilirsiniz.

### Kelimelerin revizyon türlerini almak için SSS'ler

#### S: Aspose.Words for .NET'e belge nasıl yüklenir?

 C: Kullan`Document` Bir dosyadan belge yüklemek için Aspose.Words for .NET sınıfı. Tam belge yolunu belirtebilirsiniz.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### S: Aspose.Words for .NET'te bir belgedeki paragraflar arasında nasıl geçiş yapabilirim?

 C: Kullan`Paragraphs` paragrafların koleksiyonunu almak için belge bölümünün özelliği. Daha sonra her paragrafta döngü yapmak için bir döngü kullanabilirsiniz.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Her paragrafı burada işleyin
}
```

#### S: Aspose.Words for .NET'te bir paragrafın taşınıp taşınmadığı (silindiği) nasıl kontrol edilir?

 C: Bir paragraf kullanın`IsMoveFromRevision`taşınıp taşınmadığını (silinip silinmediğini) kontrol etmek için özellik.

```csharp
if (paragraph. IsMove

FromRevision)
{
     // Paragraf taşındı (silindi)
}
```

#### S: Aspose.Words for .NET'te bir paragrafın taşınıp taşınmadığını (eklendiğini) nasıl kontrol edebilirim?

 C: Bir paragraf kullanın`IsMoveToRevision` taşınıp taşınmadığını (eklenip eklenmediğini) kontrol etmek için özellik.

```csharp
if (paragraph.IsMoveToRevision)
{
     // Paragraf taşındı (eklendi)
}
```