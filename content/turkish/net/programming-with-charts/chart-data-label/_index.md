---
title: Grafik Veri Etiketini Özelleştir
linktitle: Grafik Veri Etiketini Özelleştir
second_title: Aspose.Words Belge İşleme API'si
description: Adım adım kılavuzdan Aspose.Words for .NET kullanarak grafik veri etiketlerini nasıl özelleştireceğinizi öğrenin. .NET geliştiricileri için mükemmel.
type: docs
weight: 10
url: /tr/net/programming-with-charts/chart-data-label/
---
## giriiş

.NET uygulamalarınızı dinamik ve özelleştirilmiş belge işleme yetenekleriyle geliştirmek mi istiyorsunuz? Aspose.Words for .NET tam da aradığınız cevap olabilir! Bu kılavuzda, Word belgelerini oluşturmaya, değiştirmeye ve dönüştürmeye yönelik güçlü bir kütüphane olan Aspose.Words for .NET'i kullanarak grafik veri etiketlerini özelleştirmeye derinlemesine bakacağız. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu eğitim size her adımda yol gösterecek ve bu aracı nasıl etkili bir şekilde kullanacağınızı anlamanızı sağlayacaktır.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Visual Studio: Visual Studio 2019 veya üstünü yükleyin.
2. .NET Framework: .NET Framework 4.0 veya sonraki bir sürüme sahip olduğunuzdan emin olun.
3.  Aspose.Words for .NET: Aspose.Words for .NET'i şu adresten indirip yükleyin:[indirme bağlantısı](https://releases.aspose.com/words/net/).
4. Temel C# Bilgisi: C# programlamaya aşinalık esastır.
5.  Geçerli Bir Lisans: Alın[geçici lisans](https://purchase.aspose.com/temporary-license/) veya şuradan bir tane satın alın:[bağlantı satın al](https://purchase.aspose.com/buy).

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını C# projenize aktarmanız gerekir. Bu adım çok önemlidir çünkü Aspose.Words tarafından sağlanan tüm sınıflara ve yöntemlere erişebilmenizi sağlar.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Charts;
```

## Adım 1: Document'ı ve DocumentBuilder'ı başlatın

Word belgelerini oluşturmak ve değiştirmek için öncelikle bir örneğini başlatmamız gerekir.`Document` sınıf ve bir`DocumentBuilder` nesne.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Açıklama

- Document doc: Document sınıfının yeni bir örneğini oluşturur.
- DocumentBuilder oluşturucu: DocumentBuilder, Document nesnesine içerik eklenmesine yardımcı olur.

## 2. Adım: Grafik Ekleme

 Daha sonra, belgeye şunu kullanarak bir çubuk grafik ekleyeceğiz:`DocumentBuilder` nesne.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

### Açıklama

- Şekil şekli: Grafiği belgedeki bir şekil olarak temsil eder.
- builder.InsertChart(ChartType.Bar, 432, 252): Belirtilen boyutlara sahip bir çubuk grafik ekler.

## 3. Adım: Grafik Serisine Erişin

Veri etiketlerini özelleştirmek için öncelikle grafikteki serilere erişmemiz gerekiyor.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
```

### Açıklama

- ChartSeries series0: Grafiğin özelleştireceğimiz ilk serisini alır.

## 4. Adım: Veri Etiketlerini Özelleştirin

Veri etiketleri çeşitli bilgileri gösterecek şekilde özelleştirilebilir. Etiketleri, kategori adını ve yüzdeyi gizlerken açıklama anahtarını, seri adını ve değerini gösterecek şekilde yapılandıracağız.

```csharp
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

### Açıklama

- ChartDataLabelCollection labels: Serinin veri etiketlerine erişir.
- labels.ShowLegendKey: Açıklama anahtarını görüntüler.
- labels.ShowLeaderLines: Veri noktalarının çok dışına konumlandırılmış veri etiketleri için öncü çizgileri gösterir.
- labels.ShowCategoryName: Kategori adını gizler.
- labels.ShowPercentage: Yüzde değerini gizler.
- labels.ShowSeriesName: Seri adını görüntüler.
- labels.ShowValue: Veri noktalarının değerini görüntüler.
- labels.Separator: Veri etiketleri için ayırıcıyı ayarlar.

## Adım 5: Belgeyi Kaydedin

Son olarak belgeyi belirtilen dizine kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Açıklama

- doc.Save: Belgeyi belirtilen adla belirtilen dizine kaydeder.

## Çözüm

 Tebrikler! Aspose.Words for .NET'i kullanarak grafik veri etiketlerini başarıyla özelleştirdiniz. Bu kitaplık, Word belgelerinin programlı olarak işlenmesi için sağlam bir çözüm sunarak geliştiricilerin karmaşık ve dinamik belge işleme uygulamaları oluşturmasını kolaylaştırır. Dalış[dokümantasyon](https://reference.aspose.com/words/net/) Daha fazla özellik ve yeteneği keşfetmek için.

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin Word belgelerini programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir belge işleme kitaplığıdır.

### Aspose.Words for .NET'i nasıl yüklerim?
 adresinden indirip kurabilirsiniz.[indirme bağlantısı](https://releases.aspose.com/words/net/). Sağlanan kurulum talimatlarını izleyin.

### Aspose.Words for .NET'i ücretsiz deneyebilir miyim?
 Evet, alabilirsiniz[ücretsiz deneme](https://releases.aspose.com/) veya bir[geçici lisans](https://purchase.aspose.com/temporary-license/)Ürünü değerlendirmek için.

### Aspose.Words for .NET, .NET Core ile uyumlu mu?
Evet, Aspose.Words for .NET; .NET Core, .NET Standard ve .NET Framework ile uyumludur.

### Aspose.Words for .NET için nereden destek alabilirim?
 Ziyaret edebilirsiniz[destek forumu](https://forum.aspose.com/c/words/8) Aspose topluluğu ve uzmanlarından yardım ve destek için.
