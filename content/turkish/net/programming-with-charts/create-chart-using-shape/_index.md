---
title: Şekli Kullanarak Grafik Oluşturun ve Özelleştirin
linktitle: Şekli Kullanarak Grafik Oluşturun ve Özelleştirin
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak Word belgesindeki bir şekli kullanarak nasıl grafik oluşturacağınızı ve özelleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/create-chart-using-shape/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesindeki bir şekli kullanarak grafiğin nasıl oluşturulacağı açıklanmaktadır.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmaya itiraz edin.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Grafik Şekli Ekleme ve Yapılandırma
 kullanarak belgeye bir grafik şekli ekleyin.`InsertChart` yöntemi`DocumentBuilder` nesne. İstediğiniz grafik türünü ve boyutlarını ayarlayın.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## 4. Adım: Grafiği Özelleştirin
Grafik başlığı ve açıklama gibi çeşitli özellikleri değiştirerek grafiği özelleştirin.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Adım 5: Belgeyi Kaydedin
 Belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithCharts.CreateChartUsingShape.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Aspose.Words for .NET Kullanarak Şekil Kullanarak Grafik Oluşturma için örnek kaynak kodu 

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
	// Başlık metni olarak boş veya boş bir değer belirtilirse, otomatik olarak oluşturulan başlığın gösterileceğini lütfen unutmayın.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak bir Word belgesindeki şekli kullanarak başarıyla bir grafik oluşturdunuz.

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki şekli kullanarak nasıl grafik oluşturulacağını öğrendiniz. Adım adım kılavuzu izleyerek bir grafik şekli ekleyip yapılandırabilir, görünümünü özelleştirebilir ve belgeyi kaydedebilirsiniz. Aspose.Words for .NET, Word belgeleri ve grafikleriyle Kelime İşleme için kapsamlı bir dizi özellik sunarak, doğrudan .NET uygulamalarınızda profesyonel görünümlü ve görsel olarak çekici grafikler oluşturmanıza olanak tanır.

### SSS

#### S1. Aspose.Words for .NET kullanarak bir Word belgesinde grafikler oluşturabilir miyim?
Evet, Aspose.Words for .NET ile bir Word belgesinde programlı olarak grafikler oluşturabilirsiniz. Aspose.Words, çeşitli grafik türlerini eklemek, görünümlerini özelleştirmek ve grafik verilerini değiştirmek için API'ler ve işlevler sağlar.

#### Q2. Aspose.Words for .NET hangi grafik türlerini destekliyor?
Aspose.Words for .NET, çizgi grafikler, çubuk grafikler, pasta grafikler, alan grafikleri, dağılım grafikleri ve daha fazlasını içeren çok çeşitli grafik türlerini destekler. Verilerinize ve görselleştirme gereksinimlerinize göre uygun grafik türünü seçebilirsiniz.

#### S3. Oluşturulan grafiğin görünümünü özelleştirebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak oluşturulan grafiğin görünümünü özelleştirebilirsiniz. Özel tasarım ve biçimlendirme ihtiyaçlarınızı karşılamak için grafik başlığı, gösterge konumu, veri etiketleri, eksen etiketleri, renkler ve diğer görsel öğeler gibi özellikleri değiştirebilirsiniz.
