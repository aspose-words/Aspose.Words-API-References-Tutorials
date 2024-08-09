---
title: Liste Numarasını Yeniden Başlat
linktitle: Liste Numarasını Yeniden Başlat
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerindeki liste numaralarını nasıl yeniden başlatacağınızı öğrenin. Bu ayrıntılı, 2000 kelimelik kılavuz, kurulumdan gelişmiş özelleştirmeye kadar bilmeniz gereken her şeyi kapsar.
type: docs
weight: 10
url: /tr/net/working-with-list/restart-list-number/
---
## giriiş

Aspose.Words for .NET'i kullanarak Word belgelerinizde liste düzenleme sanatında ustalaşmak mı istiyorsunuz? Peki, doğru yerdesiniz! Bu eğitimde, belge otomasyon becerilerinizi bir sonraki seviyeye taşıyacak şık bir özellik olan liste numaralarını yeniden başlatma konusuna derinlemesine dalacağız. Kemerlerinizi bağlayın ve başlayalım!

## Önkoşullar

Koda geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Words for .NET: Aspose.Words for .NET'in kurulu olması gerekir. Henüz yüklemediyseniz, yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio gibi uygun bir geliştirme ortamına sahip olduğunuzdan emin olun.
3. Temel C# Bilgisi: Temel C# anlayışı, öğreticiyi takip etmenize yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktaralım. Bunlar Aspose.Words özelliklerine erişim için çok önemlidir.

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
using System.Drawing;
```

Şimdi süreci takip edilmesi kolay adımlara ayıralım. Liste oluşturmaktan numaralandırmayı yeniden başlatmaya kadar her şeyi ele alacağız.

## 1. Adım: Belgenizi ve Oluşturucunuzu Kurun

Listeleri değiştirmeye başlamadan önce bir belgeye ve DocumentBuilder'a ihtiyacınız vardır. DocumentBuilder, belgenize içerik eklemek için başvuracağınız araçtır.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: İlk Listenizi Oluşturun ve Özelleştirin

Daha sonra şablona dayalı bir liste oluşturacağız ve görünümünü özelleştireceğiz. Bu örnekte parantezli Arap sayı biçimini kullanıyoruz.

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

Burada yazı tipi rengini kırmızı olarak ayarladık ve metni sağa hizaladık.

## 3. Adım: İlk Listenize Öğe Ekleyin

 Listeniz hazır olduğuna göre artık bazı öğeler eklemenin zamanı geldi. DocumentBuilder'ın`ListFormat.List` özelliği, liste formatının metne uygulanmasına yardımcı olur.

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Adım 4: Liste Numaralandırmayı Yeniden Başlatın

Listeyi yeniden kullanmak ve numaralandırmayı yeniden başlatmak için orijinal listenin bir kopyasını oluşturmanız gerekir. Bu, yeni listeyi bağımsız olarak değiştirmenize olanak tanır.

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Bu örnekte yeni liste 10 numaradan başlıyor.

## Adım 5: Yeni Listeye Öğe Ekleme

Daha önce olduğu gibi yeni listenize öğeler ekleyin. Bu, listenin belirtilen numaradan yeniden başladığını gösterir.

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Adım 6: Belgenizi Kaydedin

Son olarak belgenizi belirttiğiniz dizine kaydedin.

```csharp
builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
```

## Çözüm

Aspose.Words for .NET kullanarak Word belgelerindeki liste numaralarını yeniden başlatmak basit ve son derece kullanışlıdır. İster rapor oluşturuyor olun, ister yapılandırılmış belgeler oluşturuyor olun, ister listeleriniz üzerinde daha iyi kontrole ihtiyaç duyuyor olun, bu teknik ihtiyacınızı karşılar.

## SSS'ler

### NumberArabicParenthesis dışında başka liste şablonları da kullanabilir miyim?

Kesinlikle! Aspose.Words madde işaretleri, harfler, Romen rakamları ve daha fazlası gibi çeşitli liste şablonları sunar. İhtiyaçlarınıza en uygun olanı seçebilirsiniz.

### Liste düzeyini nasıl değiştiririm?

 Liste düzeyini değiştirerek değiştirebilirsiniz.`ListLevels` mülk. Örneğin,`list1.ListLevels[1]` listenin ikinci düzeyine atıfta bulunur.

### Numaralandırmayı herhangi bir numaradan yeniden başlatabilir miyim?

 Evet, başlangıç numarasını herhangi bir tamsayı değerine ayarlayabilirsiniz.`StartAt` liste düzeyinin özelliği.

### Farklı liste düzeyleri için farklı biçimlendirmelere sahip olmak mümkün müdür?

Aslında! Her liste düzeyinin yazı tipi, hizalama ve numaralandırma stili gibi kendi biçimlendirme ayarları olabilir.

### Numaralandırmayı yeniden başlatmak yerine önceki listeden devam etmek istersem ne olur?

Numaralandırmaya devam etmek istiyorsanız listenin bir kopyasını oluşturmanıza gerek yoktur. Orijinal listeye öğe eklemeye devam etmeniz yeterlidir.


