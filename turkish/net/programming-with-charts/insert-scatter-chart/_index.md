---
title: Word Belgesine Dağılım Grafiği Ekleme
linktitle: Word Belgesine Dağılım Grafiği Ekleme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir belgeye dağılım grafiği eklemeyi öğrenin. X ve Y koordinatlarıyla seri verileri ekleyin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/insert-scatter-chart/
---

Bu öğretici, bir belgeye dağılım grafiği eklemek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve belgenin nasıl kaydedileceğini gösterir.

## 1. Adım: Projeyi kurun

Aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı yüklendi. Yüklemek için NuGet paket yöneticisini kullanarak indirebilirsiniz.
- Çıktı belgesinin kaydedileceği bir belge dizini yolu.

## 2. Adım: Yeni bir belge oluşturun ve bir grafik ekleyin

 Yeni bir tane oluştur`Document` nesne ve bir`DocumentBuilder` belgeyi oluşturmak için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ardından,`InsertChart` yöntemi`DocumentBuilder` belgeye bir dağılım grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Seri verilerini grafiğe ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte, iki set X ve Y koordinatı ekleyeceğiz.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## 4. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Bu, Aspose.Words for .NET kullanarak bir dağılım grafiği ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Dağılım Grafiği Ekleme için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesine nasıl dağılım grafiği ekleyeceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve verilen kaynak kodu kullanarak yeni bir belge oluşturabilir, dağılım grafiği ekleyebilir, X ve Y koordinatlarıyla seri verileri ekleyebilir ve belgeyi grafikle kaydedebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafiklerle Kelime İşleme için kapsamlı bir API sağlar. Dağılım grafikleri, verileri iki sayısal değişkenle görselleştirmek ve analiz etmek için kullanışlıdır. Aspose.Words for .NET ile X ve Y değerleri arasındaki ilişkiyi temsil eden dağılım grafiklerini kolayca oluşturabilir ve verilerdeki kalıpları veya eğilimleri belirleyebilirsiniz.

Aspose.Words for .NET'i kullanarak, dağılım grafikleriyle belge oluşturma sürecini otomatikleştirebilir, manuel belge oluşturmada zamandan ve emekten tasarruf edebilirsiniz. Kitaplık, dağılım grafikleri de dahil olmak üzere çok çeşitli grafik türleri sunar ve grafiğin görünümünü ihtiyaçlarınıza göre uyarlamak için çeşitli özelleştirme seçenekleri sunar.

### SSS

#### S1. Dağılım grafiği nedir?
Dağılım grafiği, iki sayısal değişken arasındaki ilişkiyi gösteren bir grafik türüdür. Bir değişkenin X ekseninde ve diğer değişkenin Y ekseninde temsil edildiği bir koordinat ızgarasında çizilen bir dizi noktadan oluşur. Dağılım grafikleri, iki veri noktası kümesi arasındaki kalıpları, korelasyonları veya eğilimleri belirlemek için kullanılır.

#### S2. Dağılım grafiğine birden çok seri ekleyebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak dağılım grafiğine birden çok seri ekleyebilirsiniz. Her seri, ilgili X ve Y koordinatlarıyla birlikte bir dizi veri noktasını temsil eder. Birden çok seri ekleyerek, aynı dağılım grafiği içinde farklı veri kümelerini karşılaştırabilir ve analiz edebilir, verilerinizin kapsamlı bir görünümünü elde edebilirsiniz.

#### S3. Dağılım grafiğinin görünümünü özelleştirebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak, dağılım grafiğinin görünümünün çeşitli yönlerini özelleştirebilirsiniz. Seri rengi, işaretçi şekli, eksen etiketleri ve grafik alanı biçimlendirmesi gibi özellikleri değiştirebilirsiniz. Kitaplık, grafiğin görsel öğelerini kontrol etmek ve ihtiyaçlarınıza uygun özelleştirilmiş bir görünüm oluşturmak için zengin bir API seti sağlar.

#### S4. Dağılım grafiği eklenmiş belgeyi farklı biçimlerde kaydedebilir miyim?
Evet, Aspose.Words for .NET belgeyi DOCX, PDF, HTML ve daha fazlası gibi çeşitli biçimlerde eklenen dağılım grafiği ile kaydetmenize olanak tanır. Gereksinimlerinize göre istediğiniz çıktı formatını seçebilir ve`Save` yöntemi`Document` belgeyi kaydetmek için nesne. Eklenen dağılım grafiği kaydedilen belgede korunacaktır.

#### S5. Dağılım grafiğini ekledikten sonra verilerini ve görünümünü değiştirebilir miyim?
Evet, dağılım grafiğini belgeye ekledikten sonra Aspose.Words for .NET tarafından sağlanan API'leri kullanarak verilerini ve görünümünü değiştirebilirsiniz. Seri verilerini yeni X ve Y koordinatlarıyla güncelleyebilir, işaretçi şekillerini ve renklerini değiştirebilir, eksen özelliklerini özelleştirebilir ve Word belgelerinizde dinamik ve etkileşimli grafikler oluşturmak için biçimlendirme seçeneklerini uygulayabilirsiniz.