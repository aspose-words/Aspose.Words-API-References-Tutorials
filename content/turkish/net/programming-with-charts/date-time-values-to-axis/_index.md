---
title: Grafiğin Eksenine Tarih Saat Değerleri Ekleme
linktitle: Grafiğin Eksenine Tarih Saat Değerleri Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Bu kapsamlı adım adım kılavuzdan Aspose.Words for .NET kullanarak bir grafiğin eksenine tarih ve saat değerlerini nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/date-time-values-to-axis/
---
## giriiş

Belgelerde grafikler oluşturmak, verileri görselleştirmenin güçlü bir yolu olabilir. Zaman serisi verileriyle uğraşırken, grafiğin eksenine tarih ve saat değerlerinin eklenmesi netlik açısından çok önemlidir. Bu eğitimde, Aspose.Words for .NET'i kullanarak bir grafiğin eksenine tarih ve saat değerleri ekleme sürecinde size yol göstereceğiz. Bu adım adım kılavuz, ortamınızı kurmanıza, kodu yazmanıza ve sürecin her bölümünü anlamanıza yardımcı olacaktır. Hadi dalalım!

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. Visual Studio veya herhangi bir .NET IDE: .NET kodunuzu yazmak ve çalıştırmak için bir geliştirme ortamına ihtiyacınız vardır.
2.  Aspose.Words for .NET: Aspose.Words for .NET kütüphanesinin kurulu olması gerekir. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/net/).
3. Temel C# bilgisi: Bu eğitimde C# programlama konusunda temel bilgiye sahip olduğunuz varsayılmaktadır.
4.  Geçerli bir Aspose lisansı: Geçici bir lisansı şu adresten alabilirsiniz:[Burada](https://purchase.aspose.com/temporary-license/).

## Ad Alanlarını İçe Aktar

Başlamak için projenize gerekli ad alanlarının aktarıldığından emin olun. Bu adım Aspose.Words sınıflarına ve yöntemlerine erişim için çok önemlidir.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## 1. Adım: Belge Dizininizi Kurun

Öncelikle belgenizin kaydedileceği dizini tanımlamanız gerekir. Bu, dosyalarınızı düzenlemek ve kodunuzun doğru şekilde çalışmasını sağlamak için önemlidir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Yeni Bir Belge ve DocumentBuilder Oluşturun

 Daha sonra, yeni bir örneğini oluşturun.`Document` sınıf ve bir`DocumentBuilder` nesne. Bu nesneler belgenizi oluşturmanıza ve değiştirmenize yardımcı olacaktır.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Belgeye Grafik Ekleme

 Şimdi belgenize şunu kullanarak bir grafik ekleyin:`DocumentBuilder` nesne. Bu örnekte sütun grafiği kullanıyoruz ancak diğer türleri de seçebilirsiniz.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Adım 4: Mevcut Serileri Temizle

Boş bir sayfayla başladığınızdan emin olmak için grafikteki mevcut serileri temizleyin. Bu adım özel veriler için gereklidir.

```csharp
chart.Series.Clear();
```

## Adım 5: Seriye Tarih ve Saat Değerlerini Ekleme

Tarih ve saat değerlerinizi grafik serisine ekleyin. Bu adım, tarihler ve karşılık gelen değerler için diziler oluşturmayı içerir.

```csharp
chart.Series.Add("Aspose Series 1",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Adım 6: X Eksenini Yapılandırma

ekseni için ölçeklendirmeyi ve onay işaretlerini ayarlayın. Bu, tarihlerinizin doğru ve uygun aralıklarla görüntülenmesini sağlar.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Adım 7: Belgeyi Kaydedin

Son olarak belgenizi belirtilen dizine kaydedin. Bu adım süreci tamamlar ve belgeniz artık X ekseninde tarih ve saat değerlerini içeren bir grafik içermelidir.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

## Çözüm

Aspose.Words for .NET ile bir belgedeki grafiğin eksenine tarih ve saat değerleri eklemek basit bir işlemdir. Bu öğreticide özetlenen adımları izleyerek, zaman serisi verilerini etkili bir şekilde görselleştiren net ve bilgilendirici grafikler oluşturabilirsiniz. İster raporlar, sunumlar, ister ayrıntılı veri gösterimi gerektiren herhangi bir belge hazırlıyor olun, Aspose.Words başarılı olmanız için ihtiyacınız olan araçları sağlar.

## SSS'ler

### Aspose.Words for .NET ile diğer grafik türlerini kullanabilir miyim?

Evet, Aspose.Words çizgi, çubuk, pasta ve daha fazlasını içeren çeşitli grafik türlerini destekler.

### Grafiğimin görünümünü nasıl özelleştirebilirim?

Grafiğin özelliklerine erişerek ve stilleri, renkleri ve daha fazlasını ayarlayarak görünümü özelleştirebilirsiniz.

### Bir grafiğe birden fazla seri eklemek mümkün mü?

 Kesinlikle! Grafiğinize birden fazla seriyi çağırarak ekleyebilirsiniz.`Series.Add` yöntemi farklı verilerle birden çok kez kullanın.

### Grafik verilerini dinamik olarak güncellemem gerekirse ne olur?

İhtiyaçlarınıza göre seri ve eksen özelliklerini programlı olarak değiştirerek grafik verilerini dinamik olarak güncelleyebilirsiniz.

### Aspose.Words for .NET için daha ayrıntılı belgeleri nerede bulabilirim?

 Daha ayrıntılı belgeler bulabilirsiniz[Burada](https://reference.aspose.com/words/net/).