---
title: Grafiğin Eksenine Tarih Saat Değerleri Ekleme
linktitle: Grafiğin Eksenine Tarih Saat Değerleri Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak bir grafiğin eksenine tarih saat değerlerini nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/date-time-values-to-axis/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir grafiğin eksenine tarih saat değerlerinin nasıl ekleneceği açıklanmaktadır.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmaya itiraz edin.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Grafik Şekli Ekleme ve Yapılandırma
 kullanarak belgeye bir grafik şekli ekleyin.`InsertChart` yöntemi`DocumentBuilder` nesne. İstediğiniz grafik türünü ve boyutlarını ayarlayın.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## 4. Adım: Grafiğe Veri Ekleme
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

## Adım 5: Ekseni Yapılandırın
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

## Adım 6: Belgeyi Kaydedin
 Belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithCharts.DateTimeValuesToAxis.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Aspose.Words for .NET kullanılarak Eksene Tarih Saat Değerleri için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
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
	// Ana birimleri bir haftaya, küçük birimleri ise bir güne ayarlayın.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Bu örnek kod, yeni bir Word belgesi oluşturur, X eksenine tarih saat değerlerini içeren bir sütun grafiği ekler ve belgeyi belirtilen dizine kaydeder.

## Çözüm
Bu eğitimde Aspose.Words for .NET'i kullanarak bir grafiğin eksenine tarih saat değerlerini nasıl ekleyeceğinizi öğrendiniz. Adım adım kılavuzu takip ederek bir grafik oluşturabilir, seriye tarih saat değerleri ekleyebilir ve ekseni, tarih saat değerlerini doğru görüntüleyecek şekilde yapılandırabilirsiniz. Aspose.Words for .NET, Word belgelerindeki grafiklerle Kelime İşleme için güçlü bir dizi özellik sunarak, verileri tarih ve saat değerleriyle etkili bir şekilde temsil etmenize ve görselleştirmenize olanak tanır.

### SSS

#### S1. Aspose.Words for .NET kullanarak bir grafiğin eksenine tarih ve saat değerleri ekleyebilir miyim?
Evet, Aspose.Words for .NET ile bir Word belgesindeki grafiğin ekseninde tarih ve saat değerleri ekleyebilir ve görüntüleyebilirsiniz. Aspose.Words, eksende tarih ve saat değerlerinin işlenmesi de dahil olmak üzere çeşitli grafik türleriyle çalışmak ve görünümlerini özelleştirmek için API'ler ve işlevler sağlar.

#### Q2. Grafik serisine tarih saat değerlerini nasıl eklerim?
 Grafik serisine tarih saat değerleri eklemek için`Add`Grafiğin serisinin yöntemi. İlgili seri değerleriyle birlikte kategori (X ekseni) verileri olarak bir tarih saat değerleri dizisi sağlayın. Bu, grafikte tarih saat değerlerine sahip veri noktalarını çizmenize olanak tanır.

#### S3. Ekseni tarih saat değerlerini görüntüleyecek şekilde nasıl yapılandırabilirim?
 Uygun özellikleri ayarlayarak grafiğin eksenini tarih saat değerlerini görüntüleyecek şekilde yapılandırabilirsiniz. Örneğin eksen için minimum ve maksimum değerleri şunu kullanarak belirleyebilirsiniz:`Scaling.Minimum` Ve`Scaling.Maximum` sırasıyla özellikler. Ayrıca eksen için aralığı ve onay işaretlerini tanımlamak üzere ana ve küçük birimleri ayarlayabilirsiniz.
