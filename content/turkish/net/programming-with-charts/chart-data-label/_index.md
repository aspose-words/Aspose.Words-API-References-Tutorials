---
title: Grafik Veri Etiketini Özelleştir
linktitle: Grafik Veri Etiketini Özelleştir
second_title: Aspose.Words Belge İşleme API'si
description: Veri noktaları hakkında ek bilgi sağlamak için Aspose.Words for .NET'i kullanarak bir grafiğe veri etiketlerini nasıl ekleyeceğinizi ve özelleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/chart-data-label/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir grafiğe veri etiketlerinin nasıl ekleneceği ve özelleştirileceği açıklanmaktadır. Veri etiketleri bir grafikteki veri noktaları hakkında ek bilgi sağlar.

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
 Yeni bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder`belgeyle çalışmaya itiraz edin.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Grafik Ekleme ve Yapılandırma
 kullanarak belgeye bir grafik ekleyin.`InsertChart` yöntemi`DocumentBuilder` nesne. İstediğiniz grafik türünü ve boyutlarını ayarlayın.

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

## Adım 5: Belgeyi Kaydedin
 Belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithCharts.ChartDataLabel.docx" olarak kaydediyoruz.

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
	// Varsayılan olarak, pasta grafikteki veri noktalarına veri etiketleri eklediğinizde, veri etiketleri için öncü çizgiler görüntülenir.
	// veri noktalarının sonunun çok dışında konumlanmıştır. Lider çizgileri, veri etiketi ile veri etiketi arasında görsel bir bağlantı oluşturur.
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

Bu kadar! Aspose.Words for .NET'i kullanarak bir grafiğe başarıyla veri etiketleri eklediniz ve özelleştirdiniz.

## Çözüm
Bu eğitimde Aspose.Words for .NET'i kullanarak bir grafiğe veri etiketlerini nasıl ekleyeceğinizi ve özelleştireceğinizi öğrendiniz. Adım adım kılavuzu izleyerek bir grafik ekleyebilir, veri etiketleri koleksiyonuna erişebilir ve veri etiketlerinin görünümünü özelleştirmek için özellikleri değiştirebilirsiniz. Aspose.Words for .NET, Word belgeleri ve grafikleriyle Kelime İşleme için güçlü bir API sunarak özelleştirilmiş veri etiketleriyle görsel olarak çekici ve bilgilendirici grafikler oluşturmanıza olanak tanır.

### SSS

#### S1. Grafikteki veri etiketleri nelerdir?
Grafikteki veri etiketleri, grafikte temsil edilen veri noktaları hakkında ek bilgi sağlar. Grafik türüne ve yapılandırmaya bağlı olarak değerleri, kategorileri, seri adlarını, yüzdeleri veya diğer ilgili ayrıntıları görüntüleyebilirler.

#### Q2. Veri etiketlerinin görünümünü özelleştirebilir miyim?
Evet, bir grafikteki veri etiketlerinin görünümünü özelleştirebilirsiniz. Aspose.Words for .NET, gösterge anahtarlarını, öncü çizgileri, kategori adlarını, seri adlarını, değerleri ve daha fazlasını gösterme gibi veri etiketlerinin çeşitli özelliklerini değiştirmek için seçenekler sunar. Ayrıca ayırıcıları ayarlayabilir ve etiketleri özel gereksinimlerinizi karşılayacak şekilde biçimlendirebilirsiniz.

#### S3. Herhangi bir grafik türüne veri etiketleri ekleyebilir miyim?
Evet, çubuk grafikler, pasta grafikler, çizgi grafikler ve daha fazlasını içeren çeşitli grafik türlerine veri etiketleri ekleyebilirsiniz. Veri etiketlerini ekleme ve özelleştirme işlemi, grafik türüne ve kullandığınız kitaplığa veya araca bağlı olarak biraz farklılık gösterebilir.
