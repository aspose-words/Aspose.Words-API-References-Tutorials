---
title: Veri Etiketleri İçin Varsayılan Seçenekler
linktitle: Veri Etiketleri İçin Varsayılan Seçenekler
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir grafikteki veri etiketleri için varsayılan seçenekleri nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/default-options-for-data-labels/
---

Bu eğitim, bir grafikteki veri etiketleri için varsayılan seçenekleri ayarlamak üzere Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kod, Aspose.Words kullanarak bir grafiğin nasıl oluşturulacağını, veri serilerinin nasıl ekleneceğini ve veri etiketlerinin nasıl özelleştirileceğini gösterir.

## 1. Adım: Projeyi kurun

Başlamadan önce, aşağıdaki gereksinimlere sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı yüklendi. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet paket yöneticisini kullanabilirsiniz.
- Çıktı belgesinin kaydedileceği bir belge dizini yolu.

## 2. Adım: Yeni bir belge oluşturun ve bir grafik ekleyin

 İlk önce yeni bir tane oluşturalım`Document` nesne ve bir`DocumentBuilder` belgeyi oluşturmak için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ardından, kullanarak belgeye bir grafik ekliyoruz.`InsertChart` yöntemi`DocumentBuilder`. Bu örnekte, bir pasta grafik ekleyeceğiz.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Grafiğe veri serisi ekleyin

Şimdi grafiğe bir veri serisi ekleyelim. Bu örnekte, üç kategori ve bunlara karşılık gelen değerleri ekleyeceğiz.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## 4. Adım: Veri etiketlerini özelleştirin

 Grafikteki veri etiketlerini özelleştirmek için şuna erişmemiz gerekir:`ChartDataLabelCollection` dizi ile ilişkili nesne.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Daha sonra çeşitli özellikleri değiştirebiliriz.`labels` veri etiketleri için istenen seçenekleri ayarlamak için nesne. Bu örnekte yüzde ve değer göstermeyi etkinleştireceğiz, lider çizgileri devre dışı bırakacağız ve özel bir ayırıcı ayarlayacağız.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## 5. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydediyoruz.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Bu, Aspose.Words for .NET kullanan bir tablodaki veri etiketleri için varsayılan seçenekleri ayarlama uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Veri Etiketleri İçin Varsayılan Seçenekler için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```