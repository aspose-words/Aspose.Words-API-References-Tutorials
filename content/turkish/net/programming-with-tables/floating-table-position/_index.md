---
title: Yüzer Tabla Konumu
linktitle: Yüzer Tabla Konumu
second_title: Aspose.Words Belge İşleme API'si
description: Ayrıntılı, adım adım kılavuzumuzla Aspose.Words for .NET kullanarak Word belgelerindeki tabloların kayan konumunu nasıl kontrol edeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/floating-table-position/
---
## giriiş

Aspose.Words for .NET'i kullanarak Word belgelerinde tablo konumlarını değiştirme dünyasına dalmaya hazır mısınız? Kemerlerinizi bağlayın, çünkü bugün masaların kayan konumunu kolaylıkla nasıl kontrol edebileceğimizi keşfedeceğiz. Sizi kısa sürede bir masa konumlandırma sihirbazına dönüştürelim!

## Önkoşullar

Bu heyecan verici yolculuğa çıkmadan önce ihtiyacımız olan her şeye sahip olduğumuzdan emin olalım:

1. Aspose.Words for .NET Library: En son sürüme sahip olduğunuzdan emin olun. Eğer yapmazsan,[buradan indir](https://releases.aspose.com/words/net/).
2. .NET Framework: Geliştirme ortamınızın .NET ile ayarlandığından emin olun.
3. Geliştirme Ortamı: Visual Studio veya tercih edilen herhangi bir IDE.
4. Word Belgesi: Tablo içeren bir Word belgesini hazır bulundurun.

## Ad Alanlarını İçe Aktar

Başlamak için .NET projenize gerekli ad alanlarını içe aktarmanız gerekir. İşte C# dosyanızın en üstüne eklenecek kod parçası:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Tables;
```

## Adım Adım Kılavuz

Şimdi süreci basit, sindirilebilir adımlara ayıralım.

## 1. Adım: Belgeyi Yükleyin

Öncelikle Word belgenizi yüklemeniz gerekir. Masanızın bulunduğu yer burasıdır.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Word belgenizin bir tuval olduğunu ve masanızın da bir sanat eseri olduğunu hayal edin. Amacımız bu sanatı tuval üzerinde tam istediğimiz yere konumlandırmaktır.

## Adım 2: Tabloya Erişin

Daha sonra belge içindeki tabloya erişmemiz gerekiyor. Genellikle belgenin gövdesindeki ilk tabloyla çalışacaksınız.

```csharp
Table table = doc.FirstSection.Body.Tables[0];
```

Bu adımı, çalışmak istediğiniz tabloyu fiziksel bir belgede bulmak olarak düşünün. Herhangi bir değişiklik yapmak için tam olarak nerede olduğunu bilmeniz gerekir.

## Adım 3: Yatay Konumu Ayarlayın

Şimdi tablonun yatay konumunu ayarlayalım. Bu, tablonun belgenin sol kenarından ne kadar uzağa yerleştirileceğini belirler.

```csharp
table.AbsoluteHorizontalDistance = 10;
```

 Bunu, tabloyu belgeniz boyunca yatay olarak hareket ettirmek olarak görselleştirin.`AbsoluteHorizontalDistance` sol kenardan tam mesafedir.

## Adım 4: Dikey Hizalamayı Ayarlayın

Ayrıca tablonun dikey hizalamasını da ayarlamamız gerekiyor. Bu, tabloyu çevresindeki metin içinde dikey olarak ortalayacaktır.

```csharp
table.RelativeVerticalAlignment = VerticalAlignment.Center;
```

Duvara bir resim astığınızı hayal edin. Estetik çekicilik için dikey olarak ortalandığından emin olmak istiyorsunuz. Bu adım bunu başarıyor.

## Adım 5: Değiştirilen Belgeyi Kaydedin

Son olarak tabloyu konumlandırdıktan sonra değiştirilen belgenizi kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Bu, düzenlediğiniz belgede 'Kaydet'e basmak gibidir. Artık tüm değişiklikleriniz korunuyor.

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak bir Word belgesindeki tabloların kayan konumunu nasıl kontrol edeceğinizi artık öğrendiniz. Bu becerilerle, belgelerinizin okunabilirliğini ve estetiğini artırmak için tablolarınızın mükemmel şekilde konumlandırılmasını sağlayabilirsiniz. Aspose.Words for .NET'in geniş yeteneklerini denemeye ve keşfetmeye devam edin.

## SSS'ler

### Tablonun dikey mesafesini sayfanın üst kısmından ayarlayabilir miyim?

 Evet, kullanabilirsiniz`AbsoluteVerticalDistance` Tablonun sayfanın üst kenarından dikey mesafesini ayarlama özelliği.

### Tabloyu belgenin sağına nasıl hizalarım?

 Tabloyu sağa hizalamak için`HorizontalAlignment` tablonun özelliği`HorizontalAlignment.Right`.

### Aynı belgede birden fazla tabloyu farklı şekilde konumlandırmak mümkün mü?

 Kesinlikle! Birden çok tablonun konumlarına tek tek erişebilir ve bunları ayarlayabilirsiniz.`Tables` belgede toplanması.

### Yatay hizalama için göreli konumlandırmayı kullanabilir miyim?

Evet, Aspose.Words aşağıdaki gibi özellikleri kullanarak hem yatay hem de dikey hizalamalar için göreceli konumlandırmayı destekler`RelativeHorizontalAlignment`.

### Aspose.Words bir belgenin farklı bölümlerinde kayan tabloları destekliyor mu?

Evet, belgenizdeki belirli bir bölüme ve onun tablolarına erişerek kayan tabloları farklı bölümlerde konumlandırabilirsiniz.