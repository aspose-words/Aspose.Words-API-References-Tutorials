---
title: Bir Word Belgesinde Grafik Eksenini Gizleme
linktitle: Bir Word Belgesinde Grafik Eksenini Gizleme
second_title: Aspose.Words Belge İşleme API'si
description: Ayrıntılı, adım adım eğitimimizle Aspose.Words for .NET kullanarak bir Word belgesinde grafik eksenini nasıl gizleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/hide-chart-axis/
---
## giriiş

Dinamik ve görsel olarak çekici Word belgeleri oluşturmak genellikle çizelge ve grafiklerin eklenmesini içerir. Böyle bir senaryo, daha temiz bir sunum için grafik ekseninin gizlenmesini gerektirebilir. Aspose.Words for .NET bu tür görevler için kapsamlı ve kullanımı kolay bir API sağlar. Bu eğitim, Aspose.Words for .NET kullanarak bir Word belgesinde bir grafik eksenini gizleme adımlarında size rehberlik edecektir.

## Önkoşullar

Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET: Buradan indirebilirsiniz.[Burada](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Visual Studio gibi .NET geliştirmeyi destekleyen herhangi bir IDE.
- .NET Framework: Makinenizde .NET Framework'ün kurulu olduğundan emin olun.
- Temel C# Bilgisi: C# programlama diline aşina olmak faydalı olacaktır.

## Ad Alanlarını İçe Aktar

Aspose.Words for .NET ile çalışmaya başlamak için gerekli ad alanlarını projenize aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

Süreci basit, takip edilmesi kolay adımlara ayıralım.

## Adım 1: Document'ı ve DocumentBuilder'ı başlatın

İlk adım, yeni bir Word belgesi oluşturmayı ve DocumentBuilder nesnesini başlatmayı içerir.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Bu adımda belgenin kaydedileceği yolu tanımlıyoruz. Daha sonra yeni bir tane oluşturuyoruz`Document` nesne ve bir`DocumentBuilder` belgemizi oluşturmaya başlamak için nesne.

## 2. Adım: Grafik Ekleme

 Daha sonra belgeye bir grafik ekleyeceğiz.`DocumentBuilder` nesne.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

 Burada belirtilen boyutlara sahip bir sütun grafiği ekliyoruz.`InsertChart` yöntem bir döndürür`Shape` grafiği içeren nesne.

## 3. Adım: Mevcut Serileri Temizle

Grafiğe yeni veri eklemeden önce mevcut serileri temizlememiz gerekiyor.

```csharp
chart.Series.Clear();
```

Bu adım, grafikteki tüm varsayılan verilerin kaldırılmasını sağlayarak, daha sonra ekleyeceğimiz yeni verilere yer açar.

## Adım 4: Seri Verilerini Ekleyin

Şimdi kendi veri serimizi grafiğe ekleyelim.

```csharp
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

Bu adımda ilgili kategoriler ve değerlerle birlikte "Aspose Series 1" başlıklı bir seri ekliyoruz.

## Adım 5: Y Eksenini Gizleyin

 Grafiğin Y eksenini gizlemek için basitçe`Hidden` Y ekseninin özelliği`true`.

```csharp
chart.AxisY.Hidden = true;
```

Bu kod satırı Y eksenini gizleyerek onu grafikte görünmez hale getirir.

## Adım 6: Belgeyi Kaydedin

Son olarak belgeyi belirtilen dizine kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Bu komut, grafik içeren Word belgesini belirtilen yola kaydeder.

## Çözüm

Tebrikler! Aspose.Words for .NET'i kullanarak bir Word belgesinde grafik eksenini nasıl gizleyeceğinizi başarıyla öğrendiniz. Bu güçlü kitaplık, Word belgelerini programlı olarak yönetmeyi kolaylaştırır. Bu adımları izleyerek minimum çabayla özelleştirilmiş ve profesyonel görünümlü belgeler oluşturabilirsiniz.

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, .NET uygulamalarında Word belgelerini oluşturmak, düzenlemek, dönüştürmek ve değiştirmek için güçlü bir API'dir.

### Bir grafikte hem X hem de Y eksenlerini gizleyebilir miyim?
 Evet, her iki ekseni de gizleyebilirsiniz.`Hidden` her ikisinin de malı`AxisX`Ve`AxisY` ile`true`.

### Aspose.Words for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).

### Daha fazla belgeyi nerede bulabilirim?
 Aspose.Words for .NET'te ayrıntılı belgeler bulabilirsiniz.[Burada](https://reference.aspose.com/words/net/).

### Aspose.Words for .NET için nasıl destek alabilirim?
 Aspose topluluğundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/words/8).
