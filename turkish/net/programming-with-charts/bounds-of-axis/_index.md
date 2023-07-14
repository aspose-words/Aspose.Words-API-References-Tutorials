---
title: Grafikte Eksen Sınırları
linktitle: Grafikte Eksen Sınırları
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET'i kullanarak eksende görüntülenen değer aralığını kontrol ederek bir grafikte bir eksenin sınırlarını nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/bounds-of-axis/
---

Bu eğitim, Aspose.Words for .NET kullanılarak bir grafikte bir eksenin sınırlarının nasıl ayarlanacağını açıklar. Bir grafik ekleyerek, seri verileri ekleyerek ve eksen ölçeklendirmeyi yapılandırarak, eksen için minimum ve maksimum değerleri tanımlayabilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluştur`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmak için nesne.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Bir Grafik Ekleyin ve Yapılandırın
 kullanarak belgeye bir grafik ekleyin.`InsertChart` yöntemi`DocumentBuilder` nesne. İstenen grafik türünü ve boyutlarını ayarlayın.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## 4. Adım: Seri Verilerini Ekleyin
Grafikteki mevcut serileri temizleyin ve yeni seri verileri ekleyin. Bu örnekte, "Öğe 1" ile "Öğe 5" arasındaki etiketleri ve karşılık gelen değerleri içeren bir dizi ekliyoruz.

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

## 6. Adım: Belgeyi Kaydedin
 kullanarak belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithCharts.BoundsOfAxis.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Aspose.Words for .NET kullanan Bounds Of Axis için örnek kaynak kodu 

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
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak bir grafikte bir eksenin sınırlarını başarıyla belirlediniz.

## Çözüm
Bu eğitimde, Aspose.Words for .NET kullanarak bir grafikte bir eksenin sınırlarını nasıl ayarlayacağınızı öğrendiniz. Adım adım kılavuzu izleyerek bir grafik ekleyebilir ve yapılandırabilir, seri verileri ekleyebilir ve eksen ölçeklendirme için minimum ve maksimum değerleri tanımlayabilirsiniz. Aspose.Words for .NET, Word belgeleriyle Kelime İşleme için güçlü ve esnek bir API sağlayarak dinamik ve görsel olarak çekici grafikleri kolayca oluşturmanıza olanak tanır.


### SSS

#### S1. Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin Word belgeleriyle programlı olarak çalışmasına izin veren bir kitaplıktır. Word belgeleri oluşturmak, değiştirmek ve kaydetmek için çok çeşitli özellikler ve işlevler sağlar.

#### S2. Aspose.Words for .NET'i nasıl kurabilirim?
Aspose.Words for .NET'i kurmak için Visual Studio'da NuGet paket yöneticisini kullanabilirsiniz. NuGet paket yöneticisinde "Aspose.Words" ifadesini arayın ve onu projenize kurun.

#### S3. Aspose.Words for .NET'i diğer programlama dilleriyle kullanabilir miyim?
Hayır, Aspose.Words for .NET, özellikle .NET uygulamaları için tasarlanmıştır. C# ve VB.NET gibi programlama dilleri ile çalışır.

#### S4. Aspose.Words for .NET'i kullanmak için başka ön koşullar var mı?
Aspose.Words for .NET kütüphanesini kurmanın yanı sıra, C# programlama ve Word belgeleriyle Kelime İşleme hakkında temel bilgilere sahip olmalısınız. .NET çerçevesine aşinalık da yardımcı olacaktır.
