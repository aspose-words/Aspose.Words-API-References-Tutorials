---
title: Revizyon Türlerini Alın
linktitle: Revizyon Türlerini Alın
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesindeki revizyon türlerini alın.
type: docs
weight: 10
url: /tr/net/working-with-revisions/get-revision-types/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir Word belgesindeki revizyon türlerini nasıl alacağınızı anlatacağız. Size tam kaynak kodunu sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi yükleme

İlk adım, revizyonları içeren belgeyi yüklemektir.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2. Adım: Paragraflar arasında geçiş yapın

Ardından, belgenin paragraflarını gözden geçireceğiz ve her paragrafla ilişkili düzeltme türlerini kontrol edeceğiz.

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
