---
title: Bir Word Belgesine Basit Sütun Grafiği Ekleme
linktitle: Bir Word Belgesine Basit Sütun Grafiği Ekleme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir belgeye basit bir sütun grafiği eklemeyi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/insert-simple-column-chart/
---

Bu öğretici, bir belgeye basit bir sütun grafiği eklemek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve belgenin nasıl kaydedileceğini gösterir.

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

 Ardından,`InsertChart` yöntemi`DocumentBuilder` belgeye bir sütun grafiği eklemek için. Gereksinimlerinize göre farklı grafik türleri ve boyutları belirleyebilirsiniz.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Seri verilerini grafiğe ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte, her biri iki kategoriye sahip birden çok seri ekleyeceğiz.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## 4. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

Bu, Aspose.Words for .NET kullanarak basit bir sütun grafiği ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Basit Sütun Grafiği Ekleme için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Farklı grafik türleri ve boyutları belirleyebilirsiniz.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Oluşturulan varsayılan seriyi silin.
	seriesColl.Clear();
	// Kategori adları dizisi oluşturun, bu eğitimde iki kategorimiz var.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Lütfen dikkat, veri dizileri boş olmamalıdır ve diziler aynı boyutta olmalıdır.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak basit bir sütun grafiğini bir Word belgesine nasıl ekleyeceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak yeni bir belge oluşturabilir, bir sütun grafiği ekleyebilir, kategoriler ve karşılık gelen değerlerle birden çok seri ekleyebilir ve belgeyi grafikle birlikte kaydedebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafiklerle Word Processing için güçlü ve esnek bir API sağlar. Basit sütun grafiği, farklı kategorilerdeki verileri temsil etmenin ve karşılaştırmanın etkili bir yoludur. Aspose.Words for .NET ile, özel verilerle kolayca sütun grafikler oluşturabilir, görsel karşılaştırma için birden çok seri ekleyebilir ve gereksinimlerinize göre grafiğin görünümünü özelleştirebilirsiniz.

Aspose.Words for .NET'i kullanarak sütun grafiklerle belge oluşturma sürecini otomatikleştirebilir, manuel belge oluşturmada zamandan ve emekten tasarruf edebilirsiniz. Kitaplık, basit sütun grafikler de dahil olmak üzere çok çeşitli grafik türleri sunar ve grafiğin görünümünü ihtiyaçlarınıza göre uyarlamak için çeşitli özelleştirme seçenekleri sunar.

### SSS

#### S1. Sütun grafiği nedir?
Sütun grafiği, verileri değişen yüksekliklerde dikey çubuklar kullanarak görüntüleyen bir grafik türüdür. Her sütun bir kategoriyi temsil eder ve sütunun yüksekliği o kategorinin değerine karşılık gelir. Sütun grafikleri, genellikle farklı kategorilerdeki verileri karşılaştırmak veya zaman içindeki değişiklikleri izlemek için kullanılır.

#### S2. Sütun grafiğine birden çok seri ekleyebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak sütun grafiğine birden çok seri ekleyebilirsiniz. Her seri, ilgili kategorileri ve değerleri ile bir dizi veri noktasını temsil eder. Birden çok seri ekleyerek, aynı sütun grafiğinde farklı veri kümelerini karşılaştırabilir ve analiz edebilir, verilerinizin kapsamlı bir görünümünü elde edebilirsiniz.

#### S3. Sütun grafiğinin görünümünü özelleştirebilir miyim?
Evet, Aspose.Words for .NET, sütun grafiğinin görünümünün çeşitli yönlerini özelleştirmenize izin verir. Seri rengi, eksen etiketleri, veri etiketleri ve grafik alanı biçimlendirmesi gibi özellikleri değiştirebilirsiniz. Kitaplık, grafiğin görsel öğelerini kontrol etmek ve ihtiyaçlarınıza uygun özelleştirilmiş bir görünüm oluşturmak için zengin bir API seti sağlar.

#### S4. Sütun grafiği eklenen belgeyi farklı biçimlerde kaydedebilir miyim?
 Evet, Aspose.Words for .NET belgeyi DOCX, PDF, HTML ve daha fazlası gibi çeşitli biçimlerde eklenen sütun grafiğiyle birlikte kaydetmenize olanak tanır. Gereksinimlerinize göre istediğiniz çıktı formatını seçebilir ve`Save` yöntemi`Document` belgeyi kaydetmek için nesne. Eklenen sütun grafiği kaydedilen belgede korunacaktır.

#### S5. Ekledikten sonra sütun grafiğinin verilerini ve görünümünü değiştirebilir miyim?
Evet, sütun grafiğini belgeye ekledikten sonra Aspose.Words for .NET tarafından sağlanan API'leri kullanarak grafiğin verilerini ve görünümünü değiştirebilirsiniz. Word belgelerinizde dinamik ve görsel olarak çekici grafikler oluşturmak için seri verilerini yeni kategoriler ve değerlerle güncelleyebilir, sütunların renklerini ve biçimlendirmesini değiştirebilir, eksen özelliklerini özelleştirebilir ve çeşitli biçimlendirme seçeneklerini uygulayabilirsiniz.