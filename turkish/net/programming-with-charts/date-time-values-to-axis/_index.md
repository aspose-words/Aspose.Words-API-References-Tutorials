---
title: Grafiğin Eksenine Tarih Saat Değerleri Ekleme
linktitle: Grafiğin Eksenine Tarih Saat Değerleri Ekleme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir grafiğin eksenine tarih saat değerleri eklemeyi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/date-time-values-to-axis/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir grafiğin eksenine tarih saat değerlerinin nasıl ekleneceğini açıklar.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluştur`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmak için nesne.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Bir Grafik Şekli Ekleyin ve Yapılandırın
 kullanarak belgeye bir grafik şekli ekleyin.`InsertChart` yöntemi`DocumentBuilder` nesne. İstenen grafik türünü ve boyutlarını ayarlayın.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## 4. Adım: Grafiğe Veri Ekleyin
Tarih saat değerleri de dahil olmak üzere grafik serisine veri ekleyin.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## 5. Adım: Ekseni Yapılandırın
Tarih saat değerlerini görüntülemek için grafiğin X eksenini yapılandırın.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## 6. Adım: Belgeyi Kaydedin
 kullanarak belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithCharts.DateTimeValuesToAxis.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Aspose.Words for .NET kullanan Date Time Values To Axis için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Büyük birimleri bir haftaya ve küçük birimleri bir güne ayarlayın.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Bu örnek kod, yeni bir Word belgesi oluşturur, X ekseninde tarih saat değerleri olan bir sütun grafiği ekler ve belgeyi belirtilen dizine kaydeder.

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir grafiğin eksenine tarih saat değerlerinin nasıl ekleneceğini öğrendiniz. Adım adım kılavuzu izleyerek bir grafik oluşturabilir, seriye tarih saat değerleri ekleyebilir ve ekseni tarih saat değerlerini doğru gösterecek şekilde yapılandırabilirsiniz. Aspose.Words for .NET, Word belgelerindeki grafiklerle Kelime İşleme için güçlü bir dizi özellik sunarak verileri tarih saat değerleriyle etkili bir şekilde temsil etmenize ve görselleştirmenize olanak tanır.

### SSS

#### S1. Aspose.Words for .NET kullanarak bir grafiğin eksenine tarih saat değerleri ekleyebilir miyim?
Evet, Aspose.Words for .NET ile bir Word belgesindeki bir grafiğin ekseninde tarih saat değerleri ekleyebilir ve görüntüleyebilirsiniz. Aspose.Words, eksende tarih saat değerlerinin işlenmesi de dahil olmak üzere çeşitli grafik türleriyle çalışmak ve bunların görünümünü özelleştirmek için API'ler ve işlevler sağlar.

#### S2. Grafik serisine tarih saat değerlerini nasıl eklerim?
 Grafik serisine tarih saat değerleri eklemek için`Add`grafik serisinin yöntemi. İlgili seri değerleriyle birlikte kategori (X ekseni) verileri olarak bir tarih saat değerleri dizisi sağlayın. Bu, veri noktalarını grafikte tarih saat değerleri ile çizmenizi sağlar.

#### S3. Ekseni tarih saat değerlerini gösterecek şekilde nasıl yapılandırabilirim?
 Grafiğin eksenini, uygun özellikleri ayarlayarak tarih saat değerlerini gösterecek şekilde yapılandırabilirsiniz. Örneğin, kullanarak eksen için minimum ve maksimum değerleri belirleyebilirsiniz.`Scaling.Minimum` Ve`Scaling.Maximum` sırasıyla özellikler. Ek olarak, eksen için aralığı ve onay işaretlerini tanımlamak üzere ana ve küçük birimleri ayarlayabilirsiniz.
