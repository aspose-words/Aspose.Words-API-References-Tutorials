---
title: Revizyon Grubu Ayrıntılarını Alın
linktitle: Revizyon Grubu Ayrıntılarını Alın
second_title: Aspose.Words Belge İşleme API'sı
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

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki bir grup revizyonun ayrıntılarını nasıl alacağımızı öğrendik. Bir döngü ve uygun özellikleri kullanarak revizyon tipi, yazar, tarih ve revize edilmiş metin gibi detayları görüntüleyebildik. Aspose.Words for .NET, revizyon yönetimi de dahil olmak üzere Word belgelerini işlemek için birçok güçlü özellik sunar. Aspose.Words for .NET'i kullanarak artık bu bilgiyi revizyon grubu ayrıntılarını kendi Word belgelerinize almak için kullanabilirsiniz.

### SSS

#### S: Revizyonlu bir belgeyi Aspose.Words for .NET'e nasıl yüklerim?

 C: Şunu kullanın:`Document`revizyonlar içeren bir dosyadan belge yüklemek için Aspose.Words for .NET sınıfı. Tam belge yolunu belirleyebilirsiniz.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### S: Aspose.Words for .NET'te bir revizyon grubunun ayrıntılarını nasıl edinebilirim?

 A: Bir döngü kullanarak belgenin revizyonlarını gözden geçirin ve istediğiniz ayrıntıları elde etmek için her revizyonun özelliklerine erişin. kullanabilirsiniz`RevisionType`, `Author`, `DateTime` Ve`ParentNode` sırasıyla revizyon türü, yazar, tarih ve revize edilmiş metni almak için özellikler.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### S: Aspose.Words for .NET'te bir revizyonun bir gruba ait olup olmadığı nasıl kontrol edilir?

 C: Şunu kullanın:`Group` mülkiyeti`Revision` Bir revizyonun bir gruba ait olup olmadığını kontrol etmek için nesne. Eğer`Group` özellik`null`revizyonun herhangi bir gruba ait olmadığı anlamına gelir.

```csharp
if (revision.Group != null)
{
      // Revizyon bir gruba ait
}
else
{
      // Revizyon herhangi bir gruba ait değil
}
```