---
title: Revizyon Gruplarını Alın
linktitle: Revizyon Gruplarını Alın
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinde revizyon grupları alın.
type: docs
weight: 10
url: /tr/net/working-with-revisions/get-revision-groups/
---

Bu adım adım kılavuzda, size Aspose.Words for .NET kullanarak bir Word belgesindeki revizyon gruplarını nasıl alacağınızı anlatacağız. Size tam kaynak kodunu sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi yükleme

İlk adım, revizyonları içeren belgeyi yüklemektir.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2. Adım: Revizyon Gruplarına Göz Atın

Ardından, belgede bulunan düzeltme grupları arasında dolaşacağız ve yazar, düzeltme türü ve düzeltilmiş metin gibi ayrıntılarını göstereceğiz.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Aspose.Words for .NET kullanarak Get Revision Groups için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir belgedeki revizyon gruplarını almak için eksiksiz kaynak kodu burada:

```csharp

	Document doc = new Document(MyDir + "Revisions.docx");

	foreach(RevisionGroup group in doc.Revisions.Groups)
	{
		 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
		 Console.WriteLine(group.Text);
	}
	
```


