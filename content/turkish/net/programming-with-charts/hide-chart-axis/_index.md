---
title: Bir Word Belgesinde Grafik Eksenini Gizleme
linktitle: Bir Word Belgesinde Grafik Eksenini Gizleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir belgede grafik eksenini nasıl gizleyeceğinizi öğrenin. Daha net ve daha odaklanmış bir grafik görünümü için ekseni gizleyin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/hide-chart-axis/
---

Bu eğitimde Aspose.Words for .NET'in bir belgedeki grafik eksenini gizlemek için nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve grafik ekseninin nasıl gizleneceğini gösterir.

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

 Daha sonra belgeye bir grafik ekleyin.`InsertChart` yöntemi`DocumentBuilder`Bu örnekte bir sütun grafiği ekleyeceğiz.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Grafiğe seri verilerini ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte beş öğeyi ve bunlara karşılık gelen değerleri ekleyeceğiz.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 4. Adım: Grafik eksenini gizleyin

 Grafik eksenini gizlemek için`AxisY` Grafiğin özelliğini seçin ve`Hidden` mülkiyet`true`.

```csharp
chart.AxisY.Hidden = true;
```

Bu örnekte grafiğin Y eksenini gizledik.

## 5. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Bu, Aspose.Words for .NET kullanarak grafik eksenini gizleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Grafik Eksenini Gizlemek için örnek kaynak kodu 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde grafik eksenini nasıl gizleyeceğinizi öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak, istediğiniz görsel efekti elde etmek için bir grafik oluşturabilir, seri verileri ekleyebilir ve grafik eksenini gizleyebilirsiniz.

 Aspose.Words for .NET, Word belgelerindeki grafiklerle Kelime İşleme için kapsamlı bir API sağlar ve eksen özellikleri de dahil olmak üzere grafiğin çeşitli yönlerini değiştirmenize olanak tanır. Erişerek`AxisY`Grafiğin özelliği, grafik görselleştirmesinden kaldırmak için Y eksenini gizleyebilirsiniz.

Eksen çizgileri ve etiketlerin dikkati dağıtmadan grafik verilerine odaklanmak istediğinizde grafik eksenini gizlemek yararlı olabilir. Grafiğe daha temiz ve minimalist bir görünüm kazandırır.

Aspose.Words for .NET'i kullanarak grafik yeteneklerini .NET uygulamalarınıza kolayca dahil edebilir ve özelleştirilmiş grafikler ve gizli grafik eksenleriyle profesyonel görünümlü belgeler oluşturabilirsiniz.

### SSS

#### S1. Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin .NET uygulamalarında Word belgelerini programlı olarak oluşturmasına, yönetmesine ve kaydetmesine olanak tanıyan güçlü bir belge işleme kitaplığıdır. Grafikler ve grafik eksenleri de dahil olmak üzere belge öğeleriyle Kelime İşleme için geniş bir özellik yelpazesi sunar.

#### Q2. Aspose.Words for .NET'i nasıl kurabilirim?
Aspose.Words for .NET'i, Visual Studio'daki NuGet paket yöneticisini kullanarak indirerek kurabilirsiniz. NuGet paket yöneticisinde "Aspose.Words" ifadesini arayın ve projenize yükleyin.

#### S3. Bir grafiğin hem X eksenini hem de Y eksenini gizleyebilir miyim?
 Evet, Aspose.Words for .NET'i kullanarak bir grafiğin hem X eksenini hem de Y eksenini gizleyebilirsiniz. X eksenini gizlemek için şuraya erişebilirsiniz:`AxisX` Grafiğin özelliğini seçin ve`Hidden` mülkiyet`true` Benzer şekilde Y eksenini gizlemek için`AxisY` özelliği ayarlayın ve`Hidden` mülkiyet`true`. Bu, grafik görselleştirmesinden her iki ekseni de kaldırmanıza olanak tanır.

#### S4. Ekseni gizledikten sonra tekrar gösterebilir miyim?
 Evet, grafik eksenini Aspose.Words for .NET kullanarak gizledikten sonra tekrar gösterebilirsiniz. Gizli bir ekseni göstermek için basitçe`Hidden` karşılık gelen mülk`AxisX` veya`AxisY` itiraz etmek`false`. Bu, eksenin grafikte tekrar görünmesini sağlayacaktır.

#### S5. Grafik ekseninin diğer özelliklerini özelleştirebilir miyim?
 Evet, Aspose.Words for .NET grafik ekseninin eksen başlığı, etiketler, çizgi rengi ve daha fazlası gibi çeşitli özelliklerini özelleştirmenize olanak tanır. Erişerek`AxisX` Ve`AxisY` Grafiğin özellikleri gibi özellikleri değiştirebilirsiniz.`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, Ve bircok digerleri. Bu size grafik ekseninin görünümü ve davranışı üzerinde ayrıntılı kontrol sağlar.

#### S6. Grafiği gizli eksenle farklı dosya formatlarında kaydedebilir miyim?
Evet, Aspose.Words for .NET, gizli eksenli grafiği içeren belgeyi DOCX, PDF, HTML ve daha fazlası gibi çeşitli dosya formatlarında kaydetmenize olanak tanır. Gereksinimlerinize göre istediğiniz çıktı formatını seçebilir ve`Save` yöntemi`Document` Belgeyi kaydetmek için nesne. Gizli eksen kaydedilen belgede korunacaktır.