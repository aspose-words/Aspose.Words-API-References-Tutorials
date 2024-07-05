---
title: Grafikteki Veri Etiketi Sayısını Biçimlendir
linktitle: Grafikteki Veri Etiketi Sayısını Biçimlendir
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir grafikteki veri etiketi sayısını nasıl formatlayacağınızı öğrenin. Veri etiketleri için sayı formatlarını kolayca özelleştirin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/format-number-of-data-label/
---

Bu eğitimde bir grafikteki veri etiketi sayısını biçimlendirmek için Aspose.Words for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve veri etiketlerinin sayı biçiminin nasıl özelleştirileceğini gösterir.

## 1. Adım: Projeyi ayarlayın

Aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kütüphanesi kuruldu. Yüklemek için NuGet paket yöneticisini kullanarak indirebilirsiniz.
- Çıktı belgesinin kaydedileceği belge dizini yolu.

## 2. Adım: Yeni bir belge oluşturun ve grafik ekleyin

 Yeni bir tane oluştur`Document` nesne ve bir`DocumentBuilder` belgeyi oluşturmak için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Daha sonra belgeye bir grafik ekleyin.`InsertChart` yöntemi`DocumentBuilder`. Bu örnekte bir çizgi grafiği ekleyeceğiz.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## 3. Adım: Grafiğe seri verilerini ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte üç kategoriyi ve bunlara karşılık gelen değerleri ekleyeceğiz.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## 4. Adım: Veri etiketlerinin sayı biçimini özelleştirin

 Veri etiketi sayısını biçimlendirmek için şuraya erişin:`DataLabels` seriyle ilişkili koleksiyon.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

Bu örnekte her veri etiketi için farklı sayı formatları belirledik. İlk veri etiketi para birimi, ikincisi tarih ve üçüncüsü yüzde olarak biçimlendirilmiştir.

## 5. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Bu, Aspose.Words for .NET kullanarak bir grafikteki veri etiketi sayısını biçimlendirme uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Veri Etiketi Sayısını Formatla için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Varsayılan oluşturulan seriyi silin.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Veya biçim kodunu bir kaynak hücreye bağlanacak şekilde ayarlayabilirsiniz.
	//bu durumda NumberFormat genel olarak sıfırlanacak ve bir kaynak hücreden devralınacaktır.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir grafikteki veri etiketi sayısını nasıl formatlayacağınızı öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak bir grafik oluşturabilir, seri verileri ekleyebilir ve veri etiketlerinin sayı biçimini gereksinimlerinize göre özelleştirebilirsiniz.

 Aspose.Words for .NET, Word belgelerindeki grafiklerle Kelime İşleme için kapsamlı bir API sunarak, veri etiketleri de dahil olmak üzere grafiğin çeşitli yönlerini değiştirmenize olanak tanır. Erişerek`DataLabels` bir seriyle ilişkili koleksiyon, tek tek veri etiketlerinin sayı biçimini özelleştirebilirsiniz.

API, değerlerin görüntülenmesini kontrol etmenize, her veri etiketi için farklı sayı biçimleri ayarlamanıza ve sayı biçimini bir kaynak hücreye bağlamanıza olanak tanır. Bu esneklik, sayısal verileri grafiklerde para birimi simgeleri, tarih biçimleri ve yüzde değerleri gibi istediğiniz biçimlendirmeyle sunmanıza olanak tanır.

Aspose.Words for .NET'i kullanarak, güçlü grafik oluşturma yeteneklerini .NET uygulamalarınıza dahil edebilir ve tamamen formatlanmış grafikler ve veri etiketleriyle profesyonel görünümlü belgeler oluşturabilirsiniz.

### SSS

#### S1. Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin .NET uygulamalarında Word belgelerini programlı olarak oluşturmasına, değiştirmesine ve kaydetmesine olanak tanıyan, zengin özelliklere sahip bir belge işleme kitaplığıdır. Grafikler ve veri etiketleri de dahil olmak üzere belge öğeleriyle Kelime İşleme için geniş bir özellik yelpazesi sunar.

#### Q2. Aspose.Words for .NET'i nasıl kurabilirim?
Aspose.Words for .NET'i, Visual Studio'daki NuGet paket yöneticisini kullanarak indirerek kurabilirsiniz. NuGet paket yöneticisinde "Aspose.Words" ifadesini arayın ve projenize yükleyin.

#### S3. Grafiğin diğer yönlerini Aspose.Words for .NET kullanarak formatlayabilir miyim?
Evet, Aspose.Words for .NET bir grafiğin çeşitli yönlerini biçimlendirmek için kapsamlı yetenekler sağlar. Veri etiketlerine ek olarak grafik türünü, seri verilerini, eksen özelliklerini, açıklamayı, başlığı, çizim alanını ve grafiğin diğer birçok öğesini özelleştirebilirsiniz. API, grafik görünümü ve biçimlendirme üzerinde ayrıntılı kontrol sunar.

#### S4. Aynı serideki farklı veri etiketlerine farklı sayı formatları uygulayabilir miyim?
Evet, Aspose.Words for .NET, aynı seri içindeki bireysel veri etiketlerine farklı sayı formatları uygulamanıza olanak tanır. Erişerek`DataLabels` bir seriyle ilişkili koleksiyonu ayarlayabilirsiniz.`FormatCode` İstenilen sayı biçimini belirtmek için her veri etiketinin özelliği. Bu, sayısal değerleri aynı grafikte farklı formatlarda sunmanıza olanak tanır.

#### S5. Veri etiketleri için özel sayı formatlarını kullanabilir miyim?
 Evet, Aspose.Words for .NET, veri etiketleri için özel sayı formatlarını destekler. İstediğiniz sayı formatını ayarlayarak belirleyebilirsiniz.`FormatCode` bir veri etiketinin özelliğini özel bir biçim koduna dönüştürür. Bu size para birimi simgeleri, tarih biçimleri, yüzde değerleri ve daha fazlası gibi çok çeşitli sayı biçimlerini uygulama esnekliği sağlar.

#### S6. Grafiği, biçimlendirilmiş veri etiketleriyle farklı biçimlerde kaydedebilir miyim?
Evet, Aspose.Words for .NET, grafiği içeren belgeyi biçimlendirilmiş veri etiketleriyle birlikte DOCX, PDF, HTML ve daha fazlası gibi çeşitli formatlarda kaydetmenize olanak tanır. Gereksinimlerinize göre uygun formatı seçebilir ve`Save` yöntemi`Document` Belgeyi kaydetmek için nesne. Biçimlendirilmiş veri etiketleri kaydedilen belgede korunacaktır.