---
title: Bir Grafikte Eksen Sınırları
linktitle: Bir Grafikte Eksen Sınırları
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak eksende görüntülenen değer aralığını kontrol ederek bir grafikte eksenin sınırlarını nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/bounds-of-axis/
---
## giriiş

.NET'te grafiklerle profesyonel belgeler mi oluşturmak istiyorsunuz? Doğru yerdesiniz! Bu kılavuz, bir grafikte eksen sınırlarını ayarlamak için Aspose.Words for .NET kullanma sürecinde size yol gösterecektir. Kütüphanede yeni olsanız bile kolayca takip edebilmenizi sağlamak için her adımı ayrıntılı olarak açıklayacağız. O halde haydi dalalım ve başlayalım!

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET: Yapabilirsin[indirmek](https://releases.aspose.com/words/net/) en son sürümü kullanın veya[ücretsiz deneme](https://releases.aspose.com/).
- .NET Framework: Sisteminizde .NET'in kurulu olduğundan emin olun.
- IDE: Visual Studio gibi bir geliştirme ortamı.

Her şeyi hazırladıktan sonra bir sonraki adıma geçebiliriz.

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını içe aktarmanız gerekir. Bunlar Aspose.Words kütüphanesine ve grafik özelliklerine erişmenizi sağlayacaktır.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## 1. Adım: Belge Dizininizi Kurun

Öncelikle belgenizin kaydedileceği dizini ayarlamanız gerekir. Bu basit bir adımdır ancak dosyalarınızı düzenlemek için çok önemlidir.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Yeni Bir Belge Oluşturun

Daha sonra yeni bir belge nesnesi oluşturun. Bu belge grafiğiniz için kapsayıcı görevi görecektir.

```csharp
Document doc = new Document();
```

## 3. Adım: Belge Oluşturucuyu Başlatın

DocumentBuilder sınıfı, belge oluşturmanın hızlı ve kolay bir yolunu sağlar. Belgenizle başlatın.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 4. Adım: Grafik Ekleme

Şimdi belgenize bir grafik eklemenin zamanı geldi. Bu örnekte Sütun grafiği kullanacağız.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Adım 5: Mevcut Serileri Temizle

Temiz bir sayfa açtığınızdan emin olmak için mevcut serileri grafikten silin.

```csharp
chart.Series.Clear();
```

## Adım 6: Grafiğe Veri Ekleme

Burada grafiğe veri ekliyoruz. Buna seri adının ve veri noktalarının belirtilmesi de dahildir.

```csharp
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Adım 7: Eksen Sınırlarını Ayarlayın

Y ekseni sınırlarını ayarlamak, grafiğinizin doğru şekilde ölçeklendirilmesini sağlar.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Adım 8: Belgeyi Kaydedin

Son olarak belgenizi belirtilen dizine kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

İşte bu kadar! Aspose.Words for .NET'i kullanarak grafik içeren bir belgeyi başarıyla oluşturdunuz. 

## Çözüm

Aspose.Words for .NET'i kullanarak belgelerinizde kolayca grafikler oluşturabilir ve değiştirebilirsiniz. Bu adım adım kılavuz, bir grafikte eksenin sınırlarını nasıl ayarlayacağınızı göstererek veri sunumunuzu daha hassas ve profesyonel hale nasıl getireceğinizi göstermiştir. İster rapor, ister sunum, ister başka bir belge oluşturuyor olun, Aspose.Words ihtiyacınız olan araçları sağlar.

## SSS

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, .NET çerçevesini kullanarak Word belgelerini programlı olarak oluşturmanıza, değiştirmenize ve dönüştürmenize olanak tanıyan bir kitaplıktır.

### Aspose.Words for .NET'i nasıl kurarım?
 Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/net/) ve verilen kurulum talimatlarını izleyin.

### Aspose.Words'ü ücretsiz kullanabilir miyim?
 Evet, kullanabilirsiniz[ücretsiz deneme](https://releases.aspose.com/) veya bir tane al[geçici lisans](https://purchase.aspose.com/temporary-license/).

### Aspose.Words for .NET belgelerini nerede bulabilirim?
 Detaylı dokümantasyon mevcut[Burada](https://reference.aspose.com/words/net/).

### Aspose.Words için nasıl destek alabilirim?
 Ziyaret edebilirsiniz[destek forumu](https://forum.aspose.com/c/words/8) yardım için.