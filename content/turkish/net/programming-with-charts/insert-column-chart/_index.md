---
title: Bir Word Belgesine Sütun Grafiği Ekleme
linktitle: Bir Word Belgesine Sütun Grafiği Ekleme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir belgeye sütun grafiği eklemeyi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/insert-column-chart/
---

Bu öğretici, bir belgeye sütun grafiği eklemek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve belgenin nasıl kaydedileceğini gösterir.

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

 Ardından,`InsertChart` yöntemi`DocumentBuilder` belgeye bir sütun grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Seri verilerini grafiğe ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte, iki kategori ve bunlara karşılık gelen değerleri ekleyeceğiz.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## 4. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

Bu, Aspose.Words for .NET kullanarak bir sütun grafiği ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Sütun Grafiği Ekleme için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesine sütun grafiği eklemeyi öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak yeni bir belge oluşturabilir, sütun grafiği ekleyebilir, seri verileri ekleyebilir ve belgeyi grafikle kaydedebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafiklerle Word Processing için güçlü bir API sağlar. Sütun grafikleri, farklı kategoriler veya gruplar arasında verileri görüntülemek ve karşılaştırmak için yaygın olarak kullanılır. Aspose.Words for .NET ile verilerinizi etkili bir şekilde görselleştiren ve değerli içgörüler sağlayan sütun grafiklerini kolayca oluşturabilirsiniz.

Aspose.Words for .NET'i kullanarak sütun grafiklerle belge oluşturma sürecini otomatikleştirebilir, manuel belge oluşturmada zamandan ve emekten tasarruf edebilirsiniz. Kitaplık, Word belgelerinizde görsel olarak çekici ve veri açısından zengin grafikler oluşturmanıza olanak tanıyan çok çeşitli grafik türleri ve özelleştirme seçenekleri sunar.

### SSS

#### S1. Sütun grafiği nedir?
Sütun grafiği, verileri dikey çubuklar veya sütunlar halinde temsil eden bir grafik türüdür. Her sütun tipik olarak bir kategoriyi veya grubu temsil eder ve sütunun yüksekliği veya uzunluğu o kategoriyle ilişkili verilerin değerini gösterir. Sütun grafikleri, genellikle farklı kategorilerdeki verileri karşılaştırmak veya zaman içindeki değişiklikleri izlemek için kullanılır.

#### S2. Sütun grafiğine birden çok seri ekleyebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak sütun grafiğine birden çok seri ekleyebilirsiniz. Her seri, ilgili kategorileri ve değerleri ile bir dizi veri noktasını temsil eder. Birden çok seri ekleyerek, verilerinizin kapsamlı bir görünümünü sağlayarak, aynı grafik içinde farklı veri kümelerini karşılaştırabilir ve analiz edebilirsiniz.

#### S3. Sütun grafiğinin görünümünü özelleştirebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak sütun grafiğinin görünümünün çeşitli yönlerini özelleştirebilirsiniz. Seri rengi, eksen etiketleri, sütun genişliği ve grafik alanı biçimlendirmesi gibi özellikleri değiştirebilirsiniz. Kitaplık, grafiğin görsel öğelerini kontrol etmek ve ihtiyaçlarınıza uygun özelleştirilmiş bir görünüm oluşturmak için zengin bir API seti sağlar.

#### S4. Sütun grafiği eklenen belgeyi farklı biçimlerde kaydedebilir miyim?
 Evet, Aspose.Words for .NET belgeyi DOCX, PDF, HTML ve daha fazlası gibi çeşitli biçimlerde eklenen sütun grafiğiyle birlikte kaydetmenize olanak tanır. Gereksinimlerinize göre istediğiniz çıktı formatını seçebilir ve`Save` yöntemi`Document` belgeyi kaydetmek için nesne. Eklenen sütun grafiği kaydedilen belgede korunacaktır.

#### S5. Ekledikten sonra sütun grafiğinin verilerini ve görünümünü değiştirebilir miyim?
Evet, sütun grafiğini belgeye ekledikten sonra Aspose.Words for .NET tarafından sağlanan API'leri kullanarak grafiğin verilerini ve görünümünü değiştirebilirsiniz. Word belgelerinizde dinamik ve etkileşimli grafikler oluşturmak için seri verilerini güncelleyebilir, sütun renklerini değiştirebilir, eksen özelliklerini özelleştirebilir ve biçimlendirme seçeneklerini uygulayabilirsiniz.