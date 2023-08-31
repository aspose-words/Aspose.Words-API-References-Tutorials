---
title: Bir Word Belgesine Sütun Grafiği Ekleme
linktitle: Bir Word Belgesine Sütun Grafiği Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir belgeye nasıl sütun grafiği ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/insert-column-chart/
---

Bu eğitimde Aspose.Words for .NET'in bir belgeye sütun grafiği eklemek için nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve belgenin nasıl kaydedileceğini gösterir.

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

 Daha sonra şunu kullanın:`InsertChart` yöntemi`DocumentBuilder` Belgeye bir sütun grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Grafiğe seri verilerini ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte iki kategoriyi ve bunlara karşılık gelen değerleri ekleyeceğiz.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## 4. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

Bu, Aspose.Words for .NET kullanarak sütun grafiği ekleme işlemini tamamlar.

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

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesine nasıl sütun grafiği ekleyeceğinizi öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodunu kullanarak yeni bir belge oluşturabilir, sütun grafiği ekleyebilir, seri verileri ekleyebilir ve belgeyi grafikle birlikte kaydedebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafiklerle Kelime İşleme için güçlü bir API sağlar. Sütun grafikleri, farklı kategorilerdeki veya gruplardaki verileri görüntülemek ve karşılaştırmak için yaygın olarak kullanılır. Aspose.Words for .NET ile verilerinizi etkili bir şekilde görselleştiren ve değerli bilgiler sağlayan sütun grafiklerini kolayca oluşturabilirsiniz.

Aspose.Words for .NET'i kullanarak, sütun grafikleriyle belge oluşturma sürecini otomatikleştirebilir, manuel belge oluşturmada zamandan ve emekten tasarruf edebilirsiniz. Kitaplık, Word belgelerinizde görsel olarak çekici ve veri açısından zengin grafikler oluşturmanıza olanak tanıyan çok çeşitli grafik türleri ve özelleştirme seçenekleri sunar.

### SSS

#### S1. Sütun grafiği nedir?
Sütun grafiği, verileri dikey çubuklar veya sütunlar halinde temsil eden bir grafik türüdür. Her sütun tipik olarak bir kategoriyi veya grubu temsil eder ve sütunun yüksekliği veya uzunluğu o kategoriyle ilişkili verilerin değerini gösterir. Sütun grafikleri, farklı kategorilerdeki verileri karşılaştırmak veya zaman içindeki değişiklikleri izlemek için yaygın olarak kullanılır.

#### Q2. Sütun grafiğine birden fazla seri ekleyebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak sütun grafiğine birden fazla seri ekleyebilirsiniz. Her seri, ilgili kategorileri ve değerleri ile birlikte bir dizi veri noktasını temsil eder. Birden fazla seri ekleyerek aynı grafikteki farklı veri kümelerini karşılaştırıp analiz edebilir, verilerinizin kapsamlı bir görünümünü sağlayabilirsiniz.

#### S3. Sütun grafiğinin görünümünü özelleştirebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak sütun grafiğinin görünümünün çeşitli yönlerini özelleştirebilirsiniz. Seri rengi, eksen etiketleri, sütun genişliği ve grafik alanı formatlaması gibi özellikleri değiştirebilirsiniz. Kitaplık, grafiğin görsel öğelerini kontrol etmek ve ihtiyaçlarınıza uygun özelleştirilmiş bir görünüm oluşturmak için zengin bir API seti sağlar.

#### S4. Sütun grafiği eklenen belgeyi farklı formatlarda kaydedebilir miyim?
 Evet, Aspose.Words for .NET, belgeyi eklenen sütun grafiğiyle birlikte DOCX, PDF, HTML ve daha fazlası gibi çeşitli formatlarda kaydetmenize olanak tanır. Gereksinimlerinize göre istediğiniz çıktı formatını seçebilir ve`Save` yöntemi`Document` Belgeyi kaydetmek için nesne. Eklenen sütun grafiği kaydedilen belgede korunacaktır.

#### S5. Sütun grafiğini ekledikten sonra verilerini ve görünümünü değiştirebilir miyim?
Evet, sütun grafiğini belgeye ekledikten sonra Aspose.Words for .NET tarafından sağlanan API'leri kullanarak verilerini ve görünümünü değiştirebilirsiniz. Word belgelerinizde dinamik ve etkileşimli grafikler oluşturmak için seri verilerini güncelleyebilir, sütun renklerini değiştirebilir, eksen özelliklerini özelleştirebilir ve biçimlendirme seçeneklerini uygulayabilirsiniz.