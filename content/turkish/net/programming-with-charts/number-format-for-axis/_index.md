---
title: Grafikteki Eksen İçin Sayı Formatı
linktitle: Grafikteki Eksen İçin Sayı Formatı
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir grafikteki eksen için sayı formatını nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/number-format-for-axis/
---

Bu eğitimde Aspose.Words for .NET'in grafikteki bir eksenin sayı formatını ayarlamak için nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve eksen etiketlerinin nasıl biçimlendirileceğini gösterir.

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

Grafiğe seri verileri ekleyin. Bu örnekte, karşılık gelen değerleriyle birlikte beş öğe ekleyeceğiz.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## 4. Adım: Eksen etiketlerini biçimlendirin

 Y ekseni etiketlerinin sayı biçimini ayarlamak için`AxisY` Grafiğin özelliğini seçin ve`NumberFormat.FormatCode` özelliği istenilen formata getirir. Bu örnekte, sayıları binlik ayırıcılarla görüntülemek için formatı "#,##0" olarak ayarladık.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## 5. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Bu, Aspose.Words for .NET kullanılarak eksen için sayı formatının ayarlanması işlemini tamamlar.

### Aspose.Words for .NET kullanan Eksen İçin Sayı Formatı için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir grafikteki eksen için sayı formatını nasıl ayarlayacağınızı öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodunu kullanarak, yeni bir belge oluşturabilir, sütun grafiği ekleyebilir, seri verileri ekleyebilir ve eksen etiketlerini, sayıları belirli bir biçimde görüntüleyecek şekilde biçimlendirebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafiklerin görünümünü özelleştirmek için güçlü özellikler sağlar. Eksen etiketleri için sayı biçimini ayarlayarak, ondalık basamaklar, binlik ayırıcılar, para birimi simgeleri ve daha fazlası gibi seçenekler de dahil olmak üzere sayıların nasıl görüntüleneceğini kontrol edebilirsiniz. Bu, sayısal verileri açık ve anlamlı bir şekilde sunmanıza olanak tanır.

Aspose.Words for .NET ile eksen etiketleri de dahil olmak üzere grafiğin çeşitli yönlerini biçimlendirme esnekliğine sahip olursunuz. Eksen için sayı formatını ayarlayarak tutarlılık sağlayabilir ve grafiğin okunabilirliğini geliştirebilir, böylece kullanıcıların temsil edilen değerleri yorumlamasını kolaylaştırabilirsiniz.

### SSS

#### S1. Grafikteki bir eksenin sayı biçimi nedir?
Grafikteki bir eksenin sayı biçimi, eksende görüntülenen sayısal değerlere uygulanan biçimlendirmeyi ifade eder. Ondalık basamaklar, binlik ayırıcılar, para birimi simgeleri, yüzde işaretleri ve daha fazlası gibi seçenekler de dahil olmak üzere sayıların nasıl sunulacağını kontrol etmenize olanak tanır. Sayı biçimini ayarlayarak, grafikteki sayısal verilerin görünümünü özel gereksinimlerinize uyacak şekilde özelleştirebilirsiniz.

#### Q2. Eksen etiketleri için sayı formatını nasıl ayarlayabilirim?
 Aspose.Words for .NET kullanarak bir grafikteki eksen etiketlerinin sayı formatını ayarlamak için şuraya erişebilirsiniz:`AxisY` Grafiğin özelliğini seçin ve`NumberFormat.FormatCode`özelliği istenilen format koduna ayarlayın. Biçim kodu, standart sayısal biçimlendirme kalıplarının sözdizimini takip eder ve sayıların nasıl görüntüleneceğini belirler. Örneğin, iki ondalık basamaklı ve binlik ayırıcılı sayıları görüntülemek için "#,##0.00" komutunu kullanabilirsiniz.

#### S3. X ekseni ve Y ekseni etiketleri için farklı sayı formatları ayarlayabilir miyim?
Evet, Aspose.Words for .NET'i kullanarak X ekseni ve Y ekseni etiketleri için farklı sayı formatları ayarlayabilirsiniz. İlgili eksene erişin (`AxisX` X ekseni için veya`AxisY` Grafiğin Y ekseni için) ve`NumberFormat.FormatCode` Her eksen için ayrı ayrı özellik. Bu, özel gereksinimlerinize göre her eksendeki etiketlere farklı sayı formatları uygulamanıza olanak tanır.

#### S4. Kullanabileceğim bazı yaygın sayı biçimi kodları nelerdir?
Aspose.Words for .NET, bir grafikteki eksen etiketlerini formatlamak için kullanabileceğiniz çok çeşitli sayı formatı kodlarını destekler. Bazı yaygın biçim kodları şunları içerir:

- `0` veya`#` - Sayıyı ondalık basamak olmadan görüntüler.
- `0.00` veya`#.00` - Sayıyı iki ondalık basamakla görüntüler.
- `#,##0` Sayıyı binlik ayırıcılarla görüntüler.
- `"€"0.00` - Sayıyı Euro para birimi simgesiyle ve iki ondalık basamakla görüntüler.
- `"%"0` - Sayıyı yüzde olarak görüntüler.

 Numara hakkında daha fazla bilgi bulabilirsiniz[format kodları](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) Aspose.Words for .NET'in API Referansında.

#### S5. Eksen etiketlerinin diğer özelliklerini özelleştirebilir miyim?
Evet, Aspose.Words for .NET eksen etiketlerinin görünümünü ve davranışını özelleştirmek için geniş bir özellik yelpazesi sunar. Sayı biçimine ek olarak yazı tipi, boyut, renk, yön, hizalama ve daha fazlası gibi özellikleri değiştirebilirsiniz. Bu, eksen etiketlerini istediğiniz stil ve sunum gereksinimlerinize uyacak şekilde tamamen özelleştirmenize olanak tanır.