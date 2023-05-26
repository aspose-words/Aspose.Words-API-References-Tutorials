---
title: Grafik Eksenini Gizle
linktitle: Grafik Eksenini Gizle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir belgede grafik eksenini nasıl gizleyeceğinizi öğrenin. Daha temiz ve daha odaklı bir grafik görüntüsü için ekseni gizleyin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/hide-chart-axis/
---

Bu eğitim, bir belgede grafik eksenini gizlemek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve grafik ekseninin nasıl gizleneceğini gösterir.

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

 Ardından, kullanarak belgeye bir grafik ekleyin.`InsertChart` yöntemi`DocumentBuilder`. Bu örnekte, bir sütun grafiği ekleyeceğiz.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Seri verilerini grafiğe ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte, beş öğe ve bunlara karşılık gelen değerleri ekleyeceğiz.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 4. Adım: Grafik eksenini gizleyin

 Grafik eksenini gizlemek için şuraya erişin:`AxisY` grafiğin özelliğini ayarlayın ve`Hidden` mülkiyet`true`.

```csharp
chart.AxisY.Hidden = true;
```

Bu örnekte, grafiğin Y eksenini gizleriz.

## 5. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Bu, Aspose.Words for .NET kullanarak grafik eksenini gizleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Hide Chart Axis için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```