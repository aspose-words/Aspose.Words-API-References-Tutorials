---
title: Şekil Kullanarak Grafik Oluştur
linktitle: Şekil Kullanarak Grafik Oluştur
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki bir şekli kullanarak grafik oluşturmayı ve özelleştirmeyi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/create-chart-using-shape/
---

Bu öğretici, Aspose.Words for .NET kullanarak bir Word belgesindeki bir şekli kullanarak bir grafiğin nasıl oluşturulacağını açıklar.

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

## 3. Adım: Bir Grafik Şekli Ekleyin ve Yapılandırın
 kullanarak belgeye bir grafik şekli ekleyin.`InsertChart` yöntemi`DocumentBuilder` nesne. İstenen grafik türünü ve boyutlarını ayarlayın.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 4. Adım: Grafiği Özelleştirin
Grafik başlığı ve açıklaması gibi çeşitli özellikleri değiştirerek grafiği özelleştirin.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## 5. Adım: Belgeyi Kaydedin
 kullanarak belgeyi belirtilen dizine kaydedin.`Save`yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithCharts.CreateChartUsingShape.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Aspose.Words for .NET kullanarak Şekil Kullanarak Grafik Oluştur için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Başlık metni olarak null veya boş bir değer belirtilirse, otomatik oluşturulan başlığın gösterileceğini lütfen unutmayın.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak bir Word belgesindeki bir şekli kullanarak başarıyla bir grafik oluşturdunuz.