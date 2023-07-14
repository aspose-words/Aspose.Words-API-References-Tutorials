---
title: Bir Word Belgesinde Grafik Eksenini Gizle
linktitle: Bir Word Belgesinde Grafik Eksenini Gizle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir belgede grafik eksenini nasıl gizleyeceğinizi öğrenin. Daha temiz ve daha odaklı bir grafik görüntüsü için ekseni gizleyin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/hide-chart-axis/
---

Bu eğitim, bir belgede grafik eksenini gizlemek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve grafik ekseninin nasıl gizleneceğini gösterir.

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

 Ardından, kullanarak belgeye bir grafik ekleyin.`InsertChart` yöntemi`DocumentBuilder`Bu örnekte, bir sütun grafiği ekleyeceğiz.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Seri verilerini grafiğe ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte, beş öğe ve bunlara karşılık gelen değerleri ekleyeceğiz.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## 4. Adım: Grafik eksenini gizleyin

 Grafik eksenini gizlemek için şuraya erişin:`AxisY` grafiğin özelliğini ayarlayın ve`Hidden` mülkiyet`true`.

```csharp
chart.AxisY.Hidden = true;
```

Bu örnekte, grafiğin Y eksenini gizleriz.

## 5. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Bu, Aspose.Words for .NET kullanarak grafik eksenini gizleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Hide Chart Axis için örnek kaynak kodu 

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

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde grafik eksenini nasıl gizleyeceğinizi öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak, istediğiniz görsel efekti elde etmek için bir grafik oluşturabilir, seri verileri ekleyebilir ve grafik eksenini gizleyebilirsiniz.

 Aspose.Words for .NET, Word belgelerindeki grafiklerle Kelime İşleme için kapsamlı bir API sağlar ve eksen özellikleri de dahil olmak üzere grafiğin çeşitli yönlerini değiştirmenize olanak tanır. erişerek`AxisY`grafiğin özelliği, grafik görselleştirmesinden kaldırmak için Y eksenini gizleyebilirsiniz.

Grafik eksenini gizlemek, eksen çizgileri ve etiketlerin dikkatini dağıtmadan grafik verilerine odaklanmak istediğinizde yararlı olabilir. Grafiğe daha temiz ve daha minimalist bir görünüm sağlar.

Aspose.Words for .NET'i kullanarak, grafik oluşturma yeteneklerini .NET uygulamalarınıza kolayca dahil edebilir ve özelleştirilmiş grafikler ve gizli grafik eksenleri ile profesyonel görünümlü belgeler oluşturabilirsiniz.

### SSS

#### S1. Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin .NET uygulamalarında programlı olarak Word belgeleri oluşturmasına, değiştirmesine ve kaydetmesine olanak sağlayan güçlü bir belge işleme kitaplığıdır. Grafikler ve grafik eksenleri dahil olmak üzere belge öğeleriyle Kelime İşleme için çok çeşitli özellikler sağlar.

#### S2. Aspose.Words for .NET'i nasıl kurabilirim?
Aspose.Words for .NET'i Visual Studio'daki NuGet paket yöneticisini kullanarak indirerek kurabilirsiniz. NuGet paket yöneticisinde "Aspose.Words" ifadesini arayın ve onu projenize kurun.

#### S3. Bir grafiğin hem X eksenini hem de Y eksenini gizleyebilir miyim?
 Evet, Aspose.Words for .NET kullanarak bir grafiğin hem X eksenini hem de Y eksenini gizleyebilirsiniz. X eksenini gizlemek için şuraya erişebilirsiniz:`AxisX` grafiğin özelliğini ayarlayın ve`Hidden` mülkiyet`true` Benzer şekilde, Y eksenini gizlemek için`AxisY` özelliğini ayarlayın ve`Hidden` mülkiyet`true`. Bu, grafik görselleştirmesinden her iki ekseni de kaldırmanıza olanak tanır.

#### S4. Ekseni gizledikten sonra tekrar gösterebilir miyim?
 Evet, grafik eksenini Aspose.Words for .NET kullanarak gizledikten sonra tekrar gösterebilirsiniz. Gizli bir ekseni göstermek için,`Hidden` karşılık gelen özellik`AxisX` veya`AxisY` itiraz etmek`false`. Bu, ekseni grafikte tekrar görünür hale getirecektir.

#### S5. Grafik ekseninin diğer özelliklerini özelleştirebilir miyim?
 Evet, Aspose.Words for .NET grafik ekseninin eksen başlığı, etiketler, çizgi rengi ve daha fazlası gibi çeşitli özelliklerini özelleştirmenize olanak tanır. erişerek`AxisX` Ve`AxisY` grafiğin özellikleri gibi özellikleri değiştirebilirsiniz.`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, Ve bircok digerleri. Bu size grafik ekseninin görünümü ve davranışı üzerinde ayrıntılı kontrol sağlar.

#### S6. Gizli eksenli grafiği farklı dosya formatlarında kaydedebilir miyim?
Evet, Aspose.Words for .NET, grafiği içeren belgeyi gizli bir eksenle DOCX, PDF, HTML ve daha fazlası gibi çeşitli dosya biçimlerinde kaydetmenize olanak tanır. Gereksinimlerinize göre istediğiniz çıktı formatını seçebilir ve`Save` yöntemi`Document` belgeyi kaydetmek için nesne. Gizli eksen kaydedilen belgede korunacaktır.