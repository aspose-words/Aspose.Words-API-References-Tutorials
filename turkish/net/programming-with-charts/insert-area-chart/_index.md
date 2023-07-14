---
title: Bir Word Belgesine Alan Grafiği Ekleme
linktitle: Bir Word Belgesine Alan Grafiği Ekleme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir belgeye alan grafiği eklemeyi öğrenin. Seri verilerini ekleyin ve belgeyi grafikle birlikte kaydedin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/insert-area-chart/
---

Bu eğitim, bir belgeye alan grafiği eklemek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve belgenin nasıl kaydedileceğini gösterir.

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

 Ardından,`InsertChart` yöntemi`DocumentBuilder` belgeye bir alan grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Seri verilerini grafiğe ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte, karşılık gelen tarihler ve değerlerle birlikte beş veri noktası ekleyeceğiz.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## 4. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Bu, Aspose.Words for .NET kullanarak bir alan grafiği ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Alan Grafiği Ekleme için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesine alan grafiği eklemeyi öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak yeni bir belge oluşturabilir, alan grafiği ekleyebilir, seri verileri ekleyebilir ve belgeyi grafikle birlikte kaydedebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafiklerle Word Processing için güçlü bir API sağlar. Yalnızca birkaç satır kodla profesyonel görünümlü alan grafikleri oluşturabilir ve bunları gereksinimlerinize göre özelleştirebilirsiniz. Alan çizelgeleri, verilerin zaman veya kategoriler üzerindeki büyüklüğünü ve eğilimlerini görüntülemek için yaygın olarak kullanılır.

Aspose.Words for .NET'i kullanarak alan grafikleriyle belge oluşturma sürecini otomatikleştirebilir, manuel belge oluşturmada zamandan ve emekten tasarruf edebilirsiniz. Kitaplık, Word belgelerinizde görsel olarak çekici ve bilgilendirici grafikler oluşturmanıza olanak tanıyan çok çeşitli grafik türleri ve özelleştirme seçenekleri sunar.

### SSS

#### S1. Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin .NET uygulamalarında programlı olarak Word belgeleri oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir belge işleme kitaplığıdır. Grafikler, paragraflar, tablolar ve daha fazlası dahil olmak üzere belge öğeleriyle Kelime İşleme için kapsamlı bir API seti sağlar.

#### S2. Aspose.Words for .NET'i nasıl kurarım?
Aspose.Words for .NET'i kurmak için Visual Studio'daki NuGet paket yöneticisini kullanarak kütüphaneyi doğrudan projenize kurabilirsiniz. NuGet paket yöneticisinde "Aspose.Words" ifadesini aratın ve paketi kurun.

#### S3. Alan grafiğinin görünümünü özelleştirebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak alan grafiğinin görünümünün çeşitli yönlerini özelleştirebilirsiniz. Grafik başlığı, seri rengi, eksen etiketleri ve grafik alanı biçimlendirmesi gibi özellikleri değiştirebilirsiniz. Kitaplık, grafiğin görsel öğelerini kontrol etmek ve ihtiyaçlarınıza uygun özelleştirilmiş bir görünüm oluşturmak için zengin bir API seti sağlar.

#### S4. Alan grafiğine birden fazla seri ekleyebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak alan grafiğine birden fazla seri ekleyebilirsiniz. Her seri, grafikte çizilen bir dizi veri noktasını temsil eder. Farklı veri kümelerine sahip seriler ekleyebilir ve her seriyi adı, veri noktaları ve görünümü dahil olmak üzere ayrı ayrı özelleştirebilirsiniz.

#### S5. Alan grafiği eklenmiş belgeyi farklı formatlarda kaydedebilir miyim?
 Evet, Aspose.Words for .NET, eklenmiş alan grafiği içeren belgeyi DOCX, PDF, HTML ve daha fazlası gibi çeşitli biçimlerde kaydetmenize olanak tanır. Gereksinimlerinize göre istediğiniz çıktı formatını seçebilir ve`Save` yöntemi`Document` belgeyi kaydetmek için nesne. Eklenen alan grafiği kaydedilen belgede korunacaktır.

#### S6. Alan grafiğini ekledikten sonra verilerini ve görünümünü değiştirebilir miyim?
Evet, alan grafiğini belgeye ekledikten sonra Aspose.Words for .NET tarafından sağlanan API'leri kullanarak verilerini ve görünümünü değiştirebilirsiniz. Word belgelerinizde dinamik ve etkileşimli grafikler oluşturmak için seri verilerini güncelleyebilir, grafik türünü değiştirebilir, eksen özelliklerini özelleştirebilir ve biçimlendirme seçeneklerini uygulayabilirsiniz.