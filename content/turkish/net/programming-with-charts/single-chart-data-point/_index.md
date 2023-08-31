---
title: Grafikteki Tek Grafik Veri Noktasını Özelleştirme
linktitle: Grafikteki Tek Grafik Veri Noktasını Özelleştirme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak bir grafikteki tek bir veri noktasını nasıl özelleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/single-chart-data-point/
---

Bu eğitimde, bir grafikteki tek bir veri noktasını özelleştirmek için Aspose.Words for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, belirli veri noktalarına nasıl erişileceğini ve bunların özelliklerinin nasıl değiştirileceğini gösterir.

## 1. Adım: Projeyi ayarlayın

Aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kütüphanesi kuruldu. Yüklemek için NuGet paket yöneticisini kullanarak indirebilirsiniz.
- Çıktı belgesinin kaydedileceği belge dizini yolu.

## 2. Adım: Yeni bir belge oluşturun ve grafik ekleyin

 Yeni bir tane oluştur`Document` nesne ve bir`DocumentBuilder` belgeyi oluşturmak için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Daha sonra şunu kullanın:`InsertChart` yöntemi`DocumentBuilder` Belgeye çizgi grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Veri noktalarına erişin ve bunları özelleştirin

 Bireysel veri noktalarını değiştirmek için`ChartDataPointCollection` diziyi seçin ve dizini kullanarak istediğiniz veri noktasını seçin.

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

Bu, Aspose.Words for .NET kullanarak bir grafikteki tek bir veri noktasının özelleştirilmesi uygulamasını tamamlıyor.

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

Bu eğitimde Aspose.Words for .NET'i kullanarak bir grafikteki tek bir veri noktasını nasıl özelleştireceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodunu kullanarak yeni bir belge oluşturabilir, bir çizgi grafik ekleyebilir, grafik serisi içindeki belirli veri noktalarına erişebilir ve istediğiniz özelleştirmeyi elde etmek için bunların özelliklerini değiştirebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafikleri yönetmek için güçlü özellikler sağlar. Bir grafik serisindeki tek tek veri noktalarına erişerek, bunların görünümlerini ve davranışlarını özelleştirmek için belirli değişiklikler uygulayabilirsiniz. Bu, grafiğinizin görsel temsilini geliştirmek için belirli veri noktalarını vurgulamanıza, işaretçi sembollerini değiştirmenize, işaretçi boyutlarını ayarlamanıza ve daha pek çok şeye olanak tanır.

Bireysel veri noktalarını özelleştirmek, size önemli verileri vurgulama veya grafiğinizdeki belirli eğilimleri vurgulama esnekliği sağlar. Aspose.Words for .NET ile çeşitli grafik türlerindeki veri noktalarına kolayca erişebilir ve bunları değiştirebilirsiniz, böylece Word belgelerinizde görsel olarak çekici ve bilgilendirici grafikler oluşturabilirsiniz.

### SSS

#### S1. Bir grafikte birden fazla veri noktasını özelleştirebilir miyim?
 Evet, Aspose.Words for .NET'i kullanarak bir grafikteki birden fazla veri noktasını özelleştirebilirsiniz. Erişerek`ChartDataPointCollection`Bir serinin indekslerine göre birden fazla veri noktasını seçip değiştirebilirsiniz. Her veri noktası için istenen özellikleri değiştirmek üzere bir döngü veya bireysel atamalar kullanın. Bu şekilde aynı grafikteki birden fazla veri noktasına farklı özelleştirmeler uygulayabilirsiniz.

#### Q2. Bir veri noktasının işaretçi sembolünü nasıl değiştirebilirim?
 Aspose.Words for .NET kullanarak bir grafikteki bir veri noktasının işaretçi sembolünü değiştirmek için şu adrese erişmeniz gerekir:`Marker` mülkiyeti`ChartDataPoint` nesneyi ayarlayın ve`Symbol` özelliği istenen işaretleyici sembolüne ekleyin. İşaretçi sembolleri, grafikteki her veri noktasını temsil etmek için kullanılan şekli veya simgeyi temsil eder. Daire, kare, elmas, üçgen, yıldız ve daha fazlası gibi çeşitli yerleşik işaretleyici semboller arasından seçim yapabilirsiniz.

#### S3. Bir veri noktası işaretçisinin boyutunu ayarlayabilir miyim?
 Evet, Aspose.Words for .NET'i kullanarak bir grafikteki veri noktası işaretçisinin boyutunu ayarlayabilirsiniz. Erişmek`Marker` mülkiyeti`ChartDataPoint` nesneyi ayarlayın ve`Size`özelliği istenen işaretleyici boyutuna getirin. İşaretçinin boyutu genellikle noktalarla belirtilir; burada daha büyük bir değer, daha büyük bir işaretleyici boyutunu temsil eder. İşaretçi boyutunu ayarlamak, belirli veri noktalarını vurgulamanıza veya bunları önemlerine göre ayırmanıza olanak tanır.

#### S4. Bir veri noktası için başka hangi özellikleri değiştirebilirim?
Aspose.Words for .NET, bir grafikteki veri noktası için değiştirebileceğiniz bir dizi özellik sağlar. Yaygın olarak değiştirilen özelliklerden bazıları işaretleyici sembolü, işaretleyici boyutu, işaretleyici rengi, veri etiketi görünürlüğü, patlama, negatifse ters çevirme ve daha fazlasını içerir. Bu özellikler, bireysel veri noktalarının görünümünü, davranışını ve etkileşimini özelleştirmenize olanak tanıyarak özel gereksinimlerinize göre uyarlanmış grafikler oluşturmanıza olanak tanır.

#### S5. Diğer grafik türlerindeki veri noktalarını özelleştirebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak çeşitli grafik türlerindeki veri noktalarını özelleştirebilirsiniz. Bu eğitimde çizgi grafikteki veri noktalarının özelleştirilmesi gösterilirken, benzer teknikleri sütun grafikleri, çubuk grafikleri, pasta grafikleri ve daha fazlası gibi diğer grafik türlerine de uygulayabilirsiniz. Süreç, grafikteki serilere ve veri noktalarına erişmeyi ve bunların özelliklerini buna göre değiştirmeyi içerir.