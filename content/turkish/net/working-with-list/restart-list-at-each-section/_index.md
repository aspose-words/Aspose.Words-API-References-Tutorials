---
title: Her Bölümde Listeyi Yeniden Başlat
linktitle: Her Bölümde Listeyi Yeniden Başlat
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesindeki her bölüme numaralı bir listeyi nasıl sıfırlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-list/restart-list-at-each-section/
---

Bu adım adım öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki her bölüme numaralı bir listeyi nasıl sıfırlayacağınızı göstereceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinize nasıl uygulayacağınızı göstereceğiz.

 Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve yapılandırılmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı adresinden indirip yükleyin.[Aspose.Releases]https://releases.aspose.com/words/net/.

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

### SSS

#### S: Aspose.Words'te her bölümde bir listeyi nasıl yeniden başlatabilirim?

 C: Aspose.Words'teki her bölümde bir listeyi yeniden başlatmak için,`List` sınıf ve ona numaralı bir liste atayın. Sonra kullanabilirsiniz`List.IsRestartAtEachSection` numaralandırmanın her bölümde yeniden başlatılması gerektiğini belirtmek için özellik. Numaralandırmanın her bölümde doğru şekilde yeniden başlaması için bu listeyi belgenizin bir veya daha fazla bölümüyle ilişkilendirebilirsiniz.

#### S: Aspose.Words'te listelerin numaralandırma formatını özelleştirebilir miyim?

 C: Evet, listelerin numaralandırma formatını Aspose.Words'te özelleştirebilirsiniz. bu`List` class bunun için çeşitli özellikler sunar, örneğin`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`vb. Liste türünü (numaralı, madde işaretli vb.), numaralandırma biçimini (Arap rakamları, Romen rakamları, harfler vb.) ve diğer numaralandırma biçimlendirme seçeneklerini ayarlamak için bu özellikleri kullanabilirsiniz.

#### S: Aspose.Words'te numaralı bir listeye ek seviyeler eklemek mümkün müdür?

 C: Evet, Aspose.Words'te numaralı bir listeye ek seviyeler eklemek mümkündür. bu`ListLevel` class, listenin her düzeyi için biçimlendirme özelliklerini ayarlamanıza olanak tanır. Önek, sonek, hizalama, girinti vb. seçenekleri ayarlayabilirsiniz. Bu, birden çok hiyerarşi düzeyine sahip listeler oluşturmanıza olanak tanır.