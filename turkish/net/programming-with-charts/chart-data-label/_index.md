---
title: Grafik Veri Etiketi
linktitle: Grafik Veri Etiketi
second_title: Aspose.Words for .NET API Referansı
description: Veri noktaları hakkında ek bilgi sağlamak için Aspose.Words for .NET'i kullanarak bir tabloya veri etiketlerini nasıl ekleyeceğinizi ve özelleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/chart-data-label/
---

Bu eğitim, Aspose.Words for .NET kullanılarak bir tabloya veri etiketlerinin nasıl ekleneceğini ve özelleştirileceğini açıklar. Veri etiketleri, bir grafikteki veri noktaları hakkında ek bilgi sağlar.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle çalışma.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluştur`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmak için nesne.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Bir Grafik Ekleyin ve Yapılandırın
 kullanarak belgeye bir grafik ekleyin.`InsertChart` yöntemi`DocumentBuilder` nesne. İstenen grafik türünü ve boyutlarını ayarlayın.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## 4. Adım: Veri Etiketlerini Özelleştirin
Grafik serisinin veri etiketleri koleksiyonuna erişin ve veri etiketlerinin görünümünü özelleştirmek için çeşitli özellikleri değiştirin.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## 5. Adım: Belgeyi Kaydedin
 kullanarak belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithCharts.ChartDataLabel.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Aspose.Words for .NET kullanan Grafik Veri Etiketi için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	//Varsayılan olarak, bir pasta grafiğindeki veri noktalarına veri etiketleri eklediğinizde, veri etiketleri için öncü çizgiler görüntülenir.
	// veri noktalarının sonunun çok dışına konumlandırılmış. Öncü çizgiler, bir veri etiketi ile etiketi arasında görsel bir bağlantı oluşturur.
	// karşılık gelen veri noktası.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak bir tabloya veri etiketlerini başarıyla eklediniz ve özelleştirdiniz.