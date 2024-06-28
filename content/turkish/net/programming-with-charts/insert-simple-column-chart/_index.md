---
title: Bir Word Belgesine Basit Sütun Grafiği Ekleme
linktitle: Bir Word Belgesine Basit Sütun Grafiği Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir belgeye basit bir sütun grafiğinin nasıl eklendiğini öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/insert-simple-column-chart/
---

Bu eğitimde, bir belgeye basit bir sütun grafiği eklemek için Aspose.Words for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve belgenin nasıl kaydedileceğini gösterir.

## 1. Adım: Projeyi ayarlayın

Aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kütüphanesi kuruldu. Yüklemek için NuGet paket yöneticisini kullanarak indirebilirsiniz.
- Çıktı belgesinin kaydedileceği belge dizini yolu.

## Adım 2: Yeni bir belge oluşturun ve bir grafik ekleyin.

 Yeni bir tane oluştur`Document` nesne ve bir`DocumentBuilder` belgeyi oluşturmak için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Daha sonra şunu kullanın:`InsertChart` yöntemi`DocumentBuilder` Belgeye bir sütun grafiği eklemek için. Gereksinimlerinize göre farklı grafik türleri ve boyutları belirleyebilirsiniz.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Grafiğe seri verilerini ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte, her biri iki kategoriye sahip birden fazla seri ekleyeceğiz.

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

Bu, Aspose.Words for .NET kullanarak basit bir sütun grafiği ekleme işlemini tamamlar.

### Aspose.Words for .NET kullanarak Basit Sütun Grafiği Ekleme için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Farklı grafik türleri ve boyutları belirtebilirsiniz.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Varsayılan oluşturulan seriyi silin.
	seriesColl.Clear();
	// Kategori adları dizisi oluşturun, bu derste iki kategorimiz var.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Veri dizilerinin boş olmaması ve dizilerin aynı boyutta olması gerektiğini lütfen unutmayın.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Çözüm

Bu eğitimde Aspose.Words for .NET'i kullanarak bir Word belgesine basit bir sütun grafiğinin nasıl ekleneceğini öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodunu kullanarak yeni bir belge oluşturabilir, sütun grafiği ekleyebilir, kategoriler ve karşılık gelen değerlerle birden fazla seri ekleyebilir ve belgeyi grafikle birlikte kaydedebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafiklerle Kelime İşleme için güçlü ve esnek bir API sağlar. Basit sütun grafiği, farklı kategorilerdeki verileri temsil etmenin ve karşılaştırmanın etkili bir yoludur. Aspose.Words for .NET ile özel verilerle kolayca sütun grafikleri oluşturabilir, görsel karşılaştırma için birden fazla seri ekleyebilir ve grafiğin görünümünü gereksinimlerinize göre özelleştirebilirsiniz.

Aspose.Words for .NET'i kullanarak, sütun grafikleriyle belge oluşturma sürecini otomatikleştirebilir, manuel belge oluşturmada zamandan ve emekten tasarruf edebilirsiniz. Kitaplık, basit sütun grafikleri de dahil olmak üzere çok çeşitli grafik türleri sunar ve grafiğin görünümünü ihtiyaçlarınıza uyacak şekilde uyarlamak için çeşitli özelleştirme seçenekleri sunar.

### SSS

#### S1. Sütun grafiği nedir?
Sütun grafiği, verileri değişen yüksekliklerdeki dikey çubukları kullanarak görüntüleyen bir grafik türüdür. Her sütun bir kategoriyi temsil eder ve sütunun yüksekliği o kategorinin değerine karşılık gelir. Sütun grafikleri, farklı kategorilerdeki verileri karşılaştırmak veya zaman içindeki değişiklikleri izlemek için yaygın olarak kullanılır.

#### Q2. Sütun grafiğine birden fazla seri ekleyebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak sütun grafiğine birden fazla seri ekleyebilirsiniz. Her seri, ilgili kategorileri ve değerleri ile birlikte bir dizi veri noktasını temsil eder. Birden fazla seri ekleyerek, aynı sütun grafiğindeki farklı veri kümelerini karşılaştırıp analiz edebilir, verilerinizin kapsamlı bir görünümünü sağlayabilirsiniz.

#### S3. Sütun grafiğinin görünümünü özelleştirebilir miyim?
Evet, Aspose.Words for .NET, sütun grafiğinin görünümünün çeşitli yönlerini özelleştirmenize olanak tanır. Seri rengi, eksen etiketleri, veri etiketleri ve grafik alanı formatlaması gibi özellikleri değiştirebilirsiniz. Kitaplık, grafiğin görsel öğelerini kontrol etmek ve ihtiyaçlarınıza uygun özelleştirilmiş bir görünüm oluşturmak için zengin bir API seti sağlar.

#### S4. Sütun grafiği eklenen belgeyi farklı formatlarda kaydedebilir miyim?
 Evet, Aspose.Words for .NET, belgeyi eklenen sütun grafiğiyle birlikte DOCX, PDF, HTML ve daha fazlası gibi çeşitli formatlarda kaydetmenize olanak tanır. Gereksinimlerinize göre istediğiniz çıktı formatını seçebilir ve`Save` yöntemi`Document` Belgeyi kaydetmek için nesne. Eklenen sütun grafiği kaydedilen belgede korunacaktır.

#### S5. Sütun grafiğini ekledikten sonra verilerini ve görünümünü değiştirebilir miyim?
Evet, sütun grafiğini belgeye ekledikten sonra Aspose.Words for .NET tarafından sağlanan API'leri kullanarak verilerini ve görünümünü değiştirebilirsiniz. Seri verilerini yeni kategoriler ve değerlerle güncelleyebilir, sütunların renklerini ve biçimlendirmesini değiştirebilir, eksen özelliklerini özelleştirebilir ve çeşitli biçimlendirme seçeneklerini uygulayarak Word belgelerinizde dinamik ve görsel olarak çekici grafikler oluşturabilirsiniz.