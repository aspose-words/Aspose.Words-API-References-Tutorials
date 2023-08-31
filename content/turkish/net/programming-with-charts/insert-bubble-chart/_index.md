---
title: Word Belgesine Kabarcık Grafiği Ekleme
linktitle: Word Belgesine Kabarcık Grafiği Ekleme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir belgeye kabarcık grafiği eklemeyi öğrenin. Seri verilerini X, Y ve kabarcık boyutu değerleri ile ekleyin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/insert-bubble-chart/
---

Bu öğretici, Aspose.Words for .NET'in bir belgeye balon grafiği eklemek için nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve belgenin nasıl kaydedileceğini gösterir.

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

 Ardından,`InsertChart` yöntemi`DocumentBuilder` belgeye balon grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Seri verilerini grafiğe ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte, karşılık gelen X, Y ve kabarcık boyutu değerlerine sahip üç veri noktası ekleyeceğiz.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## 4. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

Bu, Aspose.Words for .NET kullanarak bir balon grafiği ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Balon Grafiği Ekleme için örnek kaynak kodu 

```csharp
//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesine balon grafiği eklemeyi öğrendiniz. Adım adım kılavuzu izleyerek ve verilen kaynak kodu kullanarak yeni bir belge oluşturabilir, balon grafiği ekleyebilir, seri verileri ekleyebilir ve belgeyi grafikle birlikte kaydedebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafiklerle Word Processing için güçlü bir API sağlar. Kabarcık grafikler, her veri noktasının X ve Y koordinatları ve bir boyut değeri olan bir balonla temsil edildiği üç boyutlu verileri görselleştirmek için idealdir. Aspose.Words for .NET ile, verilerinizin görsel sunumunu geliştiren dinamik ve bilgilendirici kabarcık çizelgeleri oluşturabilirsiniz.

Aspose.Words for .NET'i kullanarak kabarcık grafiklerle belge oluşturma sürecini otomatikleştirebilir, manuel belge oluşturmada zamandan ve emekten tasarruf edebilirsiniz. Kitaplık, Word belgelerinizde görsel olarak çekici ve veri açısından zengin grafikler oluşturmanıza olanak tanıyan çok çeşitli grafik türleri ve özelleştirme seçenekleri sunar.

### SSS

#### S1. Kabarcık grafiği nedir?
Kabarcık grafiği, kabarcıkları veya küreleri kullanarak üç boyutlu verileri görüntüleyen bir grafik türüdür. Her veri noktası, X ve Y koordinatlarının balonun grafik üzerindeki konumunu belirlediği ve balonun boyutunun verilerin üçüncü boyutunu temsil ettiği bir balonla temsil edilir. Kabarcık grafikleri, birden çok değişken arasındaki ilişkileri ve kalıpları görselleştirmek için kullanışlıdır.

#### S2. Kabarcık grafiğine birden çok seri ekleyebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak kabarcık grafiğine birden çok seri ekleyebilirsiniz. Her seri, ilgili X, Y ve kabarcık boyutu değerleri ile bir dizi veri noktasını temsil eder. Birden çok seri ekleyerek, verilerinizin kapsamlı bir görünümünü sağlayarak, aynı grafik içinde farklı veri kümelerini karşılaştırabilir ve analiz edebilirsiniz.

#### S3. Kabarcık grafiğinin görünümünü özelleştirebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak balon grafiğinin görünümünün çeşitli yönlerini özelleştirebilirsiniz. Seri rengi, kabarcık boyutu, eksen etiketleri ve grafik alanı biçimlendirmesi gibi özellikleri değiştirebilirsiniz. Kitaplık, grafiğin görsel öğelerini kontrol etmek ve ihtiyaçlarınıza uygun özelleştirilmiş bir görünüm oluşturmak için zengin bir API seti sağlar.

#### S4. Eklenen balon grafiğinin bulunduğu belgeyi farklı biçimlerde kaydedebilir miyim?
Evet, Aspose.Words for .NET, eklenen balon grafiği ile belgeyi DOCX, PDF, HTML ve daha fazlası gibi çeşitli biçimlerde kaydetmenize olanak tanır. Gereksinimlerinize göre istediğiniz çıktı formatını seçebilir ve`Save` yöntemi`Document` belgeyi kaydetmek için nesne. Eklenen balon grafiği kaydedilen belgede korunacaktır.

#### S5. Balon grafiğini ekledikten sonra verilerini ve görünümünü değiştirebilir miyim?
Evet, balon grafiğini belgeye ekledikten sonra, Aspose.Words for .NET tarafından sağlanan API'leri kullanarak grafiğin verilerini ve görünümünü değiştirebilirsiniz. Word belgelerinizde dinamik ve etkileşimli grafikler oluşturmak için seri verilerini güncelleyebilir, kabarcık boyutunu değiştirebilir, eksen özelliklerini özelleştirebilir ve biçimlendirme seçeneklerini uygulayabilirsiniz.