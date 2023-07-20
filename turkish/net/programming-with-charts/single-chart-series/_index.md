---
title: Bir Grafikte Tek Grafik Serisini Özelleştirme
linktitle: Bir Grafikte Tek Grafik Serisini Özelleştirme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir grafikte tekli grafik serilerini nasıl özelleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/single-chart-series/
---

Bu öğretici Aspose.Words for .NET'in bir grafikteki tekli grafik serilerini özelleştirmek için nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, belirli serilere nasıl erişileceğini ve bunların özelliklerinin nasıl değiştirileceğini gösterir.

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
	//Belge dizininizin yolu
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

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir grafikteki tek bir grafik serisini nasıl özelleştireceğinizi öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak yeni bir belge oluşturabilir, çizgi grafiği ekleyebilir, belirli grafik serilerine erişebilir ve istenen özelleştirmeyi elde etmek için özelliklerini değiştirebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki çizelgeleri işlemek için güçlü özellikler sağlar. Tek tek grafik serilerine erişerek, görünümlerini ve davranışlarını özelleştirmek için belirli değişiklikler uygulayabilirsiniz. Bu, seri adını değiştirmenize, grafik çizgisinin düzgünleştirilmesini etkinleştirmenize, veri noktaları için işaretçileri özelleştirmenize, negatif değerler için renkleri ters çevirmenize ve grafiğinizin görsel temsilini geliştirmek için daha fazlasına olanak tanır.

Tek bir grafik serisini özelleştirmek, grafiğinizdeki belirli verileri veya belirli eğilimleri vurgulama esnekliği sağlar. Aspose.Words for .NET ile, Word belgelerinizde görsel olarak çekici ve bilgilendirici grafikler oluşturmanıza olanak tanıyan grafik serisi özelliklerine kolayca erişebilir ve bunları değiştirebilirsiniz.

### SSS

#### S1. Bir grafikte birden fazla grafik serisini özelleştirebilir miyim?
 Evet, Aspose.Words for .NET'i kullanarak bir grafikte birden fazla grafik serisini özelleştirebilirsiniz. erişerek`ChartSeries`grafikteki nesneler, dizinlerine veya belirli ölçütlerine göre birden çok seriyi seçebilir ve değiştirebilirsiniz. Her grafik serisi için istenen özellikleri değiştirmek üzere bir döngü veya bireysel atamalar kullanın. Bu şekilde, aynı grafikte birden çok seriye farklı özelleştirmeler uygulayabilirsiniz.

#### S2. Bir grafik serisinin adını nasıl değiştirebilirim?
 Aspose.Words for .NET kullanarak bir grafikteki grafik serisinin adını değiştirmek için`Name` mülkiyeti`ChartSeries` nesneyi seçin ve istediğiniz isme ayarlayın. Seri adı, genellikle grafik açıklamalarında veya veri etiketlerinde görüntülenir ve seri için açıklayıcı bir etiket sağlar. Seri adını değiştirerek, her seri tarafından temsil edilen verileri yansıtan anlamlı isimler sağlayabilirsiniz.

#### S3. Grafik serisi yumuşatma nedir?
Grafik serisi yumuşatma, grafikteki noktaları birleştiren düzgün bir çizgi oluşturmanıza olanak tanıyan görsel bir geliştirme tekniğidir. Veri noktaları arasında enterpolasyon yapmak ve görsel olarak hoş bir eğri oluşturmak için Catmull-Rom çizgileri gibi bir yumuşatma algoritması uygular. Aspose.Words for .NET kullanarak bir grafikte seri düzeltmeyi etkinleştirmek için şuraya erişin:`Smooth` mülkiyeti`ChartSeries` nesne ve onu ayarla`true`. Düzleştirme, düzensiz dalgalanmalara sahip verilerdeki eğilimleri veya kalıpları görüntülemek için yararlı olabilir.

#### S4. Bir grafik serisindeki veri noktaları için işaretçileri nasıl özelleştirebilirim?
 Aspose.Words for .NET kullanarak bir grafik serisindeki veri noktaları için işaretçileri özelleştirmek için`Marker` mülkiyeti`ChartSeries` nesne ve onun gibi özelliklerini değiştirin`Symbol` Ve`Size`. İşaretçiler, tek tek veri noktalarını temsil etmek için tabloya yerleştirilen görsel göstergelerdir. Çeşitli yerleşik işaretçi sembolleri arasından seçim yapabilir ve serideki belirli veri noktalarını vurgulamak veya ayırt etmek için boyutlarını ayarlayabilirsiniz.

#### S5. Bir grafik serisindeki negatif değerler için renkleri tersine çevirebilir miyim?
 Evet, Aspose.Words for .NET kullanarak bir grafik serisindeki negatif değerler için renkleri ters çevirebilirsiniz. ayarlayarak`InvertIfNegative` mülkiyeti`ChartSeries` itiraz etmek`true`, negatif değerlere sahip veri noktalarının renkleri ters çevrilerek görsel olarak pozitif değerlerden farklı hale getirilir. Bu özellik, bir grafik serisindeki pozitif ve negatif değerleri karşılaştırırken faydalı olabilir ve ikisi arasında net bir ayrım sağlar.