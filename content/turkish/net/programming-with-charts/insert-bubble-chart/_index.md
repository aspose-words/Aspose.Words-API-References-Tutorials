---
title: Kabarcık Grafiğini Word Belgesine Ekle
linktitle: Kabarcık Grafiğini Word Belgesine Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir belgeye nasıl kabarcık grafiği ekleyeceğinizi öğrenin. X, Y ve kabarcık boyutu değerlerine sahip seri verilerini ekleyin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/insert-bubble-chart/
---

Bu eğitimde, bir belgeye kabarcık grafiği eklemek için Aspose.Words for .NET'in nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve belgenin nasıl kaydedileceğini gösterir.

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

 Daha sonra şunu kullanın:`InsertChart` yöntemi`DocumentBuilder` Belgeye bir kabarcık grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Grafiğe seri verilerini ekleyin

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

Bu, Aspose.Words for .NET kullanarak kabarcık grafiği ekleme işlemini tamamlar.

### Aspose.Words for .NET kullanarak Kabarcık Grafiği Ekleme için örnek kaynak kodu 

```csharp
// Belge dizininizin yolu
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

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesine kabarcık grafiğinin nasıl ekleneceğini öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak yeni bir belge oluşturabilir, kabarcık grafiği ekleyebilir, seri verileri ekleyebilir ve belgeyi grafikle birlikte kaydedebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafiklerle Kelime İşleme için güçlü bir API sağlar. Kabarcık grafikleri, her veri noktasının X ve Y koordinatlarına ve boyut değerine sahip bir kabarcıkla temsil edildiği üç boyutlu verileri görselleştirmek için idealdir. Aspose.Words for .NET ile verilerinizin görsel sunumunu geliştiren dinamik ve bilgilendirici kabarcık grafikleri oluşturabilirsiniz.

Aspose.Words for .NET'i kullanarak kabarcık grafikleriyle belge oluşturma sürecini otomatikleştirebilir, manuel belge oluşturmada zamandan ve emekten tasarruf edebilirsiniz. Kitaplık, Word belgelerinizde görsel olarak çekici ve veri açısından zengin grafikler oluşturmanıza olanak tanıyan çok çeşitli grafik türleri ve özelleştirme seçenekleri sunar.

### SSS

#### S1. Kabarcık grafiği nedir?
Kabarcık grafiği, kabarcıklar veya küreler kullanarak üç boyutlu verileri görüntüleyen bir grafik türüdür. Her veri noktası bir baloncukla temsil edilir; burada X ve Y koordinatları balonun grafikteki konumunu belirler ve balonun boyutu verinin üçüncü boyutunu temsil eder. Kabarcık grafikleri, birden çok değişken arasındaki ilişkileri ve kalıpları görselleştirmek için kullanışlıdır.

#### Q2. Kabarcık grafiğine birden fazla seri ekleyebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak kabarcık grafiğine birden fazla seri ekleyebilirsiniz. Her seri, ilgili X, Y ve kabarcık boyutu değerleriyle birlikte bir dizi veri noktasını temsil eder. Birden fazla seri ekleyerek aynı grafikteki farklı veri kümelerini karşılaştırıp analiz edebilir, verilerinizin kapsamlı bir görünümünü sağlayabilirsiniz.

#### S3. Kabarcık grafiğinin görünümünü özelleştirebilir miyim?
Evet, Aspose.Words for .NET'i kullanarak kabarcık grafiğinin görünümünün çeşitli yönlerini özelleştirebilirsiniz. Seri rengi, kabarcık boyutu, eksen etiketleri ve grafik alanı biçimlendirmesi gibi özellikleri değiştirebilirsiniz. Kitaplık, grafiğin görsel öğelerini kontrol etmek ve ihtiyaçlarınıza uygun özelleştirilmiş bir görünüm oluşturmak için zengin bir API seti sağlar.

#### S4. Kabarcık grafiğinin eklendiği belgeyi farklı formatlarda kaydedebilir miyim?
 Evet, Aspose.Words for .NET, belgeyi kabarcık grafiği eklenmiş olarak DOCX, PDF, HTML ve daha fazlası gibi çeşitli formatlarda kaydetmenize olanak tanır. Gereksinimlerinize göre istediğiniz çıktı formatını seçebilir ve`Save` yöntemi`Document` Belgeyi kaydetmek için nesne. Eklenen kabarcık grafiği kaydedilen belgede korunacaktır.

#### S5. Kabarcık grafiğini ekledikten sonra verilerini ve görünümünü değiştirebilir miyim?
Evet, kabarcık grafiğini belgeye ekledikten sonra Aspose.Words for .NET tarafından sağlanan API'leri kullanarak verilerini ve görünümünü değiştirebilirsiniz. Word belgelerinizde dinamik ve etkileşimli grafikler oluşturmak için seri verilerini güncelleyebilir, kabarcık boyutunu değiştirebilir, eksen özelliklerini özelleştirebilir ve biçimlendirme seçeneklerini uygulayabilirsiniz.