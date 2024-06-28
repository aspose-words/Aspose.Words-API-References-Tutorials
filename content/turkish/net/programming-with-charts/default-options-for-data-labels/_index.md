---
title: Grafikteki Veri Etiketleri İçin Varsayılan Seçenekleri Ayarlama
linktitle: Grafikteki Veri Etiketleri İçin Varsayılan Seçenekleri Ayarlama
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir grafikteki veri etiketleri için varsayılan seçenekleri nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/default-options-for-data-labels/
---

Bu eğitimde, bir grafikteki veri etiketleri için varsayılan seçenekleri ayarlamak amacıyla Aspose.Words for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan kod, Aspose.Words kullanarak bir grafiğin nasıl oluşturulacağını, veri serilerinin nasıl ekleneceğini ve veri etiketlerinin nasıl özelleştirileceğini gösterir.

## 1. Adım: Projeyi ayarlayın

Başlamadan önce aşağıdaki gereksinimlerin karşılandığından emin olun:

- Aspose.Words for .NET kütüphanesi kuruldu. Yüklemek için NuGet paket yöneticisini kullanarak indirebilirsiniz.
- Çıktı belgesinin kaydedileceği belge dizini yolu.

## Adım 2: Yeni bir belge oluşturun ve bir grafik ekleyin.

 İlk önce yeni bir tane oluşturalım`Document` nesne ve bir`DocumentBuilder` belgeyi oluşturmak için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Daha sonra belgeye bir grafik ekliyoruz.`InsertChart` yöntemi`DocumentBuilder`. Bu örnekte pasta grafiği ekleyeceğiz.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Grafiğe veri serisi ekleyin

Şimdi grafiğe bir veri serisi ekleyelim. Bu örnekte üç kategoriyi ve bunlara karşılık gelen değerleri ekleyeceğiz.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## 4. Adım: Veri etiketlerini özelleştirin

 Grafikteki veri etiketlerini özelleştirmek için`ChartDataLabelCollection` diziyle ilişkili nesne.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Daha sonra çeşitli özelliklerini değiştirebiliriz.`labels`Veri etiketleri için istenilen seçenekleri ayarlamak için nesneyi seçin. Bu örnekte yüzde ve değerin gösterilmesini etkinleştireceğiz, öncü çizgileri devre dışı bırakacağız ve özel bir ayırıcı ayarlayacağız.

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

Bu, Aspose.Words for .NET kullanılarak bir grafikteki veri etiketleri için varsayılan seçeneklerin ayarlanması uygulamasını tamamlar.

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

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir grafikteki veri etiketleri için varsayılan seçenekleri nasıl ayarlayacağınızı öğrendiniz. Adım adım kılavuzu izleyerek bir grafik oluşturabilir, veri serileri ekleyebilir ve veri etiketlerini özel gereksinimlerinizi karşılayacak şekilde özelleştirebilirsiniz. Aspose.Words for .NET, Word belgelerindeki grafiklerle Kelime İşleme için güçlü bir API sağlayarak çeşitli grafik öğelerini değiştirmenize ve istediğiniz görünüm ve işlevselliğe ulaşmanıza olanak tanır.

 Özelliklerini ayarlayarak`ChartDataLabelCollection`Grafik serisiyle ilişkili nesneyi kullanarak, yüzdeleri, değerleri, öncü çizgileri ve özel ayırıcıları gösterme gibi seçenekler de dahil olmak üzere veri etiketlerinin görünümünü kontrol edebilirsiniz. Bu esneklik, verileri etkili bir şekilde sunmanıza ve grafiklerinizin görsel sunumunu geliştirmenize olanak tanır.

### SSS

#### S1. Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin .NET uygulamalarını kullanarak Word belgelerini programlı olarak oluşturmasına, yönetmesine ve kaydetmesine olanak tanıyan bir kitaplıktır. Grafikler de dahil olmak üzere belge öğeleriyle Kelime İşleme için geniş bir özellik yelpazesi sunar.

#### Q2. Aspose.Words for .NET'i nasıl kurabilirim?
Aspose.Words for .NET'i Visual Studio'daki NuGet paket yöneticisini kullanarak indirerek kurabilirsiniz. NuGet paket yöneticisinde "Apose.Words" ifadesini aramanız ve projenize yüklemeniz yeterlidir.

#### S3. Aspose.Words for .NET'i kullanarak grafiğin diğer yönlerini özelleştirebilir miyim?
Evet, Aspose.Words for .NET bir grafiğin grafik türü, eksen etiketleri, açıklama, çizim alanı ve daha fazlası gibi çeşitli yönlerini özelleştirmenize olanak tanır. İstediğiniz görünümü ve davranışı elde etmek için grafik nesnesinin farklı özelliklerine erişebilir ve bunları değiştirebilirsiniz.

#### S4. Grafiği farklı formatlarda kaydedebilir miyim?
 Evet, Aspose.Words for .NET, grafiği içeren belgenin DOCX, PDF, HTML ve daha fazlası dahil olmak üzere çeşitli formatlarda kaydedilmesini destekler. Gereksinimlerinize göre uygun formatı seçebilir ve`Save` yöntemi`Document` Belgeyi kaydetmek için nesne.

#### S5. Bu teknikleri diğer grafik türlerine uygulayabilir miyim?
Evet, bu eğitimde açıklanan teknikler Aspose.Words for .NET tarafından desteklenen diğer grafik türlerine de uygulanabilir. Anahtar, Kelime İşleme yaptığınız grafik türüne özgü ilgili nesnelere ve özelliklere erişmektir.