---
title: Word Belgesine Dağılım Grafiği Ekleme
linktitle: Word Belgesine Dağılım Grafiği Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir belgeye dağılım grafiğini nasıl ekleyeceğinizi öğrenin. X ve Y koordinatlarıyla seri verilerini ekleyin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/insert-scatter-chart/
---

Bu eğitimde Aspose.Words for .NET'in bir belgeye dağılım grafiği eklemek için nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve belgenin nasıl kaydedileceğini gösterir.

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

 Daha sonra şunu kullanın:`InsertChart` yöntemi`DocumentBuilder` Belgeye bir dağılım grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Grafiğe seri verilerini ekleyin

Grafiğe seri verileri ekleyin. Bu örnekte iki grup X ve Y koordinatı ekleyeceğiz.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## 4. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Bu, Aspose.Words for .NET kullanarak dağılım grafiği ekleme işlemini tamamlar.

### Aspose.Words for .NET kullanarak Dağılım Grafiği Ekleme için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesine dağılım grafiğinin nasıl ekleneceğini öğrendiniz. Adım adım kılavuzu takip ederek ve verilen kaynak kodunu kullanarak yeni bir belge oluşturabilir, dağılım grafiği ekleyebilir, X ve Y koordinatlarıyla seri verileri ekleyebilir ve belgeyi grafikle birlikte kaydedebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafiklerle Kelime İşleme için kapsamlı bir API sağlar. Dağılım grafikleri, iki sayısal değişkenli verileri görselleştirmek ve analiz etmek için kullanışlıdır. Aspose.Words for .NET ile X ve Y değerleri arasındaki ilişkiyi temsil eden dağılım grafiklerini kolayca oluşturabilir ve verilerdeki kalıpları veya eğilimleri tanımlayabilirsiniz.

Aspose.Words for .NET'i kullanarak, dağılım grafikleriyle belge oluşturma sürecini otomatikleştirebilir, manuel belge oluşturmada zamandan ve emekten tasarruf edebilirsiniz. Kitaplık, dağılım grafikleri de dahil olmak üzere çok çeşitli grafik türleri sunar ve grafiğin görünümünü ihtiyaçlarınıza göre uyarlamak için çeşitli özelleştirme seçenekleri sunar.

### SSS

#### S1. Dağılım grafiği nedir?
Dağılım grafiği, iki sayısal değişken arasındaki ilişkiyi görüntüleyen bir grafik türüdür. Bir değişkenin X ekseninde ve diğer değişkenin Y ekseninde temsil edildiği bir koordinat ızgarası üzerinde çizilen bir dizi noktadan oluşur. Dağılım grafikleri, iki veri noktası kümesi arasındaki kalıpları, korelasyonları veya eğilimleri tanımlamak için kullanılır.

#### Q2. Dağılım grafiğine birden fazla seri ekleyebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak dağılım grafiğine birden fazla seri ekleyebilirsiniz. Her seri, ilgili X ve Y koordinatlarıyla birlikte bir dizi veri noktasını temsil eder. Birden fazla seri ekleyerek aynı dağılım grafiğindeki farklı veri kümelerini karşılaştırıp analiz edebilir, verilerinizin kapsamlı bir görünümünü sağlayabilirsiniz.

#### S3. Dağılım grafiğinin görünümünü özelleştirebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak dağılım grafiğinin görünümünün çeşitli yönlerini özelleştirebilirsiniz. Seri rengi, işaretçi şekli, eksen etiketleri ve grafik alanı formatlaması gibi özellikleri değiştirebilirsiniz. Kitaplık, grafiğin görsel öğelerini kontrol etmek ve ihtiyaçlarınıza uygun özelleştirilmiş bir görünüm oluşturmak için zengin bir API seti sağlar.

#### S4. Dağılım grafiğinin eklendiği belgeyi farklı formatlarda kaydedebilir miyim?
Evet, Aspose.Words for .NET, belgeyi eklenen dağılım grafiğiyle birlikte DOCX, PDF, HTML ve daha fazlası gibi çeşitli formatlarda kaydetmenize olanak tanır. Gereksinimlerinize göre istediğiniz çıktı formatını seçebilir ve`Save` yöntemi`Document` Belgeyi kaydetmek için nesne. Eklenen dağılım grafiği kaydedilen belgede korunacaktır.

#### S5. Dağılım grafiğini ekledikten sonra verilerini ve görünümünü değiştirebilir miyim?
Evet, dağılım grafiğini belgeye ekledikten sonra Aspose.Words for .NET tarafından sağlanan API'leri kullanarak verilerini ve görünümünü değiştirebilirsiniz. Seri verilerini yeni X ve Y koordinatlarıyla güncelleyebilir, işaretçi şekillerini ve renklerini değiştirebilir, eksen özelliklerini özelleştirebilir ve Word belgelerinizde dinamik ve etkileşimli grafikler oluşturmak için biçimlendirme seçeneklerini uygulayabilirsiniz.