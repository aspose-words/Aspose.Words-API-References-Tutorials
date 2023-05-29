---
title: Eksen İçin Sayı Formatı
linktitle: Eksen İçin Sayı Formatı
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir grafikte bir eksen için sayı biçimini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/number-format-for-axis/
---

Bu öğretici, Aspose.Words for .NET'in grafikteki bir eksen için sayı formatını ayarlamak üzere nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve eksen etiketlerinin nasıl biçimlendirileceğini gösterir.

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
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## 4. Adım: Eksen etiketlerini biçimlendirin

 Y ekseni etiketlerinin sayı biçimini ayarlamak için şuraya erişin:`AxisY` grafiğin özelliğini ayarlayın ve`NumberFormat.FormatCode` özelliğini istediğiniz biçime getirin. Bu örnekte, sayıları binlik ayırıcılarla görüntülemek için biçimi "#,##0" olarak ayarladık.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## 5. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Bu, Aspose.Words for .NET kullanılarak eksen için sayı biçimini ayarlama uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Number Format For Axis için örnek kaynak kodu 

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
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```