---
title: Grafikteki Eksen İçin Sayı Biçimi
linktitle: Grafikteki Eksen İçin Sayı Biçimi
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir grafikte bir eksen için sayı biçimini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/number-format-for-axis/
---

Bu öğretici, Aspose.Words for .NET'in grafikteki bir eksen için sayı formatını ayarlamak üzere nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, seri verilerinin nasıl ekleneceğini ve eksen etiketlerinin nasıl biçimlendirileceğini gösterir.

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

Grafiğe seri verileri ekleyin. Bu örnekte, karşılık gelen değerleri ile beş öğe ekleyeceğiz.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## 4. Adım: Eksen etiketlerini biçimlendirin

 Y ekseni etiketlerinin sayı biçimini ayarlamak için şuraya erişin:`AxisY` grafiğin özelliğini ayarlayın ve`NumberFormat.FormatCode` özelliğini istediğiniz biçime getirin. Bu örnekte, sayıları binlik ayırıcılarla görüntülemek için biçimi "#,##0" olarak ayarladık.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## 5. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Bu, Aspose.Words for .NET kullanılarak eksen için sayı biçimini ayarlama uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Number Format For Axis için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
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

Bu öğreticide, Aspose.Words for .NET kullanarak bir grafikte bir eksen için sayı biçimini nasıl ayarlayacağınızı öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak yeni bir belge oluşturabilir, sütun grafiği ekleyebilir, seri verileri ekleyebilir ve sayıları belirli bir biçimde görüntülemek için eksen etiketlerini biçimlendirebilirsiniz.

Aspose.Words for .NET, Word belgelerindeki grafiklerin görünümünü özelleştirmek için güçlü özellikler sağlar. Eksen etiketleri için sayı biçimini ayarlayarak, ondalık basamaklar, binlik ayırıcılar, para birimi simgeleri ve daha fazlası gibi seçenekler de dahil olmak üzere sayıların nasıl görüntüleneceğini kontrol edebilirsiniz. Bu, sayısal verileri açık ve anlamlı bir şekilde sunmanıza olanak tanır.

Aspose.Words for .NET ile eksen etiketleri de dahil olmak üzere grafiğin çeşitli yönlerini biçimlendirme esnekliğine sahipsiniz. Eksen için sayı biçimini ayarlayarak tutarlılığı sağlayabilir ve grafiğin okunabilirliğini geliştirerek kullanıcıların temsil edilen değerleri yorumlamasını kolaylaştırabilirsiniz.

### SSS

#### S1. Grafikteki bir eksenin sayı biçimi nedir?
Grafikteki bir eksen için sayı biçimi, eksende görüntülenen sayısal değerlere uygulanan biçimlendirmeyi ifade eder. Ondalık basamaklar, binlik ayırıcılar, para birimi simgeleri, yüzde işaretleri ve daha fazlası gibi seçenekler de dahil olmak üzere sayıların nasıl sunulacağını kontrol etmenizi sağlar. Sayı biçimini ayarlayarak, grafikteki sayısal verilerin görünümünü özel gereksinimlerinize uyacak şekilde özelleştirebilirsiniz.

#### S2. Eksen etiketleri için sayı biçimini nasıl ayarlayabilirim?
 Aspose.Words for .NET kullanarak bir tablodaki eksen etiketlerinin sayı biçimini ayarlamak için`AxisY` grafiğin özelliğini ayarlayın ve`NumberFormat.FormatCode`özelliğini istediğiniz format koduna değiştirin. Biçim kodu, standart sayısal biçimlendirme kalıplarının sözdizimini izler ve sayıların nasıl görüntüleneceğini belirler. Örneğin, sayıları iki ondalık basamaklı ve binlik ayırıcılarla görüntülemek için "#,##0.00" kullanabilirsiniz.

#### S3. X ekseni ve Y ekseni etiketleri için farklı sayı biçimleri ayarlayabilir miyim?
Evet, Aspose.Words for .NET'i kullanarak X ekseni ve Y ekseni etiketleri için farklı sayı biçimleri ayarlayabilirsiniz. İlgili eksene erişin (`AxisX` X ekseni için veya`AxisY` grafiğin Y ekseni için) ve değiştirin`NumberFormat.FormatCode` her eksen için ayrı ayrı özellik. Bu, özel gereksinimlerinize göre her eksendeki etiketlere farklı sayı biçimleri uygulamanıza olanak tanır.

#### S4. Kullanabileceğim bazı yaygın sayı biçimi kodları nelerdir?
Aspose.Words for .NET, bir grafikteki eksen etiketlerini formatlamak için kullanabileceğiniz çok çeşitli sayı formatı kodlarını destekler. Bazı yaygın format kodları şunları içerir:

- `0` veya`#` - Sayıyı ondalık basamak olmadan görüntüler.
- `0.00` veya`#.00` - Sayıyı iki ondalık basamakla görüntüler.
- `#,##0` Sayıyı binlik ayırıcılarla görüntüler.
- `"€"0.00` - Sayıyı Euro para birimi simgesi ve iki ondalık basamakla görüntüler.
- `"%"0` - Sayıyı yüzde olarak görüntüler.

 Numara hakkında daha fazla bilgi bulabilirsiniz.[biçim kodları](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) Aspose.Words for .NET'in API Referansında.

#### S5. Eksen etiketlerinin diğer özelliklerini özelleştirebilir miyim?
Evet, Aspose.Words for .NET, eksen etiketlerinin görünümünü ve davranışını özelleştirmek için çok çeşitli özellikler sunar. Sayı biçimine ek olarak, yazı tipi, boyut, renk, yön, hizalama ve daha fazlası gibi özellikleri değiştirebilirsiniz. Bu, eksen etiketlerini istediğiniz tarza ve sunum gereksinimlerinize uyacak şekilde tamamen özelleştirmenize olanak tanır.