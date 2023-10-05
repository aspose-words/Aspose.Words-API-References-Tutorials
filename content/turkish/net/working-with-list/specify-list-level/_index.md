---
title: Liste Düzeyini Belirtin
linktitle: Liste Düzeyini Belirtin
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde liste düzeyini nasıl belirleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-list/specify-list-level/
---

Bu adım adım eğitimde, Aspose.Words for .NET'i kullanarak bir Word belgesinde liste düzeyini nasıl belirleyeceğinizi göstereceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

 Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve yapılandırılmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı şuradan indirip yükleyin:[Aspose.Releases]https://releases.aspose.com/words/net/.

## Adım 1: Belge ve Belge Oluşturucuyu Oluşturma

Öncelikle yeni bir belge ve ilişkili bir belge oluşturucu oluşturun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: Numaralı Liste Oluşturma ve Uygulama

Daha sonra, Microsoft Word'ün liste şablonlarından birini temel alan numaralı bir liste oluşturun ve bunu belge oluşturucudaki geçerli paragrafa uygulayın:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Adım 3: Düzey Spesifikasyonlarını Listeleyin

 Belge oluşturucuyu kullanın`ListLevelNumber` liste düzeyini belirtme ve paragrafa metin ekleme özelliği:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Liste düzeylerini belirtmek ve her düzeye metin eklemek için bu adımları tekrarlayın.

## Adım 4: Madde İşaretli Liste Oluşturma ve Uygulama

Ayrıca Microsoft Word'ün liste şablonlarından birini kullanarak madde işaretli liste oluşturabilir ve uygulayabilirsiniz:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Adım 5: Madde İşaretli Liste Düzeylerine Metin Ekleme

 Kullan`ListLevelNumber` Madde işaretli liste düzeyini belirlemek ve metin eklemek için özelliği tekrar kullanın:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Adım 6: Listeyi Biçimlendirmeyi Durdurun

 Liste biçimlendirmesini durdurmak için`null` -e`List` belge oluşturucunun özelliği:

```csharp
builder. ListFormat. List = null;
```

## Adım 7: Değiştirilen belgeyi kaydetme

Değiştirilen belgeyi kaydedin:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

Bu yüzden ! Aspose.Words for .NET'i kullanarak bir Word belgesinde liste düzeyini başarıyla belirlediniz.

### Liste düzeyini belirtmek için örnek kaynak kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Microsoft Word liste şablonlarından birine dayalı numaralandırılmış bir liste oluşturun
//ve bunu belge oluşturucunun geçerli paragrafına uygulayın.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Bu listede dokuz seviye var, hepsini deneyelim.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Microsoft Word liste şablonlarından birini temel alan madde işaretli bir liste oluşturun
//ve bunu belge oluşturucunun geçerli paragrafına uygulayın.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Bu, liste biçimlendirmesini durdurmanın bir yoludur.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### SSS'ler

#### S: Aspose.Words'te liste düzeyini nasıl belirleyebilirim?

 C: Aspose.Words'te liste düzeyini belirlemek için listenin bir örneğini oluşturmanız gerekir.`List` sınıfa gidin ve ona numaralandırılmış bir liste verin. Daha sonra şunu kullanabilirsiniz:`Paragraph.ListFormat.ListLevelNumber` Her liste öğesinin düzeyini belirtme özelliği. Liste öğelerinin istenen düzeye sahip olması için bu listeyi belgenizin bir bölümüyle ilişkilendirebilirsiniz.

#### S: Aspose.Words'te liste öğelerinin numaralandırma formatını değiştirmek mümkün mü?

 C: Evet, Aspose.Words'te liste öğelerinin numaralandırma formatını değiştirebilirsiniz.`ListLevel` class bunun için çeşitli özellikler sunar, örneğin`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`, vb. Liste öğelerinin numaralandırma biçimini (Arap rakamları, Romen rakamları, harfler vb.) ayarlamak için bu özellikleri kullanabilirsiniz.

#### S: Aspose.Words'te numaralandırılmış bir listeye ek seviyeler ekleyebilir miyim?

 C: Evet, Aspose.Words'te numaralandırılmış bir listeye ek seviyeler eklemek mümkündür.`ListLevel` class, listenin her düzeyi için biçimlendirme özelliklerini ayarlamanıza olanak tanır. Önek, sonek, hizalama, girinti vb. seçenekleri ayarlayabilirsiniz. Bu, birden fazla hiyerarşi düzeyine sahip listeler oluşturmanıza olanak tanır.


