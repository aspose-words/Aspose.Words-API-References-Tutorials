---
title: Word Belgesine Dağılım Grafiği Ekleme
linktitle: Word Belgesine Dağılım Grafiği Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word'e nasıl dağılım grafiği ekleyeceğinizi öğrenin. Görsel veri temsillerini belgelerinize entegre etmek için kolay adımlar.
type: docs
weight: 10
url: /tr/net/programming-with-charts/insert-scatter-chart/
---
## giriiş

Bu eğitimde, Word belgenize dağılım grafiği eklemek için Aspose.Words for .NET'ten nasıl yararlanacağınızı öğreneceksiniz. Dağılım grafikleri, iki değişkene dayalı veri noktalarını etkili bir şekilde görüntüleyebilen, belgelerinizi daha ilgi çekici ve bilgilendirici hale getiren güçlü görsel araçlardır.

## Önkoşullar

Aspose.Words for .NET ile dağılım grafikleri oluşturmaya başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

1.  Aspose.Words for .NET Kurulumu: Aspose.Words for .NET'i şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/words/net/).
   
2. Temel C# Bilgisi: C# programlama dili ve .NET çerçevesine aşinalık faydalı olacaktır.

## Ad Alanlarını İçe Aktar

Başlamak için C# projenize gerekli ad alanlarını içe aktarmanız gerekir:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
```

Şimdi Aspose.Words for .NET kullanarak Word belgenize dağılım grafiği ekleme sürecini inceleyelim:

## Adım 1: Document'ı ve DocumentBuilder'ı başlatın

 İlk olarak, yeni bir örneğini başlatın.`Document` sınıf ve`DocumentBuilder` belgenizi oluşturmaya başlamak için sınıf.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: Dağılım Tablosunu Ekleyin

 Kullan`InsertChart` yöntemi`DocumentBuilder` Belgeye bir dağılım grafiği eklemek için sınıf.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## 3. Adım: Grafiğe Veri Serisi Ekleme

Şimdi dağılım grafiğinize veri serileri ekleyin. Bu örnek, belirli veri noktalarına sahip bir serinin eklenmesini gösterir.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Adım 4: Belgeyi Kaydedin

 Son olarak, değiştirilen belgeyi kullanarak istediğiniz konuma kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Çözüm

Tebrikler! Aspose.Words for .NET'i kullanarak Word belgenize dağılım grafiğini nasıl ekleyeceğinizi başarıyla öğrendiniz. Dağılım grafikleri veri ilişkilerini görselleştirmek için mükemmel araçlardır ve Aspose.Words ile netliği ve anlayışı geliştirmek için bunları belgelerinizle zahmetsizce entegre edebilirsiniz.

## SSS'ler

### Aspose.Words'ü kullanarak dağılım grafiğinin görünümünü özelleştirebilir miyim?
Evet, Aspose.Words renkler, eksenler ve etiketler gibi grafik özelliklerinin kapsamlı şekilde kişiselleştirilmesine olanak tanır.

### Aspose.Words Microsoft Word'ün farklı sürümleriyle uyumlu mu?
Aspose.Words, Microsoft Word'ün çeşitli sürümlerini destekleyerek platformlar arasında uyumluluk sağlar.

### Aspose.Words diğer grafik türleri için destek sağlıyor mu?
Evet, Aspose.Words çubuk grafikler, çizgi grafikler ve pasta grafikler de dahil olmak üzere çok çeşitli grafik türlerini destekler.

### Dağılım grafiğindeki verileri programlı olarak dinamik olarak güncelleyebilir miyim?
Kesinlikle Aspose.Words API çağrılarını kullanarak grafik verilerini dinamik olarak güncelleyebilirsiniz.

### Aspose.Words için nereden daha fazla yardım veya destek alabilirim?
 Daha fazla yardım için şu adresi ziyaret edin:[Aspose.Words destek forumu](https://forum.aspose.com/c/words/8).