---
title: Liste Düzeyini Belirtin
linktitle: Liste Düzeyini Belirtin
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir Word belgesinde liste düzeyini nasıl belirleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-list/specify-list-level/
---

Bu adım adım öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde liste düzeyini nasıl belirleyeceğinizi göstereceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinize nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve yapılandırılmış olduğundan emin olun. Henüz yapmadıysanız, kütüphaneyi resmi siteden indirip yükleyin.

## 1. Adım: Belge ve Belge Oluşturucuyu Oluşturma

İlk olarak, yeni bir belge ve ilişkili bir belge oluşturucu oluşturun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: Numaralı Liste Oluşturma ve Uygulama

Ardından, Microsoft Word'ün liste şablonlarından birini temel alan bir numaralandırılmış liste oluşturun ve bunu belge oluşturucudaki geçerli paragrafa uygulayın:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## 3. Adım: Liste Düzeyi Spesifikasyonu

 Belge oluşturucunun`ListLevelNumber` liste düzeyini belirtmek ve paragrafa metin eklemek için özellik:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Liste düzeylerini belirlemek ve her düzeyde metin eklemek için bu adımları tekrarlayın.

## 4. Adım: Madde İşaretli Liste Oluşturma ve Uygulama

Ayrıca, Microsoft Word'ün liste şablonlarından birini kullanarak madde işaretli bir liste oluşturabilir ve uygulayabilirsiniz:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Adım 5: Madde İşaretli Liste Düzeylerine Metin Ekleme

 Kullan`ListLevelNumber` madde işaretli liste düzeyini belirlemek ve metin eklemek için yeniden özelliğini kullanın:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Adım 6: Listeyi Biçimlendirmeyi Durdurun

 Liste biçimlendirmesini durdurmak için,`null` için`List` belge oluşturucunun özelliği:

```csharp
builder. ListFormat. List = null;
```

## 7. Adım: Değiştirilen belgeyi kaydetme

Değiştirilen belgeyi kaydedin:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

Bu yüzden ! Aspose.Words for .NET kullanarak bir Word belgesinde liste seviyesini başarıyla belirlediniz.

### Liste düzeyini belirtmek için örnek kaynak kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//Microsoft Word liste şablonlarından birine dayalı olarak numaralandırılmış bir liste oluşturun
// ve bunu belge oluşturucunun geçerli paragrafına uygulayın.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Bu listede dokuz seviye var, hepsini deneyelim.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Microsoft Word liste şablonlarından birini temel alan madde işaretli bir liste oluşturun
// ve bunu belge oluşturucunun geçerli paragrafına uygulayın.
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

### SSS

#### S: Aspose.Words'te liste seviyesini nasıl belirleyebilirim?

 C: Aspose.Words'te liste seviyesini belirtmek için, bir örnek oluşturmanız gerekir.`List` sınıf ve ona numaralı bir liste verin. Sonra kullanabilirsiniz`Paragraph.ListFormat.ListLevelNumber` özelliği, her bir liste öğesinin düzeyini belirtmek için. Bu listeyi belgenizin bir bölümü ile ilişkilendirerek liste öğelerinin istediğiniz düzeye gelmesini sağlayabilirsiniz.

#### S: Aspose.Words'te liste öğelerinin numaralandırma biçimini değiştirmek mümkün mü?

 C: Evet, Aspose.Words'te liste öğelerinin numaralandırma biçimini değiştirebilirsiniz. bu`ListLevel` class bunun için çeşitli özellikler sunar, örneğin`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`, vb. Liste öğeleri için Arap rakamları, Romen rakamları, harfler vb. gibi numaralandırma formatını ayarlamak için bu özellikleri kullanabilirsiniz.

#### S: Aspose.Words'te numaralı bir listeye ek seviyeler ekleyebilir miyim?

 C: Evet, Aspose.Words'te numaralı bir listeye ek seviyeler eklemek mümkündür. bu`ListLevel` class, listenin her düzeyi için biçimlendirme özelliklerini ayarlamanıza olanak tanır. Önek, sonek, hizalama, girinti vb. seçenekleri ayarlayabilirsiniz. Bu, birden çok hiyerarşi düzeyine sahip listeler oluşturmanıza olanak tanır.


