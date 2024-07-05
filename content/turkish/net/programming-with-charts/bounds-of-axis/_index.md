---
title: Bir Grafikte Eksen Sınırları
linktitle: Bir Grafikte Eksen Sınırları
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak eksende görüntülenen değer aralığını kontrol ederek bir grafikte eksenin sınırlarını nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/bounds-of-axis/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir grafikte eksen sınırlarının nasıl ayarlanacağı açıklanmaktadır. Bir grafik ekleyerek, seri verileri ekleyerek ve eksen ölçeklendirmesini yapılandırarak eksen için minimum ve maksimum değerleri tanımlayabilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder`belgeyle çalışmaya itiraz edin.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Grafik Ekleme ve Yapılandırma
 kullanarak belgeye bir grafik ekleyin.`InsertChart` yöntemi`DocumentBuilder` nesne. İstediğiniz grafik türünü ve boyutlarını ayarlayın.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Adım 4: Seri Verilerini Ekleyin
Grafikteki mevcut serileri temizleyin ve yeni seri verileri ekleyin. Bu örnekte, "Öğe 1" etiketlerini "Öğe 5"e ve karşılık gelen değerlere sahip bir seri ekliyoruz.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Adım 5: Eksenin Sınırlarını Ayarlayın
 kullanarak minimum ve maksimum değerleri ayarlayarak Y ekseninin ölçeklendirmesini yapılandırın.`Scaling.Minimum` Ve`Scaling.Maximum` eksenin özellikleri.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Adım 6: Belgeyi Kaydedin
 Belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithCharts.BoundsOfAxis.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Aspose.Words for .NET kullanan Bounds Of Axis için örnek kaynak kodu 

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
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak bir grafikteki eksenin sınırlarını başarıyla ayarladınız.

## Çözüm
Bu eğitimde Aspose.Words for .NET'i kullanarak bir grafikte eksenin sınırlarını nasıl ayarlayacağınızı öğrendiniz. Adım adım kılavuzu izleyerek bir grafik ekleyip yapılandırabilir, seri verileri ekleyebilir ve eksen ölçeklendirmesi için minimum ve maksimum değerleri tanımlayabilirsiniz. Aspose.Words for .NET, Word belgeleriyle Kelime İşleme için güçlü ve esnek bir API sunarak kolaylıkla dinamik ve görsel olarak çekici grafikler oluşturmanıza olanak tanır.


### SSS

#### S1. Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin Word belgeleriyle programlı olarak çalışmasına olanak tanıyan bir kütüphanedir. Word belgelerini oluşturmak, değiştirmek ve kaydetmek için çok çeşitli özellikler ve işlevler sağlar.

#### Q2. Aspose.Words for .NET'i nasıl kurabilirim?
Aspose.Words for .NET'i yüklemek için Visual Studio'daki NuGet paket yöneticisini kullanabilirsiniz. NuGet paket yöneticisinde "Aspose.Words" ifadesini arayın ve projenize yükleyin.

#### S3. Aspose.Words for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?
Hayır, Aspose.Words for .NET, özellikle .NET uygulamaları için tasarlanmıştır. C# ve VB.NET gibi programlama dilleriyle çalışır.

#### S4. Aspose.Words for .NET'i kullanmanın başka önkoşulları var mı?
Aspose.Words for .NET kütüphanesini kurmanın yanı sıra, C# programlama ve Word belgeleriyle Kelime İşleme konusunda temel bilgiye sahip olmanız gerekir. .NET framework'üne aşina olmak da faydalı olacaktır.
