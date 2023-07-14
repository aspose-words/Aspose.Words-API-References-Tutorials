---
title: Revizyon Gruplarını Alın
linktitle: Revizyon Gruplarını Alın
second_title: Aspose.Words Belge İşleme API'sı
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

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki revizyon gruplarını nasıl alacağımızı öğrendik. Yazar ve inceleme türü gibi ayrıntıları görüntüleyerek belgeyi yükleme ve inceleme gruplarına göz atma adımlarını izledik. Artık bu bilgiyi Aspose.Words for .NET kullanarak kendi Word belgenizin revizyonlarını analiz etmek için uygulayabilirsiniz.

### SSS

#### S: Aspose.Words for .NET'te bir belge nasıl yüklenir?

 C: Şunu kullanın:`Document` bir dosyadan belge yüklemek için Aspose.Words for .NET sınıfı. Tam belge yolunu belirleyebilirsiniz.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### S: Aspose.Words for .NET'te bir belgedeki revizyon gruplarına nasıl göz atılır?

 C: Şunu kullanın:`Groups` belgenin özelliği`Revisions` revizyon gruplarının koleksiyonunu almak için nesne. Daha sonra, her inceleme grubu arasında geçiş yapmak için bir döngü kullanabilirsiniz.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Her inceleme grubunu burada işleyin
}
```

#### S: Aspose.Words for .NET'te bir inceleme grubunun yazarını nasıl edinebilirim?

 C: Şunu kullanın:`Author`mülkiyeti`RevisionGroup` revizyon grubunun yazarını almak için nesne.

```csharp
string author = group.Author;
```

#### S: Aspose.Words for .NET'te bir revizyon grubunun revizyon türü nasıl elde edilir?

 C: Şunu kullanın:`RevisionType`mülkiyeti`RevisionGroup`grubun revizyon türünü almak için nesne.

```csharp
string revisionType = group.RevisionType;
```