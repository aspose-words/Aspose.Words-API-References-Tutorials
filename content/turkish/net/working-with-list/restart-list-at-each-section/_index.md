---
title: Listeyi Her Bölümde Yeniden Başlatın
linktitle: Listeyi Her Bölümde Yeniden Başlatın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesindeki her bölüme numaralandırılmış listeyi nasıl sıfırlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-list/restart-list-at-each-section/
---

Bu adım adım eğitimde, Aspose.Words for .NET kullanarak bir Word belgesindeki her bölüme numaralandırılmış listeyi nasıl sıfırlayacağınızı göstereceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

 Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve yapılandırılmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı şuradan indirip yükleyin:[Aspose.Releases]https://releases.aspose.com/words/net/.

## Adım 1: Belge ve Liste Oluşturma

Öncelikle yeni bir belge oluşturun ve varsayılan numaralandırılmış bir liste ekleyin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## 2. Adım: Listeye öğe ekleme

 Sonra bir kullanın`DocumentBuilder` Listeye öğe eklemek için. Listeye birden fazla öğe eklemek için döngü kullanabilirsiniz:

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

Son olarak değiştirilen belgeyi kaydedin:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Bu yüzden ! Aspose.Words for .NET'i kullanarak bir Word belgesindeki her bölüme numaralandırılmış bir listeyi başarıyla sıfırladınız.

### Her bölümdeki listeyi sıfırlamak için örnek kaynak kodu

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

### SSS'ler

#### S: Aspose.Words'ün her bölümündeki bir listeyi nasıl yeniden başlatabilirim?

 C: Aspose.Words'ün her bölümünde bir listeyi yeniden başlatmak için listenin bir örneğini oluşturmanız gerekir.`List` sınıfa numaralandırılmış bir liste atayın. Daha sonra şunu kullanabilirsiniz:`List.IsRestartAtEachSection` Numaralandırmanın her bölümde yeniden başlatılması gerektiğini belirten özellik. Numaralandırmanın her bölümde doğru şekilde yeniden başlatılması için bu listeyi belgenizin bir veya daha fazla bölümüyle ilişkilendirebilirsiniz.

#### S: Aspose.Words'te listelerin numaralandırma formatını özelleştirebilir miyim?

 C: Evet, Aspose.Words'te listelerin numaralandırma formatını özelleştirebilirsiniz.`List` class bunun için çeşitli özellikler sunar, örneğin`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`Liste türünü (numaralandırılmış, madde işaretli vb.), numaralandırma biçimini (Arap rakamları, Romen rakamları, harfler vb.) ve diğer numaralandırma biçimlendirme seçeneklerini ayarlamak için bu özellikleri kullanabilirsiniz.

#### S: Aspose.Words'te numaralandırılmış bir listeye ek seviyeler eklemek mümkün müdür?

 C: Evet, Aspose.Words'te numaralandırılmış bir listeye ek seviyeler eklemek mümkündür.`ListLevel` class, listenin her düzeyi için biçimlendirme özelliklerini ayarlamanıza olanak tanır. Önek, sonek, hizalama, girinti vb. seçenekleri ayarlayabilirsiniz. Bu, birden fazla hiyerarşi düzeyine sahip listeler oluşturmanıza olanak tanır.