---
title: Grafikte Çok Satırlı Etiket Hizalamasını İşaretleyin
linktitle: Grafikte Çok Satırlı Etiket Hizalamasını İşaretleyin
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak çok satırlı işaret etiketlerini grafik ekseninde nasıl hizalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/tick-multi-line-label-alignment/
---

Bu eğitimde Aspose.Words for .NET'in grafik eksenindeki çok satırlı etiketlerin hizalamasını ayarlamak için nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, eksene nasıl erişileceğini ve onay etiketi hizalamasını nasıl değiştireceğinizi gösterir.

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

 Daha sonra şunu kullanın:`InsertChart` yöntemi`DocumentBuilder` Belgeye bir dağılım grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## 3. Adım: Onay etiketi hizalamasını ayarlayın

 Çok satırlı onay etiketlerinin hizalamasını ayarlamak için`AxisX` Grafiğin özelliğini seçin ve`TickLabelAlignment` özelliği istenen hizalamaya getirin. Bu örnekte hizalamayı şu şekilde ayarladık:`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## 4. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Bu, Aspose.Words for .NET kullanılarak çok satırlı etiket hizalamasının ayarlanması uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Tick Çok Satırlı Etiket Hizalaması için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Bu özellik yalnızca çok satırlı etiketler için etkilidir.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## Çözüm

Bu eğitimde Aspose.Words for .NET'i kullanarak bir grafik ekseninde çok satırlı işaret etiketlerinin hizalamasını nasıl ayarlayacağınızı öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodunu kullanarak yeni bir belge oluşturabilir, dağılım grafiği ekleyebilir, grafik eksenine erişebilir ve onay etiketi hizalamasını değiştirebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafikleri yönetmek için güçlü özellikler sağlar. Çok satırlı etiketleri işaretleyin, eksen etiketleri birden çok satıra sarmayı veya bölmeyi gerektiren uzun metinler içerdiğinde kullanışlıdır. Onay etiketi hizalamasını ayarlayarak, çok satırlı etiketlerin grafik ekseni içindeki yatay hizalamasını kontrol ederek en iyi sunumu ve okunabilirliği sağlayabilirsiniz.

Çok satırlı etiket hizalamasını özelleştirmek, özellikle uzun veya karmaşık etiketlerle uğraşırken grafiğinizin görünümüne ince ayar yapmanıza olanak tanır. Etiketleri sağa, sola, ortaya veya iki yana hizalayarak eksen boyunca dengeli ve görsel olarak çekici bir onay etiketi düzenlemesi elde edebilirsiniz.

Aspose.Words for .NET ile, bir grafik ekseninin onay etiketi hizalama özelliğine kolayca erişebilir ve değiştirebilirsiniz, bu da size Word belge grafiklerinizdeki onay etiketlerinin görünümü ve düzeni üzerinde tam kontrol sağlar.

### SSS

#### S1. Grafik eksenindeki çok satırlı işaret etiketleri nelerdir?
Grafik eksenindeki çok satırlı etiketleri işaretleyin, etiket metni uzun olduğunda veya kullanılabilir alana sığması için sarmalamayı gerektirdiğinde birden çok satıra yayılan eksen etiketlerini ifade eder. Grafik ekseni, etiket metnini kısaltmak veya görsel dağınıklığa neden olmak yerine, okunabilirliği sağlamak için etiketleri otomatik olarak birden fazla satıra böler. Çok satırlı etiketleri işaretleyin, özellikle grafiklerdeki uzun kategori veya değer etiketleriyle uğraşırken kullanışlıdır.

#### Q2. Grafik eksenindeki onay etiketlerinin hizalamasını özelleştirebilir miyim?
 Evet, Aspose.Words for .NET'i kullanarak grafik eksenindeki onay etiketlerinin hizalamasını özelleştirebilirsiniz. Erişerek`TickLabelAlignment` mülkiyeti`ChartAxis` nesneyi seçtiğinizde, onay etiketleri için istediğiniz hizalamayı ayarlayabilirsiniz. Hizalama seçenekleri sola, sağa, ortaya veya iki yana hizalanmış hizalamayı içerir. Hizalamayı ayarlamak, onay etiketlerinin grafik ekseni boyunca yatay konumunu kontrol etmenize olanak tanıyarak uygun okunabilirlik ve görsel sunum sağlar.

#### S3. Grafik eksenindeki onay etiketi hizalamasını ne zaman değiştirmeyi düşünmeliyim?
Optimum sunum ve okunabilirlik gerektiren uzun veya çok satırlı etiketleriniz olduğunda, grafik eksenindeki onay etiketi hizalamasını değiştirmek faydalıdır. Hizalamayı ayarlayarak etiketlerin üst üste binmesini veya kesilmesini önleyerek doğru şekilde hizalanmasını ve aralıklı olmasını sağlayabilirsiniz. Uzun kategori adlarına, ayrıntılı değer etiketlerine sahip grafiklerle veya varsayılan hizalamanın istenen görsel görünümü sağlamadığı diğer senaryolarla uğraşırken onay etiketi hizalamasını değiştirmeyi düşünün.

#### S4. Onay etiketi hizalaması grafik eksenindeki tek satırlı etiketleri etkiler mi?
Hayır, onay etiketi hizalama özelliği grafik eksenindeki tek satırlı etiketleri etkilemez. Sarma veya bölme gerektiren çok satırlı etiketler için özel olarak tasarlanmıştır. Tek satırlı etiketler, grafik ekseninin varsayılan hizalama ayarlarına göre hizalanır. Onay etiketi hizalama özelliği yalnızca birden fazla satıra yayılan etiketler için geçerli olup, çok satırlı etiket içindeki her satırın hizalamasını kontrol etmenize olanak tanır.

#### S5. Bir grafikteki onay etiketlerini X ekseni ve Y ekseni için farklı şekilde hizalayabilir miyim?
 Evet, Aspose.Words for .NET'i kullanarak bir grafikteki onay etiketlerini X ekseni ve Y ekseni için farklı şekilde hizalayabilirsiniz. Onay etiketi hizalama özelliği her grafik eksenine özeldir. İlgili bilgilere erişerek`ChartAxis` X ekseni veya Y ekseni için nesneyi seçtiğinizde, onay etiketi hizalamasını bağımsız olarak farklı değerlere ayarlayabilirsiniz. Bu size grafikteki her eksen için özel gereksinimlerinize göre onay etiketlerini farklı şekilde hizalama esnekliği sağlar.