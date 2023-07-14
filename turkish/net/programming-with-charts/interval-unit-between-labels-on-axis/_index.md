---
title: Grafiğin Eksenindeki Etiketler Arasındaki Aralık Birimi
linktitle: Grafiğin Eksenindeki Etiketler Arasındaki Aralık Birimi
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir grafiğin ekseni üzerindeki etiketler arasındaki aralık birimini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

Bu eğitim, bir grafiğin ekseni üzerindeki etiketler arasındaki aralık birimini ayarlamak için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve eksen etiketlerinin nasıl özelleştirileceğini gösterir.

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
	//Belge dizininizin yolu
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

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir grafiğin ekseni üzerindeki etiketler arasındaki aralık birimini nasıl ayarlayacağınızı öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak yeni bir belge oluşturabilir, sütun grafiği ekleyebilir, seri verileri ekleyebilir ve etiketler arasındaki boşluğu kontrol etmek için eksen etiketlerini özelleştirebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki çizelgeleri işlemek için güçlü özellikler sağlar. Eksen üzerindeki etiketler arasındaki aralık birimini ayarlayarak etiketlerin görüntü yoğunluğunu kontrol edebilir ve grafiklerinizin okunabilirliğini artırabilirsiniz. Bu, verilerin sunumunu optimize etmenize ve genel kullanıcı deneyimini iyileştirmenize olanak tanır.

Aspose.Words for .NET ile, eksen etiketleri dahil olmak üzere grafiğin çeşitli yönlerini özelleştirme esnekliğine sahipsiniz. Etiketlerin uygun şekilde aralıklı olmasını sağlamak ve veri noktalarının net bir şekilde gösterilmesini sağlamak için istenen aralık birimini ayarlayabilirsiniz.

### SSS

#### S1. Grafikteki eksen etiketleri nelerdir?
Bir grafikteki eksen etiketleri, grafiğin yatay (X ekseni) veya dikey (Y ekseni) ekseni boyunca değerlerin metinsel gösterimini ifade eder. Bu etiketler, grafikte çizilen veri noktalarının tanımlanmasına ve yorumlanmasına yardımcı olur. Eksen etiketleri bağlam sağlar ve kullanıcıların grafikteki değerlerin ölçeğini ve aralığını anlamalarına olanak tanır.

#### S2. Eksen etiketleri arasındaki boşluğu nasıl özelleştirebilirim?
 Aspose.Words for .NET kullanarak bir grafikte eksen etiketleri arasındaki aralığı özelleştirmek için`AxisX` veya`AxisY` grafiğin özelliğini değiştirin ve`TickLabelSpacing` mülk. ayarlayarak`TickLabelSpacing` belirli bir değere, ilgili eksendeki etiketler arasındaki aralık birimini kontrol edebilir, aralığı gereksinimlerinize göre ayarlayabilirsiniz.

#### S3. X ekseni ve Y ekseni etiketleri için farklı boşluklar ayarlayabilir miyim?
Evet, Aspose.Words for .NET'i kullanarak X ekseni ve Y ekseni etiketleri için farklı boşluklar ayarlayabilirsiniz. İlgili eksene erişin (`AxisX` X ekseni için veya`AxisY` grafiğin Y ekseni için) ve değiştirin`TickLabelSpacing`her eksen için ayrı ayrı özellik. Bu, X ekseni ve Y ekseni üzerindeki etiketler için farklı aralık birimlerine ve boşluklara sahip olmanızı sağlayarak grafiğin görünümü üzerinde ayrıntılı kontrol sağlar.

#### S4. Eksen üzerindeki etiketler arasındaki aralık biriminin önemi nedir?
Eksen üzerindeki etiketler arasındaki aralık birimi, grafikte gösterilen ardışık etiketler arasındaki boşluğu belirler. Aralık birimini ayarlayarak etiketlerin yoğunluğunu kontrol edebilir ve aşırı kalabalıklaşmayı ve üst üste binmeyi önlemek için etiketlerin uygun şekilde yerleştirildiğinden emin olabilirsiniz. Aralık birimini ayarlamak, verileri daha okunabilir ve görsel olarak çekici bir şekilde sunmanıza olanak tanır.

#### S5. Eksen etiketlerinin diğer özelliklerini değiştirebilir miyim?
Evet, Aspose.Words for .NET, eksen etiketlerinin görünümünü ve davranışını özelleştirmek için çok çeşitli özellikler sunar. Eksen etiketleri için istenen biçimlendirmeyi ve stili elde etmek için yazı tipi, boyut, renk, yön, hizalama ve daha fazlası gibi özellikleri değiştirebilirsiniz. Kitaplık, grafik öğeleri üzerinde kapsamlı kontrol sunarak, özel gereksinimlerinize uygun profesyonel görünümlü grafikler oluşturmanıza olanak tanır.