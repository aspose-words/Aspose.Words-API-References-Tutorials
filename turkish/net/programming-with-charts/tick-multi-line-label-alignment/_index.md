---
title: Çok Satırlı Etiket Hizalamasını işaretleyin
linktitle: Çok Satırlı Etiket Hizalamasını işaretleyin
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'i kullanarak çok satırlı etiketleri bir grafik ekseninde nasıl hizalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-charts/tick-multi-line-label-alignment/
---

Bu öğretici, Aspose.Words for .NET'in grafik eksenindeki çok satırlı etiketlerin hizalamasını ayarlamak için nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, bir grafiğin nasıl oluşturulacağını, eksene nasıl erişileceğini ve onay etiketi hizalamasının nasıl değiştirileceğini gösterir.

## 1. Adım: Projeyi kurun

Aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı yüklendi. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet paket yöneticisini kullanabilirsiniz.
- Çıktı belgesinin kaydedileceği bir belge dizini yolu.

## 2. Adım: Yeni bir belge oluşturun ve bir grafik ekleyin

 Yeni bir tane oluştur`Document` nesne ve bir`DocumentBuilder` belgeyi oluşturmak için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ardından,`InsertChart` yöntemi`DocumentBuilder` belgeye bir dağılım grafiği eklemek için.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## 3. Adım: Onay etiketi hizalamasını ayarlayın

 Çok satırlı etiketlerin hizalamasını ayarlamak için şuraya erişin:`AxisX` grafiğin özelliğini ayarlayın ve`TickLabelAlignment` özelliğini istediğiniz hizaya getirin. Bu örnekte, hizalamayı şu şekilde ayarladık:`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## 4. Adım: Belgeyi kaydedin

 Son olarak, belgeyi kullanarak belirtilen dizine kaydedin.`Save` yöntemi`Document` nesne.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Bu, Aspose.Words for .NET kullanarak çok satırlı etiket hizalamasını ayarlama uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Çok Satırlı Etiket Hizalama İşareti için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Bu özelliğin yalnızca çok satırlı etiketler için etkisi vardır.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```