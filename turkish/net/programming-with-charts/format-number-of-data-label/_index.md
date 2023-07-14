---
title: Grafikteki Veri Etiketinin Format Sayısı
linktitle: Grafikteki Veri Etiketinin Format Sayısı
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir grafikteki veri etiketi sayısını nasıl biçimlendireceğinizi öğrenin. Veri etiketleri için sayı biçimlerini kolayca özelleştirin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/format-number-of-data-label/
---

Bu eğitim, bir grafikteki veri etiketi sayısını biçimlendirmek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve veri etiketlerinin sayı biçiminin nasıl özelleştirileceğini gösterir.

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

 Ardından, kullanarak belgeye bir grafik ekleyin.`InsertChart` yöntemi`DocumentBuilder`. Bu örnekte, bir çizgi grafiği ekleyeceğiz.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## 3. Adım: Seri verilerini grafiğe ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte, üç kategori ve bunlara karşılık gelen değerleri ekleyeceğiz.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## 4. Adım: Veri etiketlerinin sayı biçimini özelleştirin

 Veri etiketi sayısını biçimlendirmek için şuraya erişin:`DataLabels` diziyle ilişkili koleksiyon.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

Bu örnekte, her veri etiketi için farklı sayı biçimleri ayarladık. İlk veri etiketi para birimi olarak, ikincisi tarih olarak ve üçüncüsü yüzde olarak biçimlendirilir.

## 5. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Bu, Aspose.Words for .NET kullanılarak bir grafikteki veri etiketi sayısını biçimlendirme uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Format Number of Data Label için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Oluşturulan varsayılan seriyi silin.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Veya bir kaynak hücreye bağlanacak biçim kodunu ayarlayabilirsiniz,
	// bu durumda NumberFormat genele sıfırlanacak ve bir kaynak hücreden devralınacaktır.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir grafikteki veri etiketi sayısını nasıl biçimlendireceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak bir grafik oluşturabilir, seri verileri ekleyebilir ve veri etiketlerinin sayı biçimini ihtiyaçlarınıza göre özelleştirebilirsiniz.

 Aspose.Words for .NET, Word belgelerindeki grafiklerle Kelime İşleme için kapsamlı bir API sağlar ve veri etiketleri de dahil olmak üzere grafiğin çeşitli yönlerini değiştirmenize olanak tanır. erişerek`DataLabels` bir seriyle ilişkilendirilmiş koleksiyon, ayrı ayrı veri etiketlerinin sayı biçimini özelleştirebilirsiniz.

API, değerlerin görüntüsünü kontrol etmenize, her veri etiketi için farklı sayı biçimleri ayarlamanıza ve sayı biçimini bir kaynak hücreye bağlamanıza olanak tanır. Bu esneklik, grafiklerde sayısal verileri para birimi simgeleri, tarih biçimleri ve yüzde değerleri gibi istenen biçimlendirmeyle sunmanıza olanak tanır.

Aspose.Words for .NET'i kullanarak güçlü grafik oluşturma yeteneklerini .NET uygulamalarınıza dahil edebilir ve tamamen biçimlendirilmiş grafikler ve veri etiketleri ile profesyonel görünümlü belgeler oluşturabilirsiniz.

### SSS

#### S1. Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin .NET uygulamalarında Word belgelerini programlı olarak oluşturmasına, değiştirmesine ve kaydetmesine olanak sağlayan, zengin özelliklere sahip bir belge işleme kitaplığıdır. Grafikler ve veri etiketleri de dahil olmak üzere belge öğeleriyle Kelime İşleme için çok çeşitli özellikler sağlar.

#### S2. Aspose.Words for .NET'i nasıl kurabilirim?
Aspose.Words for .NET'i Visual Studio'daki NuGet paket yöneticisini kullanarak indirerek kurabilirsiniz. NuGet paket yöneticisinde "Aspose.Words" ifadesini arayın ve onu projenize kurun.

#### S3. Aspose.Words for .NET'i kullanarak grafiğin diğer yönlerini biçimlendirebilir miyim?
Evet, Aspose.Words for .NET, bir grafiğin çeşitli yönlerini biçimlendirmek için kapsamlı yetenekler sağlar. Veri etiketlerine ek olarak grafik tipini, seri verilerini, eksen özelliklerini, göstergeyi, başlığı, çizim alanını ve grafiğin diğer birçok öğesini özelleştirebilirsiniz. API, grafik görünümü ve biçimlendirme üzerinde ayrıntılı kontrol sunar.

#### S4. Aynı serideki farklı veri etiketlerine farklı sayı biçimleri uygulayabilir miyim?
 Evet, Aspose.Words for .NET, aynı serideki bireysel veri etiketlerine farklı sayı biçimleri uygulamanıza izin verir. erişerek`DataLabels` bir seriyle ilişkilendirilmiş koleksiyonu ayarlayabilirsiniz.`FormatCode` İstenen sayı biçimini belirtmek için her veri etiketinin özelliği. Bu, sayısal değerleri aynı grafik içinde farklı biçimlerde sunmanıza olanak tanır.

#### S5. Veri etiketleri için özel sayı biçimlerini kullanabilir miyim?
 Evet, Aspose.Words for .NET, veri etiketleri için özel sayı biçimlerini destekler. ayarlayarak istediğiniz sayı biçimini belirleyebilirsiniz.`FormatCode`bir veri etiketinin özelliğini özel biçim koduna dönüştürür. Bu size para birimi simgeleri, tarih biçimleri, yüzde değerleri ve daha fazlası gibi çok çeşitli sayı biçimlerini uygulama esnekliği sağlar.

#### S6. Grafiği biçimlendirilmiş veri etiketleri ile farklı biçimlerde kaydedebilir miyim?
 Evet, Aspose.Words for .NET, grafiği içeren belgeyi DOCX, PDF, HTML ve daha fazlası gibi çeşitli biçimlerde biçimlendirilmiş veri etiketleriyle kaydetmenize olanak tanır. Gereksinimlerinize göre uygun formatı seçebilir ve`Save` yöntemi`Document` belgeyi kaydetmek için nesne. Biçimlendirilmiş veri etiketleri kaydedilen belgede korunacaktır.