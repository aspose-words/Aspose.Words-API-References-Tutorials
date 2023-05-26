---
title: Revizyon Grubu Ayrıntılarını Alın
linktitle: Revizyon Grubu Ayrıntılarını Alın
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinde revizyon grubu ayrıntılarını alın.
type: docs
weight: 10
url: /tr/net/working-with-revisions/get-revision-group-details/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir Word belgesindeki bir revizyon grubunun ayrıntılarını nasıl alacağınızı göstereceğiz. Size tam kaynak kodunu sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi yükleme

İlk adım, revizyonları içeren belgeyi yüklemektir.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2. Adım: Düzeltmelere göz atın

Ardından, belgede bulunan düzeltmeler arasında dolaşacağız ve tür, yazar, tarih ve düzeltilmiş metin gibi ayrıntılarını göstereceğiz.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Aspose.Words for .NET kullanarak Revizyon Grubu Ayrıntılarını Al için örnek kaynak kodu

Aspose.Words for .NET kullanan bir belgedeki bir grup revizyonun ayrıntılarını almak için eksiksiz kaynak kodu burada:

```csharp

	Document doc = new Document(MyDir + "Revisions.docx");

	foreach (Revision revision in doc.Revisions)
	{
		 string groupText = revision.Group != null
			 ? "Revision group text: " + revision.Group.Text
			 : "The revision does not belong to any group";

		 Console.WriteLine("Type: " + revision.RevisionType);
		 Console.WriteLine("Author: " + revision.Author);
		 Console.WriteLine("Date: " + revision.DateTime);
		 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
		 Console.WriteLine(groupText);
	}
	
```

