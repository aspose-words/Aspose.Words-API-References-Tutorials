---
title: Dağılım Grafiği Ekle
linktitle: Dağılım Grafiği Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir belgeye dağılım grafiği eklemeyi öğrenin. X ve Y koordinatlarıyla seri verileri ekleyin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/insert-scatter-chart/
---

Bu öğretici, bir belgeye dağılım grafiği eklemek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve belgenin nasıl kaydedileceğini gösterir.

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

 Ardından,`InsertChart` yöntemi`DocumentBuilder` belgeye bir dağılım grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Seri verilerini grafiğe ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte, iki set X ve Y koordinatı ekleyeceğiz.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## 4. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Bu, Aspose.Words for .NET kullanarak bir dağılım grafiği ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Dağılım Grafiği Ekleme için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```