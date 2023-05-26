---
title: Her Bölümde Listeyi Yeniden Başlat
linktitle: Her Bölümde Listeyi Yeniden Başlat
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesindeki her bölüme numaralı bir listeyi nasıl sıfırlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-list/restart-list-at-each-section/
---

Bu adım adım öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki her bölüme numaralı bir listeyi nasıl sıfırlayacağınızı göstereceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinize nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve yapılandırılmış olduğundan emin olun. Henüz yapmadıysanız, kütüphaneyi resmi siteden indirip yükleyin.

## Adım 1: Belge ve Listeyi Oluşturma

İlk olarak, yeni bir belge oluşturun ve varsayılan bir numaralı liste ekleyin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## 2. Adım: Listeye öğe ekleme

 Daha sonra bir`DocumentBuilder` Listeye öğe eklemek için. Listeye birden çok öğe eklemek için bir döngü kullanabilirsiniz:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

Bu örnekte, yeniden numaralandırmayı göstermek için 15. liste öğesinden sonra bir bölüm sonu ekliyoruz.

## 3. Adım: Değiştirilen belgeyi kaydedin

Son olarak, değiştirilen belgeyi kaydedin:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Bu yüzden ! Aspose.Words for .NET'i kullanarak bir Word belgesindeki her bölüme numaralandırılmış bir listeyi başarıyla sıfırladınız.

### Her bölümde listeyi sıfırlamak için örnek kaynak kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

Bu kodu kendi projelerinizde kullanmaktan ve özel ihtiyaçlarınıza uyacak şekilde değiştirmekten çekinmeyin.
