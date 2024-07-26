---
title: Grafikteki Veri Etiketi Sayısını Biçimlendir
linktitle: Grafikteki Veri Etiketi Sayısını Biçimlendir
second_title: Aspose.Words Belge İşleme API'si
description: Bu adım adım kılavuzla Aspose.Words for .NET kullanarak grafiklerdeki veri etiketlerini nasıl formatlayacağınızı öğrenin. Word belgelerinizi zahmetsizce geliştirin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/format-number-of-data-label/
---
## giriiş

İlgi çekici ve bilgilendirici belgeler oluşturmak genellikle iyi biçimlendirilmiş veri etiketlerine sahip grafiklerin eklenmesini içerir. Word belgelerinizi gelişmiş grafiklerle geliştirmek isteyen bir .NET geliştiricisiyseniz, Aspose.Words for .NET bunu başarmanıza yardımcı olacak muhteşem bir kütüphanedir. Bu eğitim, Aspose.Words for .NET kullanarak bir grafikteki sayı etiketlerini biçimlendirme sürecinde size adım adım yol gösterecektir.

## Önkoşullar

Koda dalmadan önce yerine getirmeniz gereken birkaç önkoşul vardır:

-  Aspose.Words for .NET: Aspose.Words for .NET kütüphanesinin kurulu olduğundan emin olun. Henüz yüklemediyseniz, yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Bir .NET geliştirme ortamı kurmuş olmalısınız. Visual Studio şiddetle tavsiye edilir.
- Temel C# Bilgisi: Bu eğitim C# kodunu yazmayı ve anlamayı içerdiğinden, C# programlamaya aşinalık önemlidir.
-  Geçici Lisans: Aspose.Words'ü herhangi bir sınırlama olmaksızın kullanmak için,[geçici lisans](https://purchase.aspose.com/temporary-license/).

Şimdi bir grafikteki sayı etiketlerini biçimlendirmenin adım adım sürecine dalalım.

## Ad Alanlarını İçe Aktar

Öncelikle Aspose.Words for .NET ile çalışmak için gerekli ad alanlarını içe aktarmamız gerekiyor. C# dosyanızın en üstüne aşağıdaki satırları ekleyin:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## 1. Adım: Belge Dizininizi Kurun

Word belgenizi düzenlemeye başlamadan önce belgenizin kaydedileceği dizini belirtmeniz gerekir. Bu daha sonra kaydetme işlemi için gereklidir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

## Adım 2: Document'ı ve DocumentBuilder'ı başlatın

 Bir sonraki adım yeni bir başlangıç başlatmaktır`Document` ve bir`DocumentBuilder` .`DocumentBuilder` belge içeriğini oluşturmamızı sağlayan yardımcı sınıftır.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Belgeye Grafik Ekleme

 Şimdi belgeye şunu kullanarak bir grafik ekleyelim:`DocumentBuilder`. Bu eğitimde örnek olarak Çizgi grafiği kullanacağız.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

Burada belirli genişlik ve yüksekliğe sahip bir Çizgi grafiği ekliyoruz ve grafiğin başlığını belirliyoruz.

## Adım 4: Varsayılan Seriyi Temizleyin ve Yeni Seriyi Ekleyin

Varsayılan olarak grafikte önceden oluşturulmuş bazı seriler bulunur. Bunları temizleyip belirli veri noktalarına sahip kendi serilerimizi eklememiz gerekiyor.

```csharp
// Varsayılan oluşturulan seriyi silin.
chart.Series.Clear();

// Özel veri noktalarına sahip yeni seriler ekleyin.
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
	new string[] { "Category 1", "Category 2", "Category 3" }, 
	new double[] { 2.5, 1.5, 3.5 });
```

## 5. Adım: Veri Etiketlerini Etkinleştirin

Veri etiketlerini grafikte görüntülemek için bunları serimiz için etkinleştirmemiz gerekir.

```csharp
series1.HasDataLabels = true;
series1.DataLabels.ShowValue = true;
```

## Adım 6: Veri Etiketlerini Biçimlendirin

Bu eğitimin özü veri etiketlerinin biçimlendirilmesidir. Her veri etiketine ayrı ayrı farklı sayı formatları uygulayabiliyoruz.

```csharp
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00"; // Para birimi biçimi
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy"; // Tarih formatı
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%"; // Yüzde biçimi
```

 Ek olarak, bir veri etiketinin biçimini bir kaynak hücreye bağlayabilirsiniz. Bağlandığında,`NumberFormat` genel olarak sıfırlanacak ve kaynak hücreden devralınacak.

```csharp
series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
```

## Adım 7: Belgeyi Kaydedin

Son olarak belgeyi belirtilen dizine kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Bu, belgenizi belirtilen adla kaydeder ve biçimlendirilmiş veri etiketlerine sahip grafiğinizin korunmasını sağlar.

## Çözüm

Aspose.Words for .NET kullanarak bir grafikteki veri etiketlerini biçimlendirmek, Word belgelerinizin okunabilirliğini ve profesyonelliğini büyük ölçüde artırabilir. Bu adım adım kılavuzu izleyerek artık bir grafik oluşturabilir, veri serileri ekleyebilir ve veri etiketlerini ihtiyaçlarınızı karşılayacak şekilde biçimlendirebilirsiniz. Aspose.Words for .NET, Word belgelerinin kapsamlı şekilde kişiselleştirilmesine ve otomasyonuna olanak tanıyan güçlü bir araçtır ve bu da onu .NET geliştiricileri için paha biçilmez bir varlık haline getirir.

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, Word belgelerini C# kullanarak programlı bir şekilde oluşturmak, değiştirmek ve dönüştürmek için kullanılan güçlü bir kütüphanedir.

### Aspose.Words for .NET ile diğer grafik türlerini formatlayabilir miyim?
Evet, Aspose.Words for .NET çubuk, sütun, pasta ve daha fazlasını içeren çeşitli grafik türlerini destekler.

### Aspose.Words for .NET için nasıl geçici lisans alabilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).

### Veri etiketlerini Excel'deki kaynak hücrelere bağlamak mümkün müdür?
Evet, veri etiketlerini kaynak hücrelere bağlayarak sayı biçiminin kaynak hücreden devralınmasına olanak tanıyabilirsiniz.

### Aspose.Words for .NET için daha ayrıntılı belgeleri nerede bulabilirim?
 Kapsamlı belgeler bulabilirsiniz[Burada](https://reference.aspose.com/words/net/).
