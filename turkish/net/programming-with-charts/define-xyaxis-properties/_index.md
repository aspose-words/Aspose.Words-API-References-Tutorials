---
title: XYAxis Özelliklerini Tanımlayın
linktitle: XYAxis Özelliklerini Tanımlayın
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir grafikte XY ekseni özelliklerini nasıl tanımlayacağınızı öğrenin. X ve Y eksenleri için özelleştirme seçenekleri gösterilmektedir.
type: docs
weight: 10
url: /tr/net/programming-with-charts/define-xyaxis-properties/
---

Bu eğitim, bir grafikte X ve Y eksenlerinin özelliklerini tanımlamak için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve eksen özelliklerinin nasıl özelleştirileceğini gösterir.

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

 Ardından, kullanarak belgeye bir grafik ekleyin.`InsertChart` yöntemi`DocumentBuilder`. Bu örnekte, bir alan grafiği ekleyeceğiz.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Seri verilerini grafiğe ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte, karşılık gelen tarihler ve değerlerle birlikte beş veri noktası ekleyeceğiz.

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

## 4. Adım: X ve Y ekseni özelliklerini özelleştirin

 X ve Y eksenlerinin özelliklerini özelleştirmek için şuraya erişin:`ChartAxis` grafikle ilişkili nesneler.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Özelliklerini değiştirin`xAxis` Ve`yAxis` ve Y eksenleri için istenen seçenekleri ayarlamak için nesneler. Bu örnekte, özelleştirilebilen bazı genel özellikleri göstereceğiz.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## 5. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

Bu, Aspose.Words for .NET kullanan bir grafikte XY ekseni özelliklerini tanımlama uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak XYAxis Özelliklerini Tanımlamak için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Grafik ekle
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// X eksenini tarih yerine kategori olacak şekilde değiştirin, böylece tüm noktalar X eksenine eşit aralıklarla konulacaktır.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; // Y ekseninin gösterge birimleriyle ölçülmüştür (yüzlerce).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```