---
title: Grafiğin Eksenindeki Etiketler Arasındaki Aralık Birimi
linktitle: Grafiğin Eksenindeki Etiketler Arasındaki Aralık Birimi
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir grafiğin eksenindeki etiketler arasındaki aralık birimini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

Bu eğitimde, bir grafiğin eksenindeki etiketler arasındaki aralık birimini ayarlamak için Aspose.Words for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve eksen etiketlerinin nasıl özelleştirileceğini gösterir.

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

 Daha sonra şunu kullanın:`InsertChart` yöntemi`DocumentBuilder` Belgeye bir sütun grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Grafiğe seri verilerini ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte, karşılık gelen değerleriyle birlikte beş öğe ekleyeceğiz.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 4. Adım: Eksen etiketlerini özelleştirin

 X eksenindeki etiketler arasındaki aralık birimini ayarlamak için`AxisX` Grafiğin özelliğini seçin ve`TickLabelSpacing` özelliği istenilen değere getirir. Bu örnekte aralığı 2 olarak ayarladık.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## 5. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Bu, Aspose.Words for .NET kullanılarak eksen üzerindeki etiketler arasındaki aralık biriminin ayarlanması uygulamasını tamamlar.

### Aspose.Words for .NET kullanılarak Eksen Üzerindeki Etiketler Arasındaki Aralık Birimi için örnek kaynak kodu 

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
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir grafiğin eksenindeki etiketler arasındaki aralık birimini nasıl ayarlayacağınızı öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodunu kullanarak yeni bir belge oluşturabilir, sütun grafiği ekleyebilir, seri verileri ekleyebilir ve etiketler arasındaki boşluğu kontrol etmek için eksen etiketlerini özelleştirebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafikleri yönetmek için güçlü özellikler sağlar. Eksen üzerindeki etiketler arasındaki aralık birimini ayarlayarak etiketlerin görüntülenme yoğunluğunu kontrol edebilir ve grafiklerinizin okunabilirliğini artırabilirsiniz. Bu, verilerin sunumunu optimize etmenize ve genel kullanıcı deneyimini geliştirmenize olanak tanır.

Aspose.Words for .NET ile eksen etiketleri de dahil olmak üzere grafiğin çeşitli yönlerini özelleştirme esnekliğine sahip olursunuz. Etiketlerin uygun aralıklarla yerleştirildiğinden ve veri noktalarının net bir şekilde temsil edildiğinden emin olmak için istediğiniz aralık birimini ayarlayabilirsiniz.

### SSS

#### S1. Grafikteki eksen etiketleri nelerdir?
Bir grafikteki eksen etiketleri, grafiğin yatay (X ekseni) veya dikey (Y ekseni) ekseni boyunca değerlerin metinsel temsilini ifade eder. Bu etiketler, grafikte çizilen veri noktalarının tanımlanmasına ve yorumlanmasına yardımcı olur. Eksen etiketleri bağlam sağlar ve kullanıcıların grafikteki değerlerin ölçeğini ve aralığını anlamalarına olanak tanır.

#### Q2. Eksen etiketleri arasındaki boşluğu nasıl özelleştirebilirim?
 Aspose.Words for .NET kullanarak bir grafikte eksen etiketleri arasındaki boşluğu özelleştirmek için şuraya erişebilirsiniz:`AxisX` veya`AxisY` Grafiğin özelliğini değiştirin ve`TickLabelSpacing` mülk. Ayarlayarak`TickLabelSpacing` Belirli bir değere göre ilgili eksendeki etiketler arasındaki aralık birimini kontrol edebilir, aralığı gereksinimlerinize göre ayarlayabilirsiniz.

#### S3. X ekseni ve Y ekseni etiketleri için farklı aralıklar ayarlayabilir miyim?
Evet, Aspose.Words for .NET'i kullanarak X ekseni ve Y ekseni etiketleri için farklı aralıklar ayarlayabilirsiniz. İlgili eksene erişin (`AxisX` X ekseni için veya`AxisY` Grafiğin Y ekseni için) ve`TickLabelSpacing`Her eksen için ayrı ayrı özellik. Bu, X ekseni ve Y eksenindeki etiketler için farklı aralık birimlerine ve aralıklara sahip olmanıza olanak tanıyarak grafiğin görünümü üzerinde ayrıntılı kontrol sağlar.

#### S4. Eksen üzerindeki etiketler arasındaki aralık biriminin önemi nedir?
Eksen üzerindeki etiketler arasındaki aralık birimi, grafikte görüntülenen ardışık etiketler arasındaki aralığı belirler. Aralık birimini ayarlayarak etiketlerin yoğunluğunu kontrol edebilir ve aşırı kalabalıklaşmayı ve üst üste gelmeyi önleyecek şekilde uygun aralıklarla yerleştirildiğinden emin olabilirsiniz. Aralık birimini ayarlamak, verileri daha okunaklı ve görsel olarak çekici bir şekilde sunmanıza olanak tanır.

#### S5. Eksen etiketlerinin diğer özelliklerini değiştirebilir miyim?
Evet, Aspose.Words for .NET eksen etiketlerinin görünümünü ve davranışını özelleştirmek için geniş bir özellik yelpazesi sunar. Eksen etiketleri için istediğiniz formatı ve stili elde etmek amacıyla yazı tipi, boyut, renk, yön, hizalama ve daha fazlası gibi özellikleri değiştirebilirsiniz. Kitaplık, grafik öğeleri üzerinde kapsamlı kontrol sunarak, özel gereksinimlerinize göre uyarlanmış profesyonel görünümlü grafikler oluşturmanıza olanak tanır.