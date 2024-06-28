---
title: Bir Grafikte Tek Grafik Serisini Özelleştirme
linktitle: Bir Grafikte Tek Grafik Serisini Özelleştirme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak bir grafikteki tekli grafik serilerini nasıl özelleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/single-chart-series/
---

Bu eğitimde, bir grafikteki tek grafik serisini özelleştirmek için Aspose.Words for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, belirli serilere nasıl erişileceğini ve bunların özelliklerinin nasıl değiştirileceğini gösterir.

## 1. Adım: Projeyi ayarlayın

Aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kütüphanesi kuruldu. Yüklemek için NuGet paket yöneticisini kullanarak indirebilirsiniz.
- Çıktı belgesinin kaydedileceği belge dizini yolu.

## Adım 2: Yeni bir belge oluşturun ve bir grafik ekleyin.

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

## 3. Adım: Grafik serilerine erişin ve bunları özelleştirin

 Tek grafik serisini değiştirmek için`ChartSeries` grafiğin nesneleri.

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

Bu, Aspose.Words for .NET kullanarak tek bir grafik serisinin özelleştirilmesi uygulamasını tamamlıyor.

### Aspose.Words for .NET kullanan Tek Grafik Serisi için örnek kaynak kodu 

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
	// Ayrıca grafikteki noktaları birleştiren çizginin Catmull-Rom spline'ları kullanılarak yumuşatılıp yumuşatılmayacağını da belirleyebilirsiniz.
	series0.Smooth = true;
	series1.Smooth = true;
	// Değer negatifse ana öğenin varsayılan olarak renklerini ters çevirip çevirmeyeceğini belirtir.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## Çözüm

Bu eğitimde Aspose.Words for .NET'i kullanarak bir grafikteki tek bir grafik serisini nasıl özelleştireceğinizi öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak, yeni bir belge oluşturabilir, bir çizgi grafik ekleyebilir, belirli grafik serilerine erişebilir ve istediğiniz özelleştirmeyi elde etmek için bunların özelliklerini değiştirebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafikleri yönetmek için güçlü özellikler sağlar. Bireysel grafik serilerine erişerek, görünümlerini ve davranışlarını özelleştirmek için belirli değişiklikler uygulayabilirsiniz. Bu, grafiğinizin görsel temsilini geliştirmek için seri adını değiştirmenize, grafik çizgisinin yumuşatılmasını etkinleştirmenize, veri noktaları için işaretçileri özelleştirmenize, negatif değerler için renkleri ters çevirmenize ve daha fazlasını yapmanıza olanak tanır.

Tek bir grafik serisini özelleştirmek, grafiğinizdeki belirli verileri vurgulama veya belirli eğilimleri vurgulama esnekliği sağlar. Aspose.Words for .NET ile grafik serisi özelliklerine kolayca erişebilir ve bunları değiştirebilirsiniz, böylece Word belgelerinizde görsel olarak çekici ve bilgilendirici grafikler oluşturabilirsiniz.

### SSS

#### S1. Bir grafikte birden fazla grafik serisini özelleştirebilir miyim?
 Evet, Aspose.Words for .NET'i kullanarak bir grafikte birden fazla grafik serisini özelleştirebilirsiniz. Erişerek`ChartSeries`Grafikteki nesnelerde, indekslerine veya belirli kriterlerine göre birden fazla seriyi seçip değiştirebilirsiniz. Her grafik serisi için istenen özellikleri değiştirmek üzere bir döngü veya bireysel atamalar kullanın. Bu sayede aynı grafikteki birden fazla seriye farklı özelleştirmeler uygulayabilirsiniz.

#### Q2. Bir grafik serisinin adını nasıl değiştirebilirim?
 Aspose.Words for .NET kullanarak bir grafikteki grafik serisinin adını değiştirmek için şu adrese erişmeniz gerekir:`Name` mülkiyeti`ChartSeries` nesneyi seçin ve istediğiniz adı ayarlayın. Seri adı genellikle grafik açıklamasında veya veri etiketlerinde görüntülenir ve seri için açıklayıcı bir etiket sağlar. Seri adını değiştirerek her serinin temsil ettiği verileri yansıtan anlamlı adlar sağlayabilirsiniz.

#### S3. Grafik serisi yumuşatma nedir?
Grafik serisi yumuşatma, grafikteki noktaları birleştiren düzgün bir çizgi oluşturmanıza olanak tanıyan görsel bir geliştirme tekniğidir. Veri noktaları arasında enterpolasyon yapmak ve görsel olarak hoş bir eğri oluşturmak için Catmull-Rom spline'ları gibi bir yumuşatma algoritması uygular. Aspose.Words for .NET kullanarak bir grafikte seri yumuşatmayı etkinleştirmek için şuraya erişin:`Smooth` mülkiyeti`ChartSeries` nesneyi seçin ve buna ayarlayın`true`. Düzgünleştirme, düzensiz dalgalanmalara sahip verilerdeki eğilimleri veya kalıpları görüntülemek için yararlı olabilir.

#### S4. Bir grafik serisindeki veri noktalarına ilişkin işaretçileri nasıl özelleştirebilirim?
 Aspose.Words for .NET kullanarak bir grafik serisindeki veri noktalarına ilişkin işaretçileri özelleştirmek için şu adrese erişmeniz gerekir:`Marker` mülkiyeti`ChartSeries` nesne gibi özelliklerini değiştirin ve değiştirin`Symbol` Ve`Size`. İşaretçiler, ayrı ayrı veri noktalarını temsil etmek üzere grafiğe yerleştirilen görsel göstergelerdir. Çeşitli yerleşik işaretleyici semboller arasından seçim yapabilir ve seri içindeki belirli veri noktalarını vurgulamak veya ayırt etmek için boyutlarını ayarlayabilirsiniz.

#### S5. Bir grafik serisindeki negatif değerlerin renklerini tersine çevirebilir miyim?
 Evet, Aspose.Words for .NET'i kullanarak bir grafik serisindeki negatif değerlerin renklerini tersine çevirebilirsiniz. Ayarlayarak`InvertIfNegative` mülkiyeti`ChartSeries` itiraz etmek`true`Negatif değerli veri noktalarının renkleri ters çevrilerek pozitif değerlerden görsel olarak farklı hale getirilecektir. Bu özellik, bir grafik serisindeki pozitif ve negatif değerleri karşılaştırırken faydalı olabilir ve ikisi arasında net bir ayrım sağlar.