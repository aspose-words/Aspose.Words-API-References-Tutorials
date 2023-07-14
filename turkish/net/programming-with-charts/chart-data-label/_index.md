---
title: Grafik Veri Etiketini Özelleştir
linktitle: Grafik Veri Etiketini Özelleştir
second_title: Aspose.Words Belge İşleme API'sı
description: Veri noktaları hakkında ek bilgi sağlamak için Aspose.Words for .NET'i kullanarak bir tabloya veri etiketlerini nasıl ekleyeceğinizi ve özelleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/chart-data-label/
---

Bu eğitim, Aspose.Words for .NET kullanılarak bir tabloya veri etiketlerinin nasıl ekleneceğini ve özelleştirileceğini açıklar. Veri etiketleri, bir grafikteki veri noktaları hakkında ek bilgi sağlar.

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
 kullanarak belgeyi belirtilen dizine kaydedin.`Save`yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithCharts.ChartDataLabel.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Aspose.Words for .NET kullanan Grafik Veri Etiketi için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// Varsayılan olarak, bir pasta grafiğindeki veri noktalarına veri etiketleri eklediğinizde, veri etiketleri için öncü çizgiler görüntülenir.
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

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir grafikte veri etiketlerini nasıl ekleyeceğinizi ve özelleştireceğinizi öğrendiniz. Adım adım kılavuzu izleyerek bir grafik ekleyebilir, veri etiketleri koleksiyonuna erişebilir ve veri etiketlerinin görünümünü özelleştirmek için özellikleri değiştirebilirsiniz. Aspose.Words for .NET, Word belgeleri ve çizelgeleri ile Kelime İşleme için güçlü bir API sağlayarak, özelleştirilmiş veri etiketleri ile görsel olarak çekici ve bilgilendirici çizelgeler oluşturmanıza olanak tanır.

### SSS

#### S1. Grafikteki veri etiketleri nelerdir?
Bir grafikteki veri etiketleri, grafikte temsil edilen veri noktaları hakkında ek bilgi sağlar. Grafik tipine ve yapılandırmasına bağlı olarak değerleri, kategorileri, seri adlarını, yüzdeleri veya diğer ilgili ayrıntıları görüntüleyebilirler.

#### S2. Veri etiketlerinin görünümünü özelleştirebilir miyim?
Evet, bir grafikteki veri etiketlerinin görünümünü özelleştirebilirsiniz. Aspose.Words for .NET veri etiketlerinin gösterge anahtarlarını, öncü satırları, kategori adlarını, seri adlarını, değerleri ve daha fazlasını gösterme gibi çeşitli özelliklerini değiştirmek için seçenekler sunar. Ayırıcılar ayarlayabilir ve etiketleri özel gereksinimlerinizi karşılayacak şekilde biçimlendirebilirsiniz.

#### S3. Herhangi bir grafik türüne veri etiketleri ekleyebilir miyim?
Evet, çubuk grafikler, pasta grafikler, çizgi grafikler ve daha fazlası dahil olmak üzere çeşitli grafik türlerine veri etiketleri ekleyebilirsiniz. Veri etiketleri ekleme ve özelleştirme işlemi, grafik türüne ve kullandığınız kitaplığa veya araca bağlı olarak biraz değişebilir.
