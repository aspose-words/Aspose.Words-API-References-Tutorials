---
title: Tek Grafik Serisi
linktitle: Tek Grafik Serisi
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir grafikte tekli grafik serilerini nasıl özelleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/single-chart-series/
---

Bu öğretici Aspose.Words for .NET'in bir grafikteki tekli grafik serilerini özelleştirmek için nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, belirli serilere nasıl erişileceğini ve bunların özelliklerinin nasıl değiştirileceğini gösterir.

## 1. Adım: Projeyi kurun

Aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı yüklendi. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet paket yöneticisini kullanabilirsiniz.
- Çıktı belgesinin kaydedileceği bir belge dizini yolu.

## 2. Adım: Yeni bir belge oluşturun ve bir grafik ekleyin

 Yeni bir tane oluştur`Document` nesne ve bir`DocumentBuilder` belgeyi oluşturmak için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ardından,`InsertChart` yöntemi`DocumentBuilder` belgeye bir çizgi grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Grafik serisine erişin ve özelleştirin

 Tekli grafik serisini değiştirmek için şuraya erişmeniz gerekir:`ChartSeries` grafiğin nesneleri.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## 4. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Bu, Aspose.Words for .NET kullanarak tek bir grafik serisini özelleştirme uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Single Chart Series için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Grafikteki noktaları birleştiren çizginin Catmull-Rom çizgileri kullanılarak yumuşatılıp yumuşatılmayacağını da belirleyebilirsiniz.
	series0.Smooth = true;
	series1.Smooth = true;
	// Değer negatifse varsayılan olarak üst öğenin renklerini tersine çevirip çevirmeyeceğini belirtir.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```