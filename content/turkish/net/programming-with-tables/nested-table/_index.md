---
title: İç İçe Tablo
linktitle: İç İçe Tablo
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerinde iç içe tabloların nasıl oluşturulacağını kılavuzumuzla öğrenin. Programlı olarak karmaşık belge düzenleri oluşturmak için mükemmeldir.
type: docs
weight: 10
url: /tr/net/programming-with-tables/nested-table/
---
## giriiş

Kendinizi bir Word belgesinde programlı olarak iç içe geçmiş bir tablo oluşturmaya ihtiyaç duyduğunuzda hiç buldunuz mu? İster rapor, ister fatura, ister ayrıntılı tablo yapısı gerektiren herhangi bir belge oluşturuyor olun, Aspose.Words for .NET en iyi arkadaşınız olabilir. Bu eğitimde Aspose.Words for .NET'i kullanarak Word belgelerinde iç içe tablolar oluşturma sürecini ayrıntılı olarak ele alacağız. Önkoşullardan son kod uygulamasına kadar her şeyi ele alacağız. Öyleyse başlayalım!

## Önkoşullar

Koda geçmeden önce ihtiyacınız olacak birkaç şey var:

-  Aspose.Words for .NET: Buradan indirebilirsiniz.[Burada](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Visual Studio veya başka herhangi bir C# IDE.
- Temel C# Bilgisi: C# sözdizimi ve kavramlarının anlaşılması.

Devam etmeden önce bu ayarları yaptığınızdan emin olun.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktaralım. Bu ad alanları, Word belgeleriyle çalışmak için gereken sınıflara ve yöntemlere erişmemizi sağlayacaktır.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Adım 1: Document'ı ve DocumentBuilder'ı başlatın

 Başlamak için yeni bir Word belgesi oluşturacağız ve`DocumentBuilder` tabloyu oluşturmamıza yardımcı olacak nesne.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: Dış Tabloyu Oluşturun

Şimdi dış tabloyu oluşturalım. İlk hücreyi ekleyip ona biraz içerik ekleyerek başlayacağız.

### Adım 2.1: Dış Tablonun İlk Hücresini Yerleştirin

```csharp
Cell cell = builder.InsertCell();
builder.Writeln("Outer Table Cell 1");
```

### Adım 2.2: Dış Tablonun İkinci Hücresini Yerleştirin

Daha sonra ikinci hücreyi ekleyip biraz içerik ekleyeceğiz.

```csharp
builder.InsertCell();
builder.Writeln("Outer Table Cell 2");
```

### Adım 2.3: Dış Tabloyu Sonlandırın

Tabloyu burada bitirmek, iç içe geçmiş tabloyu ilk hücrede başlatmamıza izin verdiği için çok önemlidir.

```csharp
builder.EndTable();
```

## Adım 3: İç Tabloyu Oluşturun

Yuvalanmış bir tablo oluşturmak için imleci dış tablonun ilk hücresine hareket ettirmemiz ve ardından iç tabloyu oluşturmaya başlamamız gerekir.

### Adım 3.1: Dış Tablonun İlk Hücresine Geçin

```csharp
builder.MoveTo(cell.FirstParagraph);
```

### Adım 3.2: İç Tablonun İlk Hücresini Yerleştirin

Şimdi iç tablonun ilk hücresini ekleyelim ve biraz içerik ekleyelim.

```csharp
builder.InsertCell();
builder.Writeln("Inner Table Cell 1");
```

### Adım 3.3: İç Tablonun İkinci Hücresini Yerleştirin

Son olarak ikinci hücreyi ekleyip biraz içerik ekleyeceğiz.

```csharp
builder.InsertCell();
builder.Writeln("Inner Table Cell 2");
```

### Adım 3.4: İç Tabloyu Sonlandırın

İç tabloyu sonlandırarak bitiriyoruz.

```csharp
builder.EndTable();
```

## Adım 4: Belgeyi Kaydedin

Son adım, belgeyi belirttiğiniz dizine kaydetmektir.

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak bir Word belgesinde başarıyla iç içe geçmiş bir tablo oluşturdunuz. Bu güçlü kitaplık, Word belgelerini programlı olarak yönetmeyi inanılmaz derecede kolaylaştırır. İster karmaşık raporlar ister basit tablolar oluşturuyor olun, Aspose.Words for .NET ihtiyacınızı karşılar.

## SSS'ler

### İç içe geçmiş tablo nedir?

Yuvalanmış tablo, tablo içindeki tablodur. Belgelerde formlar veya ayrıntılı veri sunumları gibi karmaşık düzenler oluşturmak için kullanılır.

### Aspose.Words for .NET'i neden kullanmalısınız?

Aspose.Words for .NET, Word belgelerini programlı olarak oluşturmak, değiştirmek ve dönüştürmek için güçlü bir dizi özellik sunar ve bu da onu geliştiriciler için ideal bir seçim haline getirir.

### Daha fazla iç içe geçmiş tablo düzeyi ekleyebilir miyim?

Evet, geçerli tabloyu sonlandırıp hücre içinde yeni bir tablo başlatma işlemini tekrarlayarak birden çok düzeyde iç içe geçmiş tablo oluşturabilirsiniz.

### Aspose.Words for .NET, Word'ün tüm sürümleriyle uyumlu mu?

Aspose.Words for .NET, DOC, DOCX, RTF ve daha fazlasını içeren çok çeşitli Word belge formatlarıyla uyumludur.

### Aspose.Words for .NET için nasıl destek alabilirim?

 adresinden destek alabilirsiniz.[Aspose.Words Destek Forumu](https://forum.aspose.com/c/words/8).