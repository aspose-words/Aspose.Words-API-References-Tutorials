---
title: Şekli Kullanarak Grafik Oluşturun ve Özelleştirin
linktitle: Şekli Kullanarak Grafik Oluşturun ve Özelleştirin
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki bir şekli kullanarak grafik oluşturmayı ve özelleştirmeyi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/create-chart-using-shape/
---

Bu öğretici, Aspose.Words for .NET kullanarak bir Word belgesindeki bir şekli kullanarak bir grafiğin nasıl oluşturulacağını açıklar.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

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
 kullanarak belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithCharts.CreateChartUsingShape.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Aspose.Words for .NET kullanarak Şekil Kullanarak Grafik Oluştur için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
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

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki bir şekli kullanarak bir grafiğin nasıl oluşturulacağını öğrendiniz. Adım adım kılavuzu izleyerek bir grafik şekli ekleyebilir ve yapılandırabilir, görünümünü özelleştirebilir ve belgeyi kaydedebilirsiniz. Aspose.Words for .NET, doğrudan .NET uygulamalarınızda profesyonel görünümlü ve görsel olarak çekici grafikler oluşturmanıza olanak tanıyan, Word belgeleri ve çizelgeleri ile Kelime İşleme için kapsamlı bir dizi özellik sunar.

### SSS

#### S1. Aspose.Words for .NET kullanarak bir Word belgesinde grafikler oluşturabilir miyim?
Evet, Aspose.Words for .NET ile bir Word belgesinde programlı olarak grafikler oluşturabilirsiniz. Aspose.Words, çeşitli grafik türleri eklemek, görünümlerini özelleştirmek ve grafik verilerini değiştirmek için API'ler ve işlevler sağlar.

#### S2. Aspose.Words for .NET hangi grafik tiplerini destekliyor?
Aspose.Words for .NET, çizgi grafikler, çubuk grafikler, pasta grafikler, alan grafikler, dağılım grafikler ve daha fazlasını içeren çok çeşitli grafik türlerini destekler. Verilerinize ve görselleştirme gereksinimlerinize göre uygun grafik türünü seçebilirsiniz.

#### S3. Oluşturulan grafiğin görünümünü özelleştirebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak oluşturulan grafiğin görünümünü özelleştirebilirsiniz. Özel tasarım ve biçimlendirme ihtiyaçlarınızı karşılamak için grafik başlığı, açıklama konumu, veri etiketleri, eksen etiketleri, renkler ve diğer görsel öğeler gibi özellikleri değiştirebilirsiniz.
