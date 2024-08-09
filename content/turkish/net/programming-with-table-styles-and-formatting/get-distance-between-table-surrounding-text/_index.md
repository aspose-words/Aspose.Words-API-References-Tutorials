---
title: Tablo Çevreleyen Metin Arasındaki Mesafeyi Alın
linktitle: Tablo Çevreleyen Metin Arasındaki Mesafeyi Alın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerinde bir tablo ile onu çevreleyen metin arasındaki mesafeyi nasıl alacağınızı öğrenin. Bu kılavuzla belge düzeninizi geliştirin.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---
## giriiş

Şık bir rapor veya önemli bir belge hazırladığınızı ve tablolarınızın tam olarak doğru görünmesini istediğinizi düşünün. Tablolar ve etraflarındaki metinler arasında yeterli boşluk olduğundan emin olmanız gerekir; böylece belgenin okunması kolay ve görsel açıdan çekici olur. Aspose.Words for .NET'i kullanarak bu mesafeleri programlı olarak kolayca alabilir ve ayarlayabilirsiniz. Bu eğitim, belgelerinizin ekstra profesyonellik dokunuşuyla öne çıkmasını sağlayarak bunu başarmak için gerekli adımlar konusunda size rehberlik edecektir.

## Önkoşullar

Koda geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Words for .NET Library: Aspose.Words for .NET kütüphanesinin kurulu olması gerekir. Henüz yapmadıysanız adresinden indirebilirsiniz.[Sürümleri Aspose](https://releases.aspose.com/words/net/) sayfa.
2. Geliştirme Ortamı: .NET Framework'ün yüklü olduğu, çalışan bir geliştirme ortamı. Visual Studio iyi bir seçenektir.
3. Örnek Belge: Kodu test etmek için en az bir tablo içeren bir Word belgesi (.docx).

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını projenize aktaralım. Bu, Aspose.Words for .NET kullanarak Word belgelerini yönetmek için gereken sınıflara ve yöntemlere erişmenizi sağlayacaktır.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Şimdi süreci takip edilmesi kolay adımlara ayıralım. Belgenizi yüklemekten masanızın etrafındaki mesafeleri almaya kadar her şeyi ele alacağız.

## 1. Adım: Belgenizi Yükleyin

 İlk adım, Word belgenizi Aspose.Words'e yüklemektir.`Document` nesne. Bu nesne belgenin tamamını temsil eder.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "Tables.docx");
```

## Adım 2: Tabloya Erişin

 Daha sonra belgenizdeki tabloya erişmeniz gerekir.`GetChild` yöntemi belgede bulunan ilk tabloyu almanızı sağlar.

```csharp
// Belgedeki ilk tabloyu alın
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Adım 3: Mesafe Değerlerini Alın

Artık tablonuz olduğuna göre mesafe değerlerini almanın zamanı geldi. Bu değerler, tablo ile onu çevreleyen metin arasındaki boşluğu her iki taraftan temsil eder: üst, alt, sol ve sağ.

```csharp
// Tablo ve çevresindeki metin arasındaki mesafeyi alın
Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
Console.WriteLine("Distance from Top: " + table.DistanceTop);
Console.WriteLine("Distance from Bottom: " + table.DistanceBottom);
Console.WriteLine("Distance from Right: " + table.DistanceRight);
Console.WriteLine("Distance from Left: " + table.DistanceLeft);
```

## Adım 4: Mesafeleri Görüntüleyin

Son olarak mesafeleri görüntüleyebilirsiniz. Bu, aralığı doğrulamanıza ve tablonuzun belgede mükemmel görünmesini sağlamak için gerekli ayarlamaları yapmanıza yardımcı olabilir.

```csharp
// Mesafeleri göster
Console.WriteLine("Distance from Top: " + table.DistanceTop);
Console.WriteLine("Distance from Bottom: " + table.DistanceBottom);
Console.WriteLine("Distance from Right: " + table.DistanceRight);
Console.WriteLine("Distance from Left: " + table.DistanceLeft);
```

## Çözüm

Ve işte karşınızda! Bu adımları izleyerek Aspose.Words for .NET'i kullanarak Word belgelerinizdeki bir tablo ile onu çevreleyen metin arasındaki mesafeleri kolayca alabilirsiniz. Bu basit ama güçlü teknik, belge düzeninizde ince ayar yapmanıza olanak tanıyarak onu daha okunabilir ve görsel olarak çekici hale getirir. Mutlu kodlama!

## SSS'ler

### Mesafeleri programlı olarak ayarlayabilir miyim?
 Evet, Aspose.Words'ü kullanarak mesafeleri programlı olarak ayarlayabilirsiniz.`DistanceTop`, `DistanceBottom`, `DistanceRight` , Ve`DistanceLeft` özellikleri`Table` nesne.

### Belgemde birden fazla tablo varsa ne olur?
 Belgenin alt düğümleri arasında geçiş yapabilir ve aynı yöntemi her tabloya uygulayabilirsiniz. Kullanmak`GetChildNodes(NodeType.Table, true)` tüm tabloları almak için.

### Aspose.Words'ü .NET Core ile kullanabilir miyim?
Kesinlikle! Aspose.Words .NET Core'u destekler ve aynı kodu .NET Core projeleri için küçük ayarlamalarla kullanabilirsiniz.

### Aspose.Words for .NET'i nasıl yüklerim?
Aspose.Words for .NET'i Visual Studio'daki NuGet Paket Yöneticisi aracılığıyla yükleyebilirsiniz. Basitçe "Aspose.Words" ifadesini arayın ve paketi yükleyin.

### Aspose.Words'ün desteklediği belge türlerinde herhangi bir sınırlama var mı?
 Aspose.Words, DOCX, DOC, PDF, HTML ve daha fazlasını içeren çok çeşitli belge formatlarını destekler. Kontrol edin[dokümantasyon](https://reference.aspose.com/words/net/) Desteklenen formatların tam listesi için.