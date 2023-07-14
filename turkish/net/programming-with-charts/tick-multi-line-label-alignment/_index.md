---
title: Bir Grafikte Çok Satırlı Etiket Hizalamasını İşaretle
linktitle: Bir Grafikte Çok Satırlı Etiket Hizalamasını İşaretle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET'i kullanarak çok satırlı etiketleri bir grafik ekseninde nasıl hizalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/tick-multi-line-label-alignment/
---

Bu öğretici, Aspose.Words for .NET'in grafik eksenindeki çok satırlı etiketlerin hizalamasını ayarlamak için nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, eksene nasıl erişileceğini ve onay etiketi hizalamasının nasıl değiştirileceğini gösterir.

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

 Ardından,`InsertChart` yöntemi`DocumentBuilder` belgeye bir dağılım grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## 3. Adım: Onay etiketi hizalamasını ayarlayın

 Çok satırlı etiketlerin hizalamasını ayarlamak için şuraya erişin:`AxisX` grafiğin özelliğini ayarlayın ve`TickLabelAlignment` özelliğini istediğiniz hizaya getirin. Bu örnekte, hizalamayı şu şekilde ayarladık:`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## 4. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Bu, Aspose.Words for .NET kullanarak çok satırlı etiket hizalamasını ayarlama uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Çok Satırlı Etiket Hizalama İşareti için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Bu özelliğin yalnızca çok satırlı etiketler için etkisi vardır.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir grafik ekseninde çok satırlı işaretli etiketlerin hizalamasını nasıl ayarlayacağınızı öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak yeni bir belge oluşturabilir, dağılım grafiği ekleyebilir, grafik eksenine erişebilir ve onay etiketi hizalamasını değiştirebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki çizelgeleri işlemek için güçlü özellikler sağlar. Çok satırlı etiketleri işaretleyin, eksen etiketleri birden çok satıra sarma veya bölme gerektiren uzun metinler içerdiğinde kullanışlıdır. Tik etiketi hizalamasını ayarlayarak, grafik ekseni içindeki çok satırlı etiketlerin yatay hizalamasını kontrol ederek optimum sunum ve okunabilirlik sağlayabilirsiniz.

Çok satırlı etiket hizalamasını özelleştirmek, özellikle uzun veya karmaşık etiketlerle uğraşırken grafiğinizin görünümüne ince ayar yapmanızı sağlar. Etiketleri sağa, sola, ortaya veya iki yana hizalayarak, eksen boyunca dengeli ve görsel olarak çekici bir onay etiketi düzenlemesi elde edebilirsiniz.

Aspose.Words for .NET ile, bir grafik ekseninin işaret etiketi hizalama özelliğine kolayca erişebilir ve bu özelliği değiştirerek Word belge çizelgelerinizdeki işaret etiketlerinin görünümü ve yerleşimi üzerinde tam kontrol sahibi olabilirsiniz.

### SSS

#### S1. Grafik eksenindeki çok satırlı işaretli etiketler nelerdir?
Bir grafik eksenindeki çok satırlı etiketleri işaretleyin, etiket metni uzun olduğunda veya kullanılabilir alana sığması için sarma gerektirdiğinde birden çok satıra yayılan eksen etiketlerine başvurur. Grafik ekseni, etiket metnini kısaltmak veya görsel karışıklığa neden olmak yerine okunabilirliği sağlamak için etiketleri otomatik olarak birden çok satıra böler. Çok satırlı etiketleri işaretleyin, grafiklerdeki uzun kategori veya değer etiketleriyle uğraşırken özellikle yararlıdır.

#### S2. Bir grafik ekseninde onay etiketlerinin hizalamasını özelleştirebilir miyim?
 Evet, Aspose.Words for .NET'i kullanarak bir grafik ekseninde onay etiketlerinin hizalamasını özelleştirebilirsiniz. erişerek`TickLabelAlignment`mülkiyeti`ChartAxis` nesne, onay etiketleri için istediğiniz hizalamayı ayarlayabilirsiniz. Hizalama seçenekleri arasında sola, sağa, ortaya veya hizalanmış hizalama bulunur. Hizalamayı ayarlamak, doğru okunabilirlik ve görsel sunum sağlayarak grafik ekseni boyunca onay etiketlerinin yatay konumunu kontrol etmenize olanak tanır.

#### S3. Bir grafik ekseninde onay işareti hizalamasını ne zaman değiştirmeyi düşünmeliyim?
En uygun sunum ve okunabilirlik gerektiren uzun veya çok satırlı etiketleriniz olduğunda, bir grafik eksenindeki onay etiketi hizalamasını değiştirmek faydalıdır. Hizalamayı ayarlayarak, etiketlerin düzgün şekilde hizalanmasını ve aralıklı olmasını sağlayarak üst üste binmeyi veya kesilmeyi önleyebilirsiniz. Uzun kategori adlarına, ayrıntılı değer etiketlerine sahip grafiklerle veya varsayılan hizalamanın istenen görsel görünümü sağlamadığı diğer senaryolarla uğraşırken onay etiketi hizalamasını değiştirmeyi düşünün.

#### S4. Onay etiketi hizalaması, bir grafik eksenindeki tek satırlık etiketleri etkiler mi?
Hayır, etiket hizalama özelliği, bir grafik eksenindeki tek satırlı etiketleri etkilemez. Sarma veya bölme gerektiren çok satırlı etiketler için özel olarak tasarlanmıştır. Tek satırlı etiketler, grafik ekseninin varsayılan hizalama ayarlarına göre hizalanır. Tik etiketi hizalama özelliği yalnızca birden çok satıra yayılan etiketler için geçerlidir ve çok satırlı etiket içindeki her satırın hizalamasını kontrol etmenize olanak tanır.

#### S5. Bir grafikte X ekseni ve Y ekseni için onay etiketlerini farklı şekilde hizalayabilir miyim?
 Evet, Aspose.Words for .NET kullanarak bir grafikte X ekseni ve Y ekseni için işaret etiketlerini farklı şekilde hizalayabilirsiniz. Onay etiketi hizalama özelliği, her grafik eksenine özeldir. İlgili içeriğe erişerek`ChartAxis` X ekseni veya Y ekseni için nesne, onay etiketi hizalamasını bağımsız olarak farklı değerlere ayarlayabilirsiniz. Bu size, grafikteki her eksen için özel gereksinimlerinize göre onay etiketlerini farklı şekilde hizalama esnekliği sağlar.