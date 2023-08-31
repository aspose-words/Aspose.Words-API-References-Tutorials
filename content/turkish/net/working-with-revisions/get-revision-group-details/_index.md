---
title: Revizyon Grubu Detaylarını Al
linktitle: Revizyon Grubu Detaylarını Al
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile revizyon grubu ayrıntılarını bir Word belgesinden alın.
type: docs
weight: 10
url: /tr/net/working-with-revisions/get-revision-group-details/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir Word belgesindeki bir grup revizyonun ayrıntılarına nasıl ulaşacağınızı göstereceğiz. Size kaynak kodunun tamamını sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi yükleme

İlk adım, revizyonları içeren belgeyi yüklemektir.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2. Adım: Düzeltmelere göz atın

Daha sonra, belgede bulunan düzeltmeler arasında geçiş yapacağız ve bunların tür, yazar, tarih ve düzeltilmiş metin gibi ayrıntılarını görüntüleyeceğiz.

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


### Aspose.Words for .NET kullanarak Revizyon Grubu Detaylarını Alma için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir belgedeki bir grup revizyonun ayrıntılarını almak için tam kaynak kodu burada bulabilirsiniz:

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

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki bir grup revizyonun ayrıntılarına nasıl ulaşacağımızı öğrendik. Bir döngü ve uygun özellikleri kullanarak revizyon türü, yazar, tarih ve revize edilen metin gibi ayrıntıları görüntüleyebildik. Aspose.Words for .NET, revizyon yönetimi de dahil olmak üzere Word belgelerinin işlenmesi için birçok güçlü özellik sunar. Artık bu bilgiyi, Aspose.Words for .NET'i kullanarak revizyon grubu ayrıntılarını kendi Word belgelerinize almak için kullanabilirsiniz.

### SSS'ler

#### S: Revizyonları olan bir belgeyi Aspose.Words for .NET'e nasıl yüklerim?

 C: Kullan`Document`Revizyonları içeren bir dosyadan belge yüklemek için Aspose.Words for .NET sınıfı. Tam belge yolunu belirtebilirsiniz.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### S: Aspose.Words for .NET'te bir revizyon grubunun ayrıntılarını nasıl edinebilirim?

 C: Bir döngü kullanarak belgenin revizyonlarını gözden geçirin ve istediğiniz ayrıntıları elde etmek için her revizyonun özelliklerine erişin. Şunu kullanabilirsiniz:`RevisionType`, `Author`, `DateTime` Ve`ParentNode` sırasıyla revizyon türünü, yazarı, tarihi ve revize edilen metni almak için özellikler.

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

 C: Kullan`Group` mülkiyeti`Revision` Bir revizyonun bir gruba ait olup olmadığını kontrol etmek için nesne. Eğer`Group` mülkiyet`null`revizyonun herhangi bir gruba ait olmadığı anlamına gelir.

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