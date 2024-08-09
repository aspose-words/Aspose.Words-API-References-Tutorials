---
title: Grafikteki Eksen İçin Sayı Formatı
linktitle: Grafikteki Eksen İçin Sayı Formatı
second_title: Aspose.Words Belge İşleme API'si
description: Bu adım adım kılavuzla Aspose.Words for .NET kullanarak grafik eksen numaralarını nasıl formatlayacağınızı öğrenin. Belgenizin okunabilirliğini ve profesyonelliğini zahmetsizce geliştirin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/number-format-for-axis/
---
## giriiş

Selam! Hiç belgelerinizdeki grafiklerle çalıştınız mı ve ekseninizdeki sayıları daha profesyonel görünecek şekilde biçimlendirmeyi dilediniz mi? Şanslısın! Bu eğitimde Aspose.Words for .NET kullanarak tam da bunu nasıl başarabileceğinizi derinlemesine inceleyeceğiz. Bu güçlü kitaplık, Word belgelerini çok kolay bir şekilde işlemenizi sağlar. Ve bugün, bu grafik eksenlerine özel sayı formatlarıyla bir görünüm kazandırmaya odaklanıyoruz.

## Önkoşullar

Başlamadan önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım. İşte hızlı bir kontrol listesi:

-  Aspose.Words for .NET: Yüklediğinizden emin olun. Değilse, yapabilirsiniz[buradan indir](https://releases.aspose.com/words/net/).
- .NET Framework: Uyumlu bir .NET framework'ün kurulu olduğundan emin olun.
- Geliştirme Ortamı: Visual Studio gibi bir IDE mükemmel çalışacaktır.
- Temel C# Bilgisi: Bu, kodlama örneklerini takip etmenize yardımcı olacaktır.

## Ad Alanlarını İçe Aktar

Öncelikle projenize gerekli ad alanlarını içe aktarmanız gerekir. Bu, bir evin inşasından önce temelin atılması gibidir. Kod dosyanızın en üstüne aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Reporting;
```

Şimdi süreci basit, takip edilmesi kolay adımlara ayıralım.

## Adım 1: Belgeyi Ayarlama

Başlık: Belgenizi Başlatın

Öncelikle yeni bir belge ve belge oluşturucu oluşturmanız gerekir. Bu adımı, şaheserinize başlamadan önce tuvalinizi ve fırçanızı hazırlamak olarak düşünün.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Burada,`dataDir` son dosyayı kaydedeceğiniz belge dizininizin yoludur.`Document`Ve`DocumentBuilder` Aspose.Words'ün Word belgelerini oluşturmanıza ve değiştirmenize yardımcı olan sınıflarıdır.

## Adım 2: Grafik Ekleme

Başlık: Belgenize Grafik Ekleme

Daha sonra belgenize bir grafik ekleyelim. İşte sihir burada başlıyor. Boş tuvalimiz görevi görecek bir sütun grafiği ekleyeceğiz.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

`InsertChart` yöntemi, belgeye belirtilen türde (bu durumda Sütun) ve boyutlarda bir grafik ekler.

## Adım 3: Grafik Serisini Özelleştirme

Başlık: Grafiğinizi Verilerle Doldurun

Şimdi grafiğimize bazı veriler eklememiz gerekiyor. Bu adım, grafiğinizi anlamlı bilgilerle doldurmaya benzer.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

 Burada beş veri noktasına sahip "Aspose Series 1" adında yeni bir seri ekliyoruz.`Series.Clear` yöntemi, yeni serimizi eklemeden önce önceden var olan tüm verilerin kaldırılmasını sağlar.

## Adım 4: Eksen Numaralarını Formatlama

Başlık: Eksen Numaralarınızı Güzelleştirin

Son olarak Y eksenindeki sayıları daha okunabilir hale getirecek şekilde biçimlendirelim. Bu, sanat eserinize son rötuşları yapmak gibidir.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

`FormatCode` özelliği eksendeki sayılar için özel bir format ayarlamanıza olanak tanır. Bu örnekte,`#,##0`büyük sayıların binler için virgülle görüntülenmesini sağlar.

## Adım 5: Belgeyi Kaydetme

Başlık: Başyapıtınızı Kaydedin

Artık her şey ayarlandığına göre belgenizi kaydetme zamanı geldi. Bu adım, çalışmanızın büyük ortaya çıkışıdır.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

 Burada,`Save` yöntem belgeyi dosya adıyla belirtilen yola kaydeder`WorkingWithCharts.NumberFormatForAxis.docx`.

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak grafiğinizin Y eksenindeki sayıları başarıyla biçimlendirdiniz. Bu yalnızca grafiklerinizin daha profesyonel görünmesini sağlamakla kalmaz, aynı zamanda okunabilirliği de artırır. Aspose.Words, programlı olarak çarpıcı Word belgeleri oluşturmanıza yardımcı olabilecek çok sayıda özellik sunar. Öyleyse neden daha fazlasını keşfedip başka neler yapabileceğinizi görmüyorsunuz?

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin Word belgelerini programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır.

### Grafiğin eksen numaralarının yanı sıra diğer yönlerini de biçimlendirebilir miyim?
Kesinlikle! Aspose.Words for .NET, başlıkları, etiketleri biçimlendirmenize ve hatta grafiğin görünümünü özelleştirmenize olanak tanır.

### Aspose.Words for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, alabilirsiniz[ücretsiz deneme burada](https://releases.aspose.com/).

### Aspose.Words for .NET'i C#'ın yanı sıra diğer .NET dilleriyle de kullanabilir miyim?
Evet, Aspose.Words for .NET, VB.NET ve F# dahil tüm .NET dilleriyle uyumludur.

### Daha ayrıntılı belgeleri nerede bulabilirim?
 Ayrıntılı belgeler şu adreste mevcuttur:[Aspose.Words for .NET dokümantasyon sayfası](https://reference.aspose.com/words/net/).
