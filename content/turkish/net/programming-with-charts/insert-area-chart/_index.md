---
title: Alan Grafiğini Bir Word Belgesine Ekleme
linktitle: Alan Grafiğini Bir Word Belgesine Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir belgeye nasıl alan grafiği ekleyeceğinizi öğrenin. Seri verilerini ekleyin ve belgeyi grafikle birlikte kaydedin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/insert-area-chart/
---
## giriiş

Aspose.Words for .NET kullanarak bir Word belgesine alan grafiğinin nasıl ekleneceğiyle ilgili bu adım adım kılavuza hoş geldiniz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu eğitim size Word belgelerinizde çarpıcı ve bilgilendirici alan grafikleri oluşturmak için bilmeniz gereken her şeyi anlatacaktır. Önkoşulları ele alacağız, size gerekli ad alanlarını nasıl içe aktaracağınızı göstereceğiz ve açık, takip edilmesi kolay talimatlarla sürecin her adımında size yol göstereceğiz.

## Önkoşullar

Başlamadan önce, başlamak için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  Aspose.Words for .NET: Aspose.Words for .NET'in kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/words/net/).
2. .NET Framework: Makinenizde .NET Framework'ün kurulu olduğundan emin olun.
3. IDE: Kodunuzu yazmak ve yürütmek için Visual Studio gibi bir Tümleşik Geliştirme Ortamı (IDE).
4. Temel C# Bilgisi: C# programlamanın temel bir anlayışı faydalı olacaktır.

Bu önkoşulları yerine getirdikten sonra Word belgelerinizde güzel alan grafikleri oluşturmaya hazırsınız.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktaralım. Bu ad alanları Aspose.Words for .NET'te Word belgeleri ve grafikleriyle çalışmak için gereken sınıfları ve yöntemleri sağlar.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System;
```

Artık gerekli ad alanlarını içe aktardığımıza göre, belgemizi oluşturmaya ve adım adım alan grafiği eklemeye geçelim.

## 1. Adım: Yeni Bir Word Belgesi Oluşturun

Yeni bir Word belgesi oluşturarak başlayalım. Bu, alan grafiğimizi ekleyeceğimiz temel olacaktır.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

 Bu adımda yeni bir başlangıç başlatıyoruz.`Document` Word belgemizi temsil eden nesne.

## Adım 2: Grafik Eklemek için DocumentBuilder'ı kullanın

 Daha sonra şunu kullanacağız:`DocumentBuilder` Belgemize bir alan grafiği eklemek için sınıf.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
```

 Burada bir oluşturuyoruz`DocumentBuilder` nesneyi seçin ve bunu belgemize belirli boyutlarda (432x252) bir alan grafiği eklemek için kullanın.

## 3. Adım: Grafik Nesnesine Erişin

 Grafiği ekledikten sonra şuraya erişmemiz gerekiyor:`Chart` alan grafiğimizi özelleştirmek için nesneyi seçin.

```csharp
Chart chart = shape.Chart;
```

 Bu kod satırı,`Chart` az önce eklediğimiz şekildeki nesneyi seçin.

## Adım 4: Seri Verilerini Grafiğe Ekleme

Şimdi grafiğimize bazı veriler eklemenin zamanı geldi. Tarihleri ve karşılık gelen değerleri içeren bir seri ekleyeceğiz.

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

Bu adımda, bir dizi tarih ve karşılık gelen değerleri içeren "Aspose Series 1" adlı bir seri ekliyoruz.

## Adım 5: Belgeyi Kaydedin

Son olarak belgemizi eklenen alan grafiğiyle kaydedeceğiz.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Bu kod satırı, belgeyi verilen dosya adıyla belirtilen dizine kaydeder.

## Çözüm

Tebrikler! Aspose.Words for .NET'i kullanarak bir Word belgesine başarıyla alan grafiği eklediniz. Bu kılavuz, ortamınızı ayarlamaktan son belgeyi kaydetmeye kadar her adımda size yol gösterecektir. Aspose.Words for .NET ile Word belgelerinizde çok çeşitli grafikler ve diğer karmaşık öğeler oluşturabilir, raporlarınızı ve sunumlarınızı daha dinamik ve bilgilendirici hale getirebilirsiniz.

## SSS'ler

### Aspose.Words for .NET'i diğer .NET dilleriyle kullanabilir miyim?
Evet, Aspose.Words for .NET, VB.NET gibi diğer .NET dillerini destekler.

### Grafiğin görünümünü özelleştirmek mümkün mü?
Kesinlikle! Aspose.Words for .NET, grafiklerinizin görünümünü özelleştirmeniz için kapsamlı seçenekler sunar.

### Tek bir Word belgesine birden fazla grafik ekleyebilir miyim?
Evet, tek bir Word belgesine istediğiniz kadar grafik ekleyebilirsiniz.

### Aspose.Words for .NET diğer grafik türlerini destekliyor mu?
Evet, Aspose.Words for .NET çubuk, çizgi, pasta ve daha fazlasını içeren çeşitli grafik türlerini destekler.

### Aspose.Words for .NET için nereden geçici lisans alabilirim?
 adresinden geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).