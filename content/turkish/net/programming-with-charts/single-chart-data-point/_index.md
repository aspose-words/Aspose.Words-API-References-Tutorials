---
title: Bir Grafikte Tek Bir Grafik Veri Noktasını Özelleştirme
linktitle: Bir Grafikte Tek Bir Grafik Veri Noktasını Özelleştirme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir grafikteki tek bir veri noktasını nasıl özelleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/single-chart-data-point/
---

Bu eğitim, bir grafikte tek bir veri noktasını özelleştirmek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, belirli veri noktalarına nasıl erişileceğini ve bunların özelliklerinin nasıl değiştirileceğini gösterir.

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

 Ardından,`InsertChart` yöntemi`DocumentBuilder` belgeye bir çizgi grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Veri noktalarına erişin ve bunları özelleştirin

 Tek tek veri noktalarını değiştirmek için şuraya erişmeniz gerekir:`ChartDataPointCollection` dizini seçin ve dizini kullanarak istenen veri noktasını seçin.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## 4. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

Bu, Aspose.Words for .NET kullanılarak bir grafikte tek bir veri noktasının özelleştirilmesi uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Tek Grafik Veri Noktası için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir grafikteki tek bir veri noktasını nasıl özelleştireceğinizi öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak yeni bir belge oluşturabilir, çizgi grafiği ekleyebilir, grafik serisindeki belirli veri noktalarına erişebilir ve istenen özelleştirmeyi elde etmek için özelliklerini değiştirebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki çizelgeleri işlemek için güçlü özellikler sağlar. Bir grafik serisindeki ayrı veri noktalarına erişerek, görünümlerini ve davranışlarını özelleştirmek için belirli değişiklikler uygulayabilirsiniz. Bu, grafiğinizin görsel sunumunu geliştirmek için belirli veri noktalarını vurgulamanıza, işaretçi sembollerini değiştirmenize, işaretçi boyutlarını ayarlamanıza ve daha pek çok şeye olanak tanır.

Bireysel veri noktalarını özelleştirmek, grafiğinizdeki önemli verileri veya belirli eğilimleri vurgulama esnekliği sağlar. Aspose.Words for .NET ile çeşitli grafik türlerindeki veri noktalarına kolayca erişebilir ve bunları değiştirebilir, böylece Word belgelerinizde görsel olarak çekici ve bilgilendirici grafikler oluşturabilirsiniz.

### SSS

#### S1. Bir grafikte birden fazla veri noktasını özelleştirebilir miyim?
 Evet, Aspose.Words for .NET'i kullanarak bir grafikte birden çok veri noktasını özelleştirebilirsiniz. erişerek`ChartDataPointCollection`bir serinin birden çok veri noktasını indekslerine göre seçebilir ve değiştirebilirsiniz. Her veri noktası için istenen özellikleri değiştirmek üzere bir döngü veya bireysel atamalar kullanın. Bu şekilde, aynı grafikteki birden fazla veri noktasına farklı özelleştirmeler uygulayabilirsiniz.

#### S2. Bir veri noktası için işaretçi sembolünü nasıl değiştirebilirim?
 Aspose.Words for .NET kullanarak bir grafikteki bir veri noktası için işaretçi sembolünü değiştirmek için şuraya erişmeniz gerekir:`Marker` mülkiyeti`ChartDataPoint` nesne ve ayarlayın`Symbol` özelliğini istediğiniz işaretleyici sembolüne değiştirin. İşaret sembolleri, grafikteki her bir veri noktasını temsil etmek için kullanılan şekli veya simgeyi temsil eder. Daire, kare, baklava, üçgen, yıldız ve daha fazlası gibi çeşitli yerleşik işaretçi sembolleri arasından seçim yapabilirsiniz.

#### S3. Bir veri noktası işaretçisinin boyutunu ayarlayabilir miyim?
 Evet, Aspose.Words for .NET kullanarak bir grafikteki veri noktası işaretçisinin boyutunu ayarlayabilirsiniz. Erişmek`Marker` mülkiyeti`ChartDataPoint` nesne ve ayarlayın`Size`özelliğini istediğiniz işaretçi boyutuna ayarlayın. İşaretçinin boyutu tipik olarak, daha büyük bir değerin daha büyük bir işaretçi boyutunu temsil ettiği noktalarda belirtilir. İşaretçi boyutunu ayarlamak, belirli veri noktalarını vurgulamanıza veya önem derecelerine göre ayırt etmenize olanak tanır.

#### S4. Bir veri noktası için başka hangi özellikleri değiştirebilirim?
Aspose.Words for .NET, bir grafikteki bir veri noktası için değiştirebileceğiniz bir dizi özellik sağlar. Yaygın olarak değiştirilen özelliklerden bazıları, işaretçi sembolü, işaretçi boyutu, işaretçi rengi, veri etiketi görünürlüğü, patlama, negatifse ters çevir ve daha fazlasını içerir. Bu özellikler, bireysel veri noktalarının görünümünü, davranışını ve etkileşimini özelleştirmenize izin vererek, özel gereksinimlerinize uygun grafikler oluşturmanıza olanak tanır.

#### S5. Diğer grafik türlerinde veri noktalarını özelleştirebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak çeşitli grafik türlerindeki veri noktalarını özelleştirebilirsiniz. Bu öğretici bir çizgi grafikte veri noktalarının özelleştirilmesini gösterirken, benzer teknikleri sütun grafikler, çubuk grafikler, pasta grafikler ve daha fazlası gibi diğer grafik türlerine uygulayabilirsiniz. Süreç, tablodaki serilere ve veri noktalarına erişmeyi ve bunların özelliklerini buna göre değiştirmeyi içerir.