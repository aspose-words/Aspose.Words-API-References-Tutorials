---
title: Yüzen Masa Konumunu Alın
linktitle: Yüzen Masa Konumunu Alın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerinde kayan tablo konumlarını nasıl elde edeceğinizi öğrenin. Bu ayrıntılı, adım adım kılavuz, bilmeniz gereken her şeyde size yol gösterecektir.
type: docs
weight: 10
url: /tr/net/programming-with-tables/get-floating-table-position/
---
## giriiş

Aspose.Words for .NET dünyasına dalmaya hazır mısınız? Bugün sizi Word belgelerindeki kayan tabloların sırlarını açığa çıkaracak bir yolculuğa çıkaracağız. Sadece sabit durmayan, aynı zamanda metnin etrafında zarif bir şekilde süzülen bir masanız olduğunu hayal edin. Oldukça hoş, değil mi? Bu eğitim, bu tür kayan tabloların konumlandırma özelliklerinin nasıl elde edileceği konusunda size yol gösterecektir. Öyleyse başlayalım!

## Önkoşullar

Eğlenceli kısma geçmeden önce, hazır bulundurmanız gereken birkaç şey var:

1.  Aspose.Words for .NET: Henüz yapmadıysanız Aspose.Words for .NET'i aşağıdaki adresten indirip yükleyin:[Aspose sürümler sayfası](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Bir .NET geliştirme ortamı kurduğunuzdan emin olun. Visual Studio harika bir seçenektir.
3. Örnek Belge: Kayan tablo içeren bir Word belgesine ihtiyacınız olacak. Bir tane oluşturabilir veya mevcut bir belgeyi kullanabilirsiniz. 

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını içe aktarmanız gerekir. Bu, Word belgelerini düzenlemek için gereken Aspose.Words sınıflarına ve yöntemlerine erişmenizi sağlar.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Peki, süreci takip edilmesi kolay adımlara ayıralım.

## 1. Adım: Belgenizi Yükleyin

Öncelikle Word belgenizi yüklemeniz gerekir. Bu belge incelemek istediğiniz kayan tabloyu içermelidir.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

 Bu adımda Aspose.Words'e belgenizi nerede bulacağını söylüyorsunuz. Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` belgenizin gerçek yolu ile.

## Adım 2: Belgedeki Tablolara Erişin

Daha sonra belgenin ilk bölümündeki tablolara erişmeniz gerekiyor. Belgeyi büyük bir kap olarak düşünün ve tüm tabloları bulmak için onu kazıyorsunuz.

```csharp
foreach (Table table in doc.FirstSection.Body.Tables)
{
    // Her tabloyu işlemek için kodunuz buraya gelir
}
```

Burada, belgenizin ilk bölümünün gövdesinde bulunan her tablonun içinde dolaşıyorsunuz.

## 3. Adım: Tablonun Kayan olup olmadığını kontrol edin

Şimdi tablonun kayan tipte olup olmadığını belirlemeniz gerekiyor. Kayan tabloların belirli metin sarma ayarları vardır.

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
    // Tablo konumlandırma özelliklerini yazdırma kodunuz buraya gelir
}
```

Bu koşul, tablonun metin sarma stilinin "Etrafında" olarak ayarlanıp ayarlanmadığını kontrol eder; bu, tablonun kayan bir tablo olduğunu gösterir.

## Adım 4: Konumlandırma Özelliklerini Yazdırın

Son olarak kayan tablonun konumlandırma özelliklerini çıkartıp yazdıralım. Bu özellikler size tablonun metne ve sayfaya göre nerede konumlandırıldığını söyler.

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
    Console.WriteLine("Horizontal Anchor: " + table.HorizontalAnchor);
    Console.WriteLine("Vertical Anchor: " + table.VerticalAnchor);
    Console.WriteLine("Absolute Horizontal Distance: " + table.AbsoluteHorizontalDistance);
    Console.WriteLine("Absolute Vertical Distance: " + table.AbsoluteVerticalDistance);
    Console.WriteLine("Allow Overlap: " + table.AllowOverlap);
    Console.WriteLine("Relative Vertical Alignment: " + table.RelativeVerticalAlignment);
    Console.WriteLine("..............................");
}
```

Bu özellikler, tablonun belge içinde nasıl sabitlendiğine ve konumlandırıldığına ilişkin ayrıntılı bir görünüm sağlar.

## Çözüm

Ve işte karşınızda! Bu adımları izleyerek Aspose.Words for .NET'i kullanarak Word belgelerinizdeki kayan tabloların konumlandırma özelliklerini kolayca alabilir ve yazdırabilirsiniz. İster belge işlemeyi otomatikleştiriyor olun, ister yalnızca tablo düzenlerini merak ediyor olun, bu bilgi kesinlikle işinize yarayacaktır.

Unutmayın, Aspose.Words for .NET ile çalışmak, belge işleme ve otomasyon için bir olasılıklar dünyasının kapılarını açar. Mutlu kodlama!

## SSS'ler

### Word belgelerinde kayan tablo nedir?
Kayan tablo, metne sabitlenmeyen ancak genellikle etrafına metin sarılarak hareket edebilen bir tablodur.

### Aspose.Words for .NET kullanarak bir tablonun değişken olup olmadığını nasıl anlarım?
 Bir tablonun kayan olup olmadığını inceleyerek kontrol edebilirsiniz.`TextWrapping` mülk. Eğer ayarlanmışsa`TextWrapping.Around`, masa yüzüyor.

### Kayan tablonun konumlandırma özelliklerini değiştirebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak, kayan tablonun konumlandırma özelliklerini değiştirerek düzenini özelleştirebilirsiniz.

### Aspose.Words for .NET büyük ölçekli belge otomasyonuna uygun mu?
Kesinlikle! Aspose.Words for .NET, yüksek performanslı belge otomasyonu için tasarlanmıştır ve büyük ölçekli işlemleri verimli bir şekilde gerçekleştirebilir.

### Aspose.Words for .NET hakkında daha fazla bilgiyi ve kaynağı nerede bulabilirim?
Ayrıntılı belge ve kaynakları şu adreste bulabilirsiniz:[Aspose.Words for .NET dokümantasyon sayfası](https://reference.aspose.com/words/net/).