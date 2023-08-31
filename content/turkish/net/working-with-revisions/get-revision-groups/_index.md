---
title: Revizyon Gruplarını Alma
linktitle: Revizyon Gruplarını Alma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesindeki revizyon gruplarını alın.
type: docs
weight: 10
url: /tr/net/working-with-revisions/get-revision-groups/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir Word belgesindeki revizyon gruplarını nasıl alacağınızı anlatacağız. Size kaynak kodunun tamamını sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi yükleme

İlk adım, revizyonları içeren belgeyi yüklemektir.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Adım 2: Revizyon Gruplarına Göz Atın

Daha sonra belgede bulunan revizyon grupları arasında geçiş yapacağız ve bunların yazar, revizyon türü ve revize edilen metin gibi ayrıntılarını görüntüleyeceğiz.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Aspose.Words for .NET kullanarak Revizyon Gruplarını Al için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir belgedeki revizyon gruplarını almak için gereken kaynak kodun tamamı burada:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde revizyon gruplarının nasıl alınacağını öğrendik. Belgeyi yüklemek ve inceleme gruplarına göz atmak, yazar ve inceleme türü gibi ayrıntıları görüntülemek için adımları izledik. Artık bu bilgiyi Aspose.Words for .NET kullanarak kendi Word belgenizin revizyonlarını analiz etmek için uygulayabilirsiniz.

### SSS'ler

#### S: Aspose.Words for .NET'e belge nasıl yüklenir?

 C: Kullan`Document` Bir dosyadan belge yüklemek için Aspose.Words for .NET sınıfı. Tam belge yolunu belirtebilirsiniz.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### S: Aspose.Words for .NET'te bir belgedeki revizyon gruplarına nasıl göz atılır?

 C: Kullan`Groups` belgenin özelliği`Revisions` revizyon gruplarının koleksiyonunu almak için nesne. Daha sonra her inceleme grubunda döngü oluşturmak için bir döngü kullanabilirsiniz.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Her inceleme grubunu burada işleyin
}
```

#### S: Aspose.Words for .NET'te bir inceleme grubunun yazarını nasıl edinebilirim?

 C: Kullan`Author` mülkiyeti`RevisionGroup` revizyon grubunun yazarını almak için nesne.

```csharp
string author = group.Author;
```

#### S: Aspose.Words for .NET'te bir revizyon grubunun revizyon tipini nasıl edinebilirim?

 C: Kullan`RevisionType` mülkiyeti`RevisionGroup`Grubun revizyon türünü almak için nesne.

```csharp
string revisionType = group.RevisionType;
```