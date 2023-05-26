---
title: Veri Etiketinin Biçim Numarası
linktitle: Veri Etiketinin Biçim Numarası
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir grafikteki veri etiketi sayısını nasıl biçimlendireceğinizi öğrenin. Veri etiketleri için sayı biçimlerini kolayca özelleştirin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/format-number-of-data-label/
---

Bu eğitim, bir grafikteki veri etiketi sayısını biçimlendirmek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve veri etiketlerinin sayı biçiminin nasıl özelleştirileceğini gösterir.

## 1. Adım: Projeyi kurun

Aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı yüklendi. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet paket yöneticisini kullanabilirsiniz.
- Çıktı belgesinin kaydedileceği bir belge dizini yolu.

## 2. Adım: Yeni bir belge oluşturun ve bir grafik ekleyin

 Yeni bir tane oluştur`Document` nesne ve bir`DocumentBuilder` belgeyi oluşturmak için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ardından, kullanarak belgeye bir grafik ekleyin.`InsertChart` yöntemi`DocumentBuilder`Bu örnekte, bir çizgi grafiği ekleyeceğiz.

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
	// Belge dizininizin yolu
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