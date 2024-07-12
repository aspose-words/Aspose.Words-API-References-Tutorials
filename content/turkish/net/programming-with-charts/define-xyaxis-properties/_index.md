---
title: Grafikte XY Ekseni Özelliklerini Tanımlama
linktitle: Grafikte XY Ekseni Özelliklerini Tanımlama
second_title: Aspose.Words Belge İşleme API'si
description: Bu adım adım kılavuzla Aspose.Words for .NET kullanarak bir grafikte XY ekseni özelliklerini nasıl tanımlayacağınızı öğrenin. .NET geliştiricileri için mükemmel.
type: docs
weight: 10
url: /tr/net/programming-with-charts/define-xyaxis-properties/
---
## giriiş

Grafikler verileri görselleştirmek için güçlü bir araçtır. Dinamik grafiklerle profesyonel belgeler oluşturmanız gerektiğinde Aspose.Words for .NET paha biçilmez bir kütüphanedir. Bu makale, Aspose.Words for .NET kullanarak bir grafikte XY ekseni özelliklerini tanımlama sürecinde size yol gösterecek ve netlik ve anlaşılırlık sağlamak için her adımı parçalara ayıracaktır.

## Önkoşullar

Kodlamaya başlamadan önce yerine getirmeniz gereken birkaç önkoşul vardır:

1.  Aspose.Words for .NET: Aspose.Words for .NET kitaplığına sahip olduğunuzdan emin olun. Yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio gibi entegre bir geliştirme ortamına (IDE) ihtiyacınız var.
3. .NET Framework: Geliştirme ortamınızın .NET geliştirme için ayarlandığından emin olun.
4. Temel C# Bilgisi: Bu kılavuz, C# programlama konusunda temel bilgiye sahip olduğunuzu varsaymaktadır.

## Ad Alanlarını İçe Aktar

Başlangıç olarak projenize gerekli ad alanlarını içe aktarmanız gerekir. Bu, belgeleri ve grafikleri oluşturmak ve değiştirmek için gereken tüm sınıflara ve yöntemlere erişmenizi sağlar.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

Süreci, her biri bir grafikte XY ekseni özelliklerini tanımlamanın belirli bir kısmına odaklanan basit adımlara ayıracağız.

## Adım 1: Document'ı ve DocumentBuilder'ı başlatın

 Öncelikle yeni bir belge başlatmanız gerekir ve`DocumentBuilder` nesne.`DocumentBuilder` belgeye içerik eklenmesine yardımcı olur.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Grafik Ekleme

Daha sonra belgeye bir grafik ekleyeceksiniz. Bu örnekte Alan grafiği kullanacağız. Grafiğin boyutlarını gerektiği gibi özelleştirebilirsiniz.

```csharp
// Grafik ekle
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Varsayılan Seriyi Temizleyin ve Özel Verileri Ekleyin

Varsayılan olarak grafikte önceden tanımlanmış bazı seriler bulunur. Bunları temizleyip özel veri serimizi ekleyeceğiz.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
	new DateTime[]
	{
		new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
		new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
	},
	new double[] { 640, 320, 280, 120, 150 });
```

## Adım 4: X Ekseni Özelliklerini Tanımlayın

Şimdi X ekseninin özelliklerini tanımlamanın zamanı geldi. Buna kategori tipinin ayarlanması, eksen geçişinin özelleştirilmesi ve onay işaretlerinin ve etiketlerin ayarlanması da dahildir.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3; // ekseninin görüntü birimleri (yüzlerce) cinsinden ölçülür.
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;
```

## Adım 5: Y Ekseni Özelliklerini Tanımlayın

Benzer şekilde Y ekseninin özelliklerini de ayarlayacaksınız. Bu, onay etiketi konumunun, ana ve küçük birimlerin, görüntüleme biriminin ve ölçeklendirmenin ayarlanmasını içerir.

```csharp
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Adım 6: Belgeyi Kaydedin

Son olarak belgeyi belirttiğiniz dizine kaydedin. Bu, özelleştirilmiş grafiği içeren Word belgesini oluşturacaktır.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Çözüm

Aspose.Words for .NET'i kullanarak Word belgelerinde grafikler oluşturmak ve özelleştirmek, ilgili adımları anladığınızda çok kolaydır. Bu kılavuz, belgenin başlatılmasından son ürünün kaydedilmesine kadar, bir grafikte XY ekseni özelliklerini tanımlama sürecinde size yol göstermiştir. Bu becerilerle belgelerinizi geliştiren ayrıntılı, profesyonel görünümlü grafikler oluşturabilirsiniz.

## SSS'ler

### Aspose.Words for .NET ile ne tür grafikler oluşturabilirim?
Alan, Çubuk, Çizgi, Pasta ve daha fazlasını içeren çeşitli grafik türleri oluşturabilirsiniz.

### Aspose.Words for .NET'i nasıl yüklerim?
 Aspose.Words for .NET'i şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/words/net/) ve verilen kurulum talimatlarını izleyin.

### Grafiklerimin görünümünü özelleştirebilir miyim?
Evet, Aspose.Words for .NET renkler, yazı tipleri ve eksen özellikleri de dahil olmak üzere grafiklerin kapsamlı şekilde özelleştirilmesine olanak tanır.

### Aspose.Words for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).

### Daha fazla öğreticiyi ve belgeyi nerede bulabilirim?
 Daha fazla eğitim ve ayrıntılı belgeyi şu adreste bulabilirsiniz:[Aspose.Words for .NET dokümantasyon sayfası](https://reference.aspose.com/words/net/).
