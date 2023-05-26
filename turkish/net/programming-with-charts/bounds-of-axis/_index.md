---
title: eksen sınırları
linktitle: eksen sınırları
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'i kullanarak eksende görüntülenen değer aralığını kontrol ederek bir grafikte bir eksenin sınırlarını nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/bounds-of-axis/
---

Bu eğitim, Aspose.Words for .NET kullanılarak bir grafikte bir eksenin sınırlarının nasıl ayarlanacağını açıklar. Bir grafik ekleyerek, seri verileri ekleyerek ve eksen ölçeklendirmeyi yapılandırarak, eksen için minimum ve maksimum değerleri tanımlayabilirsiniz.

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
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 4. Adım: Seri Verilerini Ekleyin
Grafikteki mevcut serileri temizleyin ve yeni seri verileri ekleyin. Bu örnekte, "Öğe 1" ile "Öğe 5" arasındaki etiketleri ve karşılık gelen değerleri içeren bir dizi ekliyoruz.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Adım 5: Eksenin Sınırlarını Ayarlayın
 kullanarak minimum ve maksimum değerleri ayarlayarak Y ekseninin ölçeklendirmesini yapılandırın.`Scaling.Minimum` Ve`Scaling.Maximum` eksenin özellikleri.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## 6. Adım: Belgeyi Kaydedin
 kullanarak belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithCharts.BoundsOfAxis.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Aspose.Words for .NET kullanan Bounds Of Axis için örnek kaynak kodu 

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
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak bir grafikte bir eksenin sınırlarını başarıyla belirlediniz.