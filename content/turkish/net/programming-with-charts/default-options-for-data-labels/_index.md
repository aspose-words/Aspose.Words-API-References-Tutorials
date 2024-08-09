---
title: Grafikteki Veri Etiketleri İçin Varsayılan Seçenekleri Ayarlama
linktitle: Grafikteki Veri Etiketleri İçin Varsayılan Seçenekleri Ayarlama
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir grafikteki veri etiketleri için varsayılan seçenekleri nasıl ayarlayacağınızı öğrenin. Grafikleri zahmetsizce oluşturmak ve özelleştirmek için adım adım kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/default-options-for-data-labels/
---
## giriiş

Selam! Belge otomasyonu dünyasına dalmaktan heyecanlı mısınız? Bugün Aspose.Words for .NET'i programlı olarak büyüleyici belgeler oluşturmak için nasıl kullanabileceğimizi keşfedeceğiz. Aspose.Words, Word belgelerini kolaylıkla değiştirmenize olanak tanıyan güçlü bir kütüphanedir ve bu eğitimde, bir grafikteki veri etiketleri için varsayılan seçenekleri ayarlamaya odaklanacağız. İster deneyimli bir geliştirici olun, ister yeni başlayan biri olun, bu kılavuz, kısa sürede çalışmaya başlamanız için her adımda size yol gösterecektir.

## Önkoşullar

Başlamadan önce, bu eğitimle birlikte takip etmeniz gereken her şeye sahip olduğunuzdan emin olalım. İşte hızlı bir kontrol listesi:

- Visual Studio veya herhangi bir .NET uyumlu IDE: Kodunuzu yazacağınız ve çalıştıracağınız yer burasıdır.
-  Aspose.Words for .NET: Yapabilirsin[en son sürümü indir](https://releases.aspose.com/words/net/) ve projenize yükleyin.
- C# programlamaya ilişkin temel bilgiler: Bu kılavuz yeni başlayanlar için uygun olsa da, C#'a biraz aşina olmak faydalı olacaktır.
- .NET Framework yüklü: Makinenizde .NET Framework'ün kurulu olduğundan emin olun.
-  Aspose.Words için geçici lisans: Bir tane edinin[Burada](https://purchase.aspose.com/temporary-license/) Tam işlevselliğin kilidini açmak için.

Bu önkoşulları sıraladıktan sonra başlamaya hazırız!

## Ad Alanlarını İçe Aktar

Öncelikle projemizi kuralım ve gerekli namespace’leri import edelim. Bu ad alanları Aspose.Words işlevselliğine erişim için çok önemlidir.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.ReportingServices;
```

## 1. Adım: Yeni Bir Belge Oluşturun


 Yolculuk yeni bir belge oluşturup bir belge başlatarak başlar.`DocumentBuilder` .`DocumentBuilder` sınıf, belge içeriğini kolayca değiştirmek için bir dizi yöntem sağlar.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni bir belge oluştur
Document doc = new Document();

// DocumentBuilder'ı başlat
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Açıklama

 Bu adımda içeriğimizi eklemek ve biçimlendirmek için kullanacağımız belgeyi ve oluşturucuyu kurduk.`dataDir` değişken son belgemizi kaydedeceğimiz yolu tutar.

## 2. Adım: Grafik Ekleme

 Daha sonra belgemize bir pasta grafiği ekleyeceğiz.`InsertChart` yöntemi`DocumentBuilder` sınıf bunu çok kolaylaştırıyor.

```csharp
// Pasta grafiği ekleme
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);

// Grafik nesnesine erişme
Chart chart = shape.Chart;
```

### Açıklama

Burada belgemize bir pasta grafiği ekliyoruz.`InsertChart` yöntem, parametre olarak grafik türünü, genişliğini ve yüksekliğini gerektirir. Grafiği ekledikten sonra, onu daha fazla değiştirmek için grafik nesnesine erişiriz.

## 3. Adım: Grafik Serisini Özelleştirin

Şimdi grafikteki mevcut serileri temizleyip özel serilerimizi ekleyeceğiz. Bu seri veri noktalarımızı temsil edecek.

```csharp
// Mevcut grafik serisini temizle
chart.Series.Clear();

// Grafiğe yeni seriler ekleyin
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

### Açıklama

Bu adımda önceden var olan serileri temizleyerek grafiğimizin boş olduğundan emin oluyoruz. Ardından pasta grafiğimizde görüntülenecek özel kategorilere ve değerlere sahip yeni bir seri ekliyoruz.

## Adım 4: Veri Etiketleri için Varsayılan Seçenekleri Ayarlayın

Grafiğinizi bilgilendirici kılmak için veri etiketleri çok önemlidir. Yüzdeyi, değeri gösterme ve ayırıcıyı özelleştirme seçeneklerini ayarlayacağız.

```csharp
// Veri etiketleri koleksiyonuna erişme
ChartDataLabelCollection labels = series.DataLabels;

// Veri etiketi seçeneklerini ayarlama
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

### Açıklama

 Burada şuraya erişiyoruz:`DataLabels`Her veri etiketinde görüntülenen görünümü ve bilgileri özelleştirmek için serimizin özelliği. Hem yüzdeyi hem de değeri göstermeyi, öncü çizgileri gizlemeyi ve özel bir ayırıcı ayarlamayı seçtik.

## Adım 5: Belgeyi Kaydedin

Son olarak belgemizi belirtilen dizine kaydedeceğiz. Bu adım, tüm değişikliklerimizin bir dosyaya yazılmasını sağlar.

```csharp
// Belgeyi kaydet
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

### Açıklama

 Bu son adımda belgemizi kullanarak kaydediyoruz.`Save` Yöntem. Belge, belirtilen dizine kaydedilecektir.`dataDir`, "WorkingWithCharts.DefaultOptionsForDataLabels.docx" adıyla.

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak özelleştirilmiş pasta grafiğine sahip bir Word belgesini başarıyla oluşturdunuz. Bu güçlü kitaplık, belge oluşturmayı ve düzenlemeyi otomatikleştirmeyi kolaylaştırarak zamandan ve emekten tasarruf etmenizi sağlar. İster rapor, ister fatura, ister başka türde bir belge oluşturuyor olun, Aspose.Words yanınızdadır.

 Keşfetmekten çekinmeyin[Aspose.Words belgeleri](https://reference.aspose.com/words/net/) daha fazla özellik ve örnek için. Mutlu kodlama!

## SSS'ler

### Aspose.Words'ü ücretsiz kullanabilir miyim?
Aspose.Words'ü ücretsiz olarak kullanabilirsiniz.[geçici lisans](https://purchase.aspose.com/temporary-license/) veya özelliklerini kullanarak keşfedin[ücretsiz deneme](https://releases.aspose.com/).

### Aspose.Words için nasıl destek alabilirim?
 aracılığıyla destek alabilirsiniz.[Aspose.Words destek forumu](https://forum.aspose.com/c/words/8).

### Başka türde grafik ekleyebilir miyim?
 Evet, Aspose.Words çubuk, çizgi ve sütun grafikleri gibi çeşitli grafik türlerini destekler. Kontrol edin[dokümantasyon](https://reference.aspose.com/words/net/) daha fazla ayrıntı için.

### Aspose.Words .NET Core ile uyumlu mu?
 Evet, Aspose.Words .NET Core ile uyumludur. Daha fazla bilgiyi şurada bulabilirsiniz:[dokümantasyon](https://reference.aspose.com/words/net/).

### Aspose.Words lisansını nasıl satın alabilirim?
 adresinden lisans satın alabilirsiniz.[Aspose mağaza](https://purchase.aspose.com/buy).

