---
title: Bir Grafikte XY Ekseni Özelliklerini Tanımlama
linktitle: Bir Grafikte XY Ekseni Özelliklerini Tanımlama
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir grafikte XY ekseni özelliklerini nasıl tanımlayacağınızı öğrenin. X ve Y eksenleri için özelleştirme seçenekleri gösterilmektedir.
type: docs
weight: 10
url: /tr/net/programming-with-charts/define-xyaxis-properties/
---

Bu eğitim, bir grafikte X ve Y eksenlerinin özelliklerini tanımlamak için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve eksen özelliklerinin nasıl özelleştirileceğini gösterir.

## 1. Adım: Projeyi kurun

Aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı yüklendi. Yüklemek için NuGet paket yöneticisini kullanarak indirebilirsiniz.
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
	//Belge dizininizin yolu
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

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir grafikte X ve Y eksenleri için özelliklerin nasıl tanımlanacağını öğrendiniz. Adım adım kılavuzu izleyerek bir grafik oluşturabilir, seri verileri ekleyebilir ve eksen özelliklerini özel gereksinimlerinizi karşılayacak şekilde özelleştirebilirsiniz. Aspose.Words for .NET, Word belgelerindeki grafiklerle Word Processing için kapsamlı bir API sağlar ve eksenler dahil olmak üzere grafiğin çeşitli yönlerini değiştirmenize olanak tanır.

 erişerek`ChartAxis` grafikle ilişkilendirilmiş nesneler, kategori türü, eksen geçişleri, onay işaretleri, etiket konumları, ölçekleme ve daha fazlası gibi özellikleri değiştirebilirsiniz. Bu esneklik, verilerinizi etkili bir şekilde sunmak için grafiğin eksenlerinin görünümünü ve davranışını uyarlamanıza olanak tanır.

Aspose.Words for .NET'i kullanarak, grafik oluşturma ve özelleştirme yeteneklerini .NET uygulamalarınıza sorunsuz bir şekilde entegre edebilir ve zengin görselleştirmelerle profesyonel görünümlü belgelerin oluşturulmasını otomatikleştirebilirsiniz.

### SSS

#### S1. Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin .NET uygulamalarında programlı olarak Word belgeleri oluşturmasına, değiştirmesine ve kaydetmesine olanak sağlayan güçlü bir belge işleme kitaplığıdır. Grafikler de dahil olmak üzere belge öğeleriyle Kelime İşleme için çok çeşitli özellikler sağlar.

#### S2. Aspose.Words for .NET'i nasıl kurabilirim?
Aspose.Words for .NET'i Visual Studio'daki NuGet paket yöneticisini kullanarak indirerek kurabilirsiniz. NuGet paket yöneticisinde "Aspose.Words" ifadesini arayın ve onu projenize kurun.

#### S3. Aspose.Words for .NET'i kullanarak grafiğin diğer özelliklerini özelleştirebilir miyim?
Evet, Aspose.Words for .NET, bir grafiğin çeşitli yönlerini özelleştirmek için kapsamlı yetenekler sağlar. Eksen özelliklerini tanımlamaya ek olarak, grafik tipini, veri serisini, açıklamayı, başlığı, çizim alanını, veri etiketlerini ve grafiğin diğer birçok öğesini değiştirebilirsiniz. API, grafik görünümü ve davranışı üzerinde ayrıntılı kontrol sunar.

#### S4. Aspose.Words for .NET kullanarak farklı türde grafikler oluşturabilir miyim?
Evet, Aspose.Words for .NET, alan, çubuk, çizgi, pasta, dağılım ve daha fazlasını içeren çok çeşitli grafik türlerini destekler. kullanabilirsiniz`ChartType` bir Word belgesine grafik şekli eklerken istenen grafik türünü belirtmek için numaralandırma.

#### S5. Grafiği farklı formatlarda kaydedebilir miyim?
 Evet, Aspose.Words for .NET, grafiği içeren belgeyi DOCX, PDF, HTML ve daha fazlası gibi çeşitli biçimlerde kaydetmenize olanak tanır. Gereksinimlerinize göre uygun formatı seçebilir ve`Save` yöntemi`Document` belgeyi kaydetmek için nesne.

#### S6. Bu teknikleri bir belgedeki birden çok grafiğe uygulayabilir miyim?
 Evet, her grafik için gerekli adımları tekrarlayarak bu teknikleri bir belgedeki birden çok grafiğe uygulayabilirsiniz. ayrı oluşturabilirsiniz`Chart` Ve`ChartAxis` her grafik için nesneler ve özelliklerini buna göre özelleştirin. Aspose.Words for .NET, tek bir belgede birden çok grafikle Kelime İşleme için tam destek sağlar.