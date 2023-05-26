---
title: Eksen Üzerindeki Etiketler Arasındaki Aralık Birimi
linktitle: Eksen Üzerindeki Etiketler Arasındaki Aralık Birimi
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir grafiğin ekseni üzerindeki etiketler arasındaki aralık birimini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

Bu eğitim, bir grafiğin ekseni üzerindeki etiketler arasındaki aralık birimini ayarlamak için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve eksen etiketlerinin nasıl özelleştirileceğini gösterir.

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

 Ardından,`InsertChart` yöntemi`DocumentBuilder` belgeye bir sütun grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Seri verilerini grafiğe ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte, karşılık gelen değerleri ile beş öğe ekleyeceğiz.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 4. Adım: Eksen etiketlerini özelleştirin

 X eksenindeki etiketler arasındaki aralık birimini ayarlamak için şuraya erişin:`AxisX` grafiğin özelliğini ayarlayın ve`TickLabelSpacing` özelliği istenen değere getirin. Bu örnekte, aralığı 2 olarak ayarladık.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## 5. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Bu, Aspose.Words for .NET kullanılarak eksen üzerindeki etiketler arasındaki aralık birimini ayarlama uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Eksen Üzerindeki Etiketler Arasındaki Aralık Birimi için örnek kaynak kodu 

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
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```